# Documentation of RsyncOSX source

This is documentation of the design and code of RsyncOSX. I have just commenced the documentation (June 2017) and it will take time to complete. Why am I doing it? Well, primary for fun but i might learn something from it as well. The design of RsyncOSX is based upon ideas of the [MVC](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller) pattern. One of the objectives is to separate the views and models.

First will the data (model) and some of the methods operating on the data be documented. After that details about how RsyncOSX is working after data about configurations and schedules are loaded in memory. RsyncOSX kicks off the `rsync` utility to do the real work. The `rsync` is executed in a `Process` object. Every time RsyncOSX [executes](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/processCmd.swift) a command, RsyncOSX is listening for two notifications `didTerminateNotification` and `NSFileHandleDataAvailable`. Those two notifications kicks of other functions depended upon the state of RsyncOSX.

# High Level design

The views has no knowledge about the models or data stored about configurations, schedules and logdata. All data presented in RsyncOSX are mostly table data. Presenting table data utilizes the `NSTableViewDelegate`. All data which are stored to permanent store are saved as xml-files ([plist](https://en.wikipedia.org/wiki/Property_list) files). RsyncOSX does **not** utilize the Core Data because the data about `configurations`, `schedules` and `logs` are simple and there is no need for a complex datamodel.

## Configurations (tasks)

The configurations are read from the permanent store and kept in memory during RsyncOSX lifetime. Each record (one task) are read from permanent store as a `NSDictionary` item and loaded into an `Array<configuration>`. A [configuration](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/configuration.swift) is a struct holding all data about one task.

The object [SharingManagerConfigurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/SharingManagerConfiguration.swift) holds all data and methods operating on configurations. The method `readAllConfigurationsAndArguments` loads all data about configurations in memory. Every time a configuration is read the rsync arguments are computed and hold by the struct [argumentsOneConfiguration.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/argumentsOneConfiguration.swift) in memory. There are four types of arguments which are computed during startup, arguments for `--dry-run` and real run and both arguments for presentation on screen. Each configuration is allocated a uniq computed nonsense key `hiddenID = Int`.

The object [SharingManagerConfigurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/SharingManagerConfiguration.swift) creates an `Array<NSMutableDictionary>` which holds all data about `configuration` and computed values of arguments. Computed values are **not** saved to permanent store. They are computed when RsyncOSX starts or a new profile is loaded. The method `getConfigurationsDataSource()` returns the computed `Array<NSMutableDictionary>` and it is the data object which is loaded by the `NSTableViewDelegate` delegate methods into tables. As an example see [ViewControllertabMain.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ViewControllertabMain.swift) and `func tableView(_ tableView: NSTableView, objectValueFor tableColumn: NSTableColumn?, row: Int) -> Any?` how data is loaded into tables.

### Changes to configurations

All changes to configurations (edit, delete, new, parameters to rsync) is a three step operation:

- any changes to configurations are updated in memory (to the `Array<configuration>`)
  - [configuration](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/configuration.swift) is a struct holding all attributes for one configuration
  - the `Array<NSMutableDictionary>` is computed and read-only after loaded in memory
- after an update the configuration in memory configurations are saved to permanent store
- the configurations in memory are wiped out and loaded into memory from the permanent store to compute any new values due to changes
  - a new and computed `Array<NSMutableDictionary>` is loaded

This is a kind of brute force. No code needed for partly update and it secures a 100% correct and updated configuration in memory at all time. Saving, wiping memory and reading configurations is done in matter of milliseconds.

## Schedules and log data

Schedules and logdata is saved and loaded in separate data structure. [Schedules](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/configurationSchedule.swift) are linked to [configuration](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/configuration.swift) by `hiddenID=Int`. All logs are saved in separate file. Manually executed tasks are stamped with date (US-format) "01 Jan 1900 00:00".

A log record is constructed by number of files, size of transferred files in time (`58 files : 5.04 MB in 2.50 seconds`) as reported from rsync. The output from rsync is investigated and all numbers are copied from the rsync output. Every record are linked to its parent bye the function `computeKey` and used when records are deleted.

The object [SharingManagerSchedule](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/SharingManagerSchedule.swift) holds all data and operations working on Schedule data. 
# Changelog

Index of [RsyncOSX documentation](https://rsyncosx.github.io/Documentation/).

I am using the application on a daily basis and it evolves during my own use. Suggestions for new _features_, _changed features_ and _bug reports_ are more than welcome.

Please add an [Issue](https://github.com/rsyncOSX/RsyncOSX/issues) regarding any requests or bugs.

## New version 3.1.3 of rsync

There is 28 January 2018, released a new version of rsync - [version 3.1.3](https://rsync.samba.org/). I will include a .dmg file with latest version of rsync for manually install as part of the new release 4.9.9 of RsyncOSX. If you plan to utilize the [snapshot](https://github.com/rsyncOSX/Documentation/blob/master/docs/Snapshots.md) feature of RsyncOSX, please use either version 3.1.2 or 3.1.3 of rsync.

A compiled version of version 3.1.3 of rsync is included in the latest release candidate. My advise is to either compile your own version or install by utilizing homebrew.

## Version 5.0.1 release candidate

Updated 11 February 2018

I always looks for improvements and bugs in code. I also try to refactor code when I am learning new stuff about Swift and the refactor is beneficial. The next major enhancements in RsyncOSX is a
* [menu app](https://github.com/rsyncOSX/RsyncOSXsched)
to execute scheduled backups.

The `menu app`is a minimal version of RsyncOSX only capable of executing scheduled tasks. All editing of tasks and schedules are within RsyncOSX.

**Important:** There are some issues regarding how to enter `daily` and `weekly` schedules in version 5.0.0 of RsyncOSX. The scheduled part is redesigned in the release candidate. To activate a schedule select start date and time and type of schedule. The schedules are active until *deleted* or *stopped*. Schedule `once` only executes once, `daily` and `weekly` until stopped or deleted.

## Version 5.0.0

- released 1 February 2018
- [snapshot](https://github.com/rsyncOSX/Documentation/blob/master/docs/Snapshots.md) is the main new feature in this release
- enhancements in Quick Backup
	-	selecting the i-button checks and estimates the number of changed files compared to the remote storage
	- select which tasks to be executed and press the play button for executing tasks immidialaty
	- the progress of each task is presented (require an estimate first - the i-button)
- some minor cleanup in the schedule part

![](screenshots/4.9.9rc/quick3.png)
![](screenshots/4.9.9rc/quick1.png)

## Version 4.9.6

- released 9 January 2018
- a couple of minor bugfixes
	- in logging
	- in the ssh-tab for assisting setup of password less logins, when port number in use there is a bug, thx to [pierre-fromager](https://github.com/pierre-fromager) reporting the bug
	- bug in copy files when ssh port in use
- new function for **quick backups**, sort and select which tasks to be executed in one go
- new function for **info about backup locations**
- new function for doing **quick backups** from the **info about backup locations**
- in parameter view the rsync parameter `--compress` can be toggled on/off
- sort and filter in **quick backups** and **info about backup locations**

![](screenshots/4.9.5/remoteinfo.png)
![](screenshots/4.9.5/aboutrsync.png)

In right bottom of main view the version number of the `rsync` utilized in RsyncOSX is shown.

![](screenshots/4.9.5/start.png)
Select catalogs which should be backed up and close view. If there is a selection the Quick backup view will automatically opens with preselected tasks.
![](screenshots/4.9.5/remote.png)
There might be preselected catalogs to be backed up from the info view. Select which tasks to be executed in one go. List is sorted by selecting the appropriate column, by local catalog, remote catalog, remote server or days.
![](screenshots/4.9.5/quickbackup.png)
The result from backup tasks in log view.
![](screenshots/4.9.5/logs.png)

![](screenshots/4.9.5/select.png)
After selection choose execute and tasks are executed. When task is completed the row is marked completed with a check flag.
![](screenshots/4.9.5/execute.png)
Filter and select, filter by column.
![](screenshots/4.9.5/filter.png)
![](screenshots/4.9.5/filter2.png)

## Version 4.9.2

- v4.9.2 released 17 Dec 2017
- focus on GUI single tasks and batch
- adding several shortcuts
	- after selecting a row the following shortcuts are effective
	- `⌘E` - shortcut for edit task
	- `⌘O` - shortcut for rsync parameters to task
	- `⌘D` - shortcut for delete task
	- `⌘R` - shortcut for immediate execute task
	- `⌘A` - Abort task

![](screenshots/4.9.2rc/singletask1.png)
![](screenshots/4.9.2rc/singletask2.png)
![](screenshots/4.9.2rc/batch.png)
![](screenshots/4.9.2rc/shortcuts2.png)
If shortcut `⌘R` is pressed the backup task is executed immidialaty.
![](screenshots/4.9.2rc/shortcuts1.png)
Scheduling of tasks. A green mark is shown on a task if there are active schedules. The schedules view shows details about planned tasks.
![](screenshots/4.9.2rc/schedule2.png)
![](screenshots/4.9.2rc/schedule1.png)

## Version 4.9.1

- released 1 Dec 2017
- fixed a bug in batchview causing batch not executing properly

## Version 4.9.0

- released 28 Nov 2017
- new buttons are implemented
- fixed a typo and some minor fixes
![](screenshots/4.9.0rc/rsyncosx3.png)
![](screenshots/4.9.0rc/buttons.png)

## Version 4.8.6

- released 23 Nov 2017
- logging result after execution of tasks is fixed
- added possibility of logging, either minimum or full, output from rsync to loggfile in `Documents/rsynclog.txt`
	- the logging to file is default off when starting RsyncOSX, status of logging is not saved in userconfiguration
	- the log function appends new logs, be careful not logging all actions
- fixed some other minor glitches
- added number of days since last backup in main view
![](screenshots/4.8.6/main.png)
![](screenshots/4.8.6/user.png)
![](screenshots/4.8.6/loggfile.png)

## Version 4.8.2

* released 15 Nov 2017
* it is minor maintenance release, a couple of bugfixes and enhancements in batchview

## Version 4.8.1

* released 7 Nov 2017
* this will be the last release for RsyncOSX for some time
	- I have commenced a new project, the new project [RcloneOSX](https://rsyncosx.github.io/rcloneosx/) is adapting RsyncOSX to utilize [rclone](https://rclone.org)
	- the [Changelog](https://rsyncosx.github.io/rcloneosx/docs/RcloneOSX/Changelog.html) for the new project

The main focus in the version 4.8.1 is UX-design (user experience). The objective is to make the UX-experience in RsyncOSX as good as possible. Below are some samples of changes to make a better UX-design.
![](screenshots/4.8.1rc/ux1.png)
![](screenshots/4.8.1rc/ux2.png)
![](screenshots/4.8.1rc/ux3.png)
![](screenshots/4.8.1rc/ux4.png)
![](screenshots/4.8.1rc/norsync.png)

## Version 4.8.0

* released 25 Oct 2017
* redesigned the schedules part
* fixed a major bug in batch mode
	- hiding view in batch mode previous versions of RsyncOSX will reset the batch task
	- there are no risk for damaging files, just restart batch task and rsync(OSX) continues from where it stopped
* some other bug fixes as well
* the .dmg file is built on a mounted NOT APFS (SMB mount) filesystem to avoid problems mounting the .dmg file on non APFS systems

The [intro](https://rsyncosx.github.io/Documentation/docs/Intro.html) page is updated reflecting version 4.8.0.

## Version 4.7.5

* released 12 Oct 2017
* fixed bug in batch function

## Version 4.7.0

*Caution : there is a bug in the batch function, working on a new release.*

In version 4.5.1, configurations and schedules are kept in memory utilizing singeltons. In version 4.7.0 singeltons are replaced by dynamic objects. This results in cleaner code, less couplings and less housekeeping. Stateful objects are difficult and increases complexity in the code.

* released 10 Oct 2017
* major refactor of several parts (eliminating singeltons)
* changed how to get list of remote files (in Copy Files)
* changed how output from rsync executes and information from rsync output is collected
	- all the analysis on the output is done after a process termination is observed
	- in batch mode calling next task after a 1.0 second stop, if not a process termination might be observed before output from task is completed
* fixed a bug in batchview if rsync discover an error, now rsync aborts and close batchview and notifies about the rsync error
* fixed a bug in setting user selected parameters to rsync (the two first parameters)
* and fixed other minor bugs as well

View and delete log records or stop scheduled tasks (`⌘L`)from the main view.
![](screenshots/4.6.5rc/loggs.png)
Change profile from Schedule view (`⌘P`).
![](screenshots/4.6.5rc/profile.png)
Either double click on row or `⌘L` to view and delete log records or stop scheduled tasks from the schedules view.
![](screenshots/4.6.5rc/loggs2.png)
Refactor of collecting output from rsync, applies to copy files as well, more efficient. Selects info about 10,000 remote files in less than one second. Info about remote files is utilized by using rsync and it is very efficient.
![](screenshots/4.6.5rc/copyfiles.png)
Error handling in batch. As en example just added a parameter which makes rsync produce an error.
![](screenshots/4.6.5rc/error1.png)
![](screenshots/4.6.5rc/error2.png)
An error is discovered, batchview closes and batchwork is aborted.
![](screenshots/4.6.5rc/error3.png)
Pressing the Information button informs which error made rsync halt.
![](screenshots/4.6.5rc/error4.png)

## Version 4.5.1

Built with Xcode 9 GM.

There is a rsync-3.1.2.dmg included which is a built version of latest rsync. To install this version of rsync please make a catalog in your home directory (or use /usr/local/bin) and make RsyncOSX aware of using the new rsync in [userconfig](https://rsyncosx.github.io/Documentation/docs/UserConfiguration.html).

* released 13 Sept 2017
* using [SwiftLint](https://github.com/realm/SwiftLint) has caused several and major rewrites in parts of code
	* some of the classes are yet not adapted to SwiftLint rules
* code is adapted to Swift 4
* fixed a bug when choosing task for batch, an `execute` of task might accidentally start when select or deselect batch task
* fixed a bug in discover new version of RsyncOSX
* there are numerous internal changes and quite a few minor bugfixes
* refactor filter (search) functions in logs and copy files
* fixed a bug causing RsyncOSX to crash if loading new profile during a test for TCP connections
* added parameter `--max-delete=-1` to secure no execution of task if files will be deleted during run (user selected in setting rsync parameters)

![](screenshots/4.5.0rc/max-delete.png)
![](screenshots/4.5.0rc/max-delete-2.png)


## Version 4.4.6

* released 3 July 2017
* rewrite of code for executing single and batch tasks, reduces the complexity and size of code and it separates the view and model
* fixed a bug in Schedules some other minor bugs
* removed test for TCP connections remote servers to a button in main view (no automatic check for connections)


## Version 4.4.0

* released 8 June 2017
	* compiled with latest release 8.3.3 of Xcode (which was released June 2017)
* Seems like the [logging](Logging.md) problem is partly solved in 30 May 2017 update
* Added Abort when real task is executing
* Refactor of Copy Single files/directory
	* in userconfig set temporary restore catalog (for single files or directory)
	* display size remote files
	* double click on row to get remote filelist
	* double click on row to restore files or directory to temporary (local) catalog
* Clean up of other parts of code

![](screenshots/4.3.5/abort.png)
![](screenshots/4.3.5/config.png)
![](screenshots/4.3.5/remote.png)
![](screenshots/4.3.5/filelist.png)
![](screenshots/4.3.5/doubleclick.png)
![](screenshots/4.3.5/finished.png)

## Version 4.3.0

* released 8 May 2017
* assist in setup of [passwordless logins](PasswordlessLogin.md)
	* see [doc](ssh.md) - documentation in progress
* couple of bugfixes

## Version 4.2.5

**Bug** in version 4.2.5 causes RsyncOSX to crash if RsyncOSX is minimized during execution of a task. Bug is fixed and will be released in version 4.3.0.

**Next** release (version 4.3.0) will probably include some functionality for assisting setup of [passwordless logins](PasswordlessLogin.md). Don't know when it will be released. Summer is coming and further development of RsyncOSX will be slowed down during summer. I am currently working on this release now and (slowly) progressing...

* released 23 Apr 2017
* minor bugfixes and cleanup of code
* compiled with new release of Xcode (version 8.3.2)
* adjusted the parameters to rsync
* adjusted the schedule

![](screenshots/4.2.5/parameter.png)
![](screenshots/4.2.5/mainview.png)

In the parameter to rsync, if `backup` option is selected RsyncOSX adds the directory to the backup catalog (for saving changed and deleted files). Choose either suffix for FreeBSD or Linux. Neither of them works on **local backup** macOS (have to test more). But, if you copy and paste the FreeBSD suffix in a terminal window it works on macOS (it adds the correct timestamp to the changed files in the backup directory).

![](screenshots/4.2.5/schedule.png)

The schedule now informs if a scheduled backup plan is to short ahead. A weekly backup must be at least seven days ahead of current date and time.

## Version 4.2.0

* released 10 April 2017
* compiled with new release of Xcode (version 8.3.1)
* enhanced the batchwork part
* fixed a couple of minor bugs
* some cleanup in code
* reorganized Help
* there is an issue when RsyncOSX counts files to be transferred in *batchmode*, the issue does not introduce any faults (informal only)
* there is also an issue when RsyncOSX is logging, sometimes RsyncOSX does log 0 files and not the actual number of files and size of transfer (informal only)

![](screenshots/4.1.5rc/batch.png)

## Version 4.1.0

* released 19 March 2017
* fixed one bug in parameters to rsync (causing RsyncOSX to crash)
* new help function - opens relevant html page in browser
* added new info using rsync version 3.1.2 (number of *new* and *delete* files)
	* see [user configuration](UserConfiguration.md) how set other version of rsync

![](screenshots/4.1.0/new.png)


## Version 4.0.0

* released 8 March 2017
* new application icon by Forrest Walter (this is the primary reason why releasing a new version)
* added new functionality in `Copy files` - double click on source get list of files from remote server

![](screenshots/4.0.0/copy.png)


## Version 3.9.7

Sometimes rsync throws errors and does not execute as expected. Single task is implemented as queue of work (`estimate`, `execute` and `done`). If `estimate` or `execute` fails (by some reason) the user has to be made aware of situation and fix it.

RsyncOSX checks output from rsync for string *rsync error:*. If found main view is notified, error is marked (in red) and work queue is reset if option in userconfig (see below) is set. To test enter a not valid user name for a remote server ([edit task](SingleTask.md) in main view).

Other changes:

- released 2 March 2017
- some refactor and several cleanup of code
- Added reporting any file errors (in profile) to main view.
- There is also fixed a minor bug in Profiles.
- In About menu reference to GitHub Pages about Changelog and Documentation of RsyncOSX

See [releases](https://github.com/rsyncOSX/Version3.x/releases) for download.

![Shedules](screenshots/3.9.6rc/config.png)
![Logs](screenshots/3.9.6rc/error.png)

## Version 3.9.5

Version 3.9.5 might **crash** for some user. This is due to localized string representation of dates in logs. RsyncOSX only accepts `en_US` format of dates in logs. Comparing and sorting other localized string representation of dates causes a crash.

If RsyncOSX crash during startup please delete the schedule and loggfile: `Documents/Rsync/MacID/scheduleRsync.plist` (deleting this file only deletes any schedule and logs).


- released 28 January 2017
- I´m not adding any major new functionality to RsyncOSX, only minor enhancements.
- the focus in this release candidate is to make logs more informal and stable
- logs are now sorted with most recent log on top (first row in table)
- active schedules are marked red
	- number of logs in each schedule
	- manual execution of tasks are logged under start date `1 Jan 1900 00:00`
- dates are forced to "en_US" localization to prevent RsyncOSX from crashing if the preferred language of macOS is other than english (e.g. Norwegian)

![Shedules](screenshots/3.9.5rc/screen2.png)
![Logs](screenshots/3.9.5rc/screen1.png)


## Version 3.9.1
- released 19 January 2017
- added a few tweaks regarding radio buttons in main view and deselect row after delete actions
- moved Add button new configurations into tab view and added some more checks when adding new configurations
- In Sch

## Version 3.8.6
After releasing this version I will not release new versions for some time. I have to focus on my new job (start 2 January 2017) for some time. I will continue to develop RsyncOSX in the future, but the number of new releases will drop compared to 2016.

- fixed bug in profiles
- added an alternative suffix (in [parameters](Parameters.md) to rsync)
- added delete log rows in log view
- even more cleanup of code

## Version 3.7.7
- released **23 December 2016**
- fixing one bug in Profiles introduced another bug causing logs to be overwritten

## Version 3.7.6
- released **23 December 2016**
- fixed yet another bug in Profiles
	- bug causing old configurations and schedule data not properly cleaned when new profile is created
- compiled with latest version 8.2.1 of Xcode
- the are several parts of code which is refactored
	- cleaned up external references (in About and NewVersion)
	- added guard statements to make code safer
	- fixed a bug in Main.storyboard referring to a non existing class
	- refactor of computing parameters to rsync

## Version 3.7.2
- fixed a bug in set optional path for rsync

## Version 3.7.1
- updated **13 December 2016**, compiled with new version 8.2 of Xcode released 12 December 2016
- released **10 December 2016**
- fixed a bug `--suffix` parameter used together with `--backup` parameter to set date and time suffix (e.g `changed-file_2016-12-10.15.25`) of changed or deleted files in backup directory
- split `--backup` parameter and `--suffix` in parameter view
- refactor of code for rsync parameters and logging
- speed of sorting and filter logs improved
- added display both `--dry-run` and `real run` of rsync command in main view

## Version 3.6.5

- released **23 November 2016**
	- this will be the last release for some time (most likely last release this year)
	- there are no known issues or request for new features
	- I will continue develop RsyncOSX in 2017, there are some internal parts which should be refactored
- new About view (links to docs, changelog and check for new versions)
- fixed a bug in Edit configurations (reset values when new configuration is loaded)
- some minor cleanup of code

## Version 3.6.1

- released 15 November 2016
- [logs part](Logging.md) is changed, text search for **remote server**, **local catalog** or **executed date/time**
- there is a bug in deleting ssh-port - **fixed**
- there is a bug in enabling Profiles menu when RsyncOSX is started on a Mac for the first time (Profiles menu is not enabled) - **fixed**
- sometimes output from rsync is set to **nil** (in RsyncOSX), doing an unwrap of nil value causes RsyncOSX to crash - **fixed**


## Version 3.5.5

- new image updated **10 November 2016** : some minor GUI tweaks and automatic dismiss after 10 seconds in some of the views
- new image updated **5 November 2016** : if selecting new profile before background check for connection is completed RsyncOSX might crash, fix is done and new image is uploaded. Background check is executed when main view loads and remote servers not responding is marked red.
- released 3 November 2016
- fixed a couple of bugs in automatic dismiss of popup views (when scheduled backups are running and in main view a popup informs of backup)
- some minor refactor of code


## Version 3.5.1

- new image updated **2 November 2016** : added check for optional version and path of rsync
- new image updated **1 November 2016** : "moved" GUI updates in background (Scheduled operations) to main thread - making RsyncOSX unstable if not - throwing "CoreAnimation: warning, deleted thread with uncommitted CATransaction" if not
- **caution** : a bug in Scheduled jobs caused version 3.5.1 released 30 October 2016 to crash - a new image of version 3.5.1 uploaded late 30 October 2016.
- released 30 October 2016
- fixed a bug in version 3.5.0 deleting/stopping schedules causing a nil pointer exception and crash
  - bug was "introduced" when compiling RsyncOSX with latest release version 8.1 of Xcode
- notify new versions of RsyncOSX by delegate
- mainly a maintenance release, some bigger internal changes and some GUI tweaks
- RsyncOSX is more stable than ever
  - replaced states by work queue (using states get complex even with a few states)
  - I am learning Swift every day and [refactor code](https://en.wikipedia.org/wiki/Code_refactoring) is important
- code ([master](https://github.com/rsyncOSX/Version3.x/tree/master)) at Github is updated with last commits
- added double click for executing single task and select profile
  - double click first time executes a dry run, another double click after dryrun executes the real task
  - enable/disable double click in user configuration


## Version 3.4.1

- released 20 October 2016
- copy and paste was by mistake not in 3.4.0 - now it is...
- there was an issue with Copy files (search and copy single files or catalogs) - if you experience any problems with copy files in version 3.4.1 please update to last image of version 3.4.1


## Version 3.4.0

- released 19 October 2016
- added profiles - select profiles from the File menu, profiles is just new catalogs for storing configurations and schedules files.
- backup of single files in Add view, only backup part is added for single files, use Copy Files to search and restore single files
- some minor internal cleanup and fixes, adjusted Copy Files view
- added abort in Copy Files (terminates search process)
- in logs view selecting row selects logs for selected remote server
- removed test mode in RsyncOSX - replaced by profiles
- user configuration available from Main tab, Add tab and Schedule tab
- in main tab when rsync is changed in user configuration, if row is selected rsync command in view is updated
- counting of files and directories from rsync output is more robust, only version 3.x of rsync counting directories remote


## Version 3.3.0

- released 6 October 2016
- capture of more precise info about files, tested on both stock version on rsync and 3.1.2 of rsync (only version 3.x counts directories)
- fixed a bug not saving path for other version of rsync
- added backup in rsync parameters
  - changed files are moved to backup location (default ../backup) and appended a timestamp before updated files are transferred from source to destination
  - useful when saving versions of e.g. documents
- fixed a memory leak in scheduling of tasks
  - after the last release 4 Oct 2016 it seems that there are no memory leaks (at least the graphic memory debugger in Xcode reports no leaks as well as the Xcode instrument Memory Leaks)


## Version 3.1.5

- released 24 Sept 2016
  - image is updated 26 Sept 2016 (fixed a few minor glitches)
- added detailed logging
  - logging switch on/off in Configuration
- hopefully no more releases for some time after this release


## Version 3.1.0

- updated 22 Sept (released 20 Sept 2016)
- scheduling of tasks
- added (22 Sept 2016) adding local volumes by graphical window or drag and drop from Finder
- a few minor bug fixes (22 Sept 2016)


## Version 3.0.5

- updated 15 Sept 2016
- copy of single files or catalogs from remote storage
  - doing a restore require to press the Estimate button twice, once for a -- dry-run (estimate) and the the real run (execute)
- some visual enhancements
- Scheduling of tasks is **not yet** included in this version (will be in version 3.1.0)
  - tasks might be scheduled in version 3.0.5 but not executed


## Version 3.0.0

- built on macOS 10.12 GM by Xcode 8 GM (GM = "gold master")
- supports macOS 10.11 and macOS 10.12

What is **NOT** implemented in version 3.0

- no execution of Scheduled task, but scheduled task may be added, stopped and deleted
  - the code for execution of scheduled tas has to be revised and tested
  - will come in version 3.1.0
- no copy of single files or catalogs from remote servers
  - will come in version 3.1.0
- no detailed logging
  - will come in version 3.1.0


## Changelog prior version 3.0.0

Changelog prior to version 3.0.0 is deleted. The initial release was 14 March 2016 and code is rewritten since the initial release.


## Version 0.5 beta

- initial listing 14 March 2016, released on MacUpdate as well

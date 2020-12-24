## Analytics > Log & Crash Search > Release Notes

### December 15, 2020
#### Updates/Changes
* [Console] Displays and limits the maximum number of letters allowed for title and description when setting alarms
* [Console] Fixed the bug where the change is not saved when the threshold for crash alarm is modified to 0
* [Console] Deleted log retention period of 6 months and 1 year while adding that of 4 months

### October 13, 2020
#### Feature Updates
* Changed the capacity limit for a single log (general or crash) from 2MB to 8MB 

### September 22, 2020 
#### Feature Changes
* [Console] Supports IAM console from access link for TOAST Log & Search, attached to notifications of email, or Dooray!  

### August 25, 2020 
#### Feature Changes
* [Console] Updated to enter and execute multiple objects for alarm callback/webhook

### July 28, 2020
#### Feature Updates
* [Console] Added the feature of integrity validation for logs that are externally stored 
    * [See Console User Guide](/Analytics/Log%20&%20Crash%20Search/ko/console-guide/#_27)

### June 23, 2020
#### Feature Updates
* [Console] Changed the query method for Object and Array types
    * Query delivery method must be same as the search of character strings
    * [See Guide for Lucene Query](/Analytics/Log%20&%20Crash%20Search/ko/lucene-query-guide/)

### May 26, 2020
#### Feature Updates
* [Console] Support analyzing iOS app crashes applied with Bitcode  
    * Modified to upload and analyze symbol files for each architecture within same version

### April 28, 2020
#### Feature Updates
* [Console] Restricted the maximum available period for a log search up to 3 months 
* [API] Changed the identification method for Android NDK crash  
#### Bug Fixes
* [Console] Fixed bugs in which modified queries are not properly saved under particular conditions

### March 24, 2020	
#### Feature Updates 
* [Console] Edited the error message for failure in deleting saved queries 

### February 25, 2020
#### Feature Updates
* [Console] Modified tooltip messages on the setting page of SDK log delivery. 
* [Console] Added, in query saving, the validity authetication process for Lucene query.
#### Bug Fixes 
* [Console] Fixed bugs in which particular Windows symbol files cannot be processed in uploading symbol files. 
    * Due to many builds, if the age of Windows PDB exceeds 11, symbol files that are extracted afterwards may contain a guid which has more than 34 characters. The limit of 33 characters for a guid field has been lifted. 
* [Console] Fixed bugs, in which fields that are saved with the search of logs older than 30 days are not properoly exposed.

### January 21, 2020
#### Feature Updates
* [Console] Changed how to locate the occurrence of iOS crashes. 
* [Console] Allows additional display of information on iOS crashes (on TOAST SDK iOS 0.21.0 or higher versions).

### October 29, 2019
#### Feature Updates
* [Console] Added the feature of S3 uploading. 
* [Console] Changed the error message for alarms activated due to invalid query of alarm. 

### August 27, 2019
#### Bug Fixes 
- [Console] Fixed an event in which search of a particular query is unavailable from the list. 

### June 25, 2019
#### Updates/Changes 
* Fixed the (null) ((null)) symbolication result of some iOS crash logs.   
* Increased the capacity limit of a single log case (general and crash) from 1MB to 2MB.
* Modified to display actual phone numbers on the list of alarm recipients.

#### Bug Fixes
* Allowed to query modified alarms from the list, when the last modifier has been excluded from project members.   

### May 28, 2019
#### Bug Fixes
* [Console] Fixed abnormal operations in some pages for Windows 10 and Internet Explorer 11. 
* [Console] Fixed the unavailability of interpreting some zip files when symbolized files were uploaded. 
* [Console] Allows to immediately apply particular parts when language was changed on a web console. 
* [Console] Fixed the alarm setting by which https callback setting was unavailable. 

### March 27, 2019
#### Feature Updates
* [Console] Support analysis of crashes occured on iOS arm64e (requires compatible SDK).
* [Console] Support analysis of crash occurred on Android NDK (requires compatible SDK).
* [Console] Apply globalization (in Japanese) 

### January 15, 2019
#### Feature Updates
* [Console] Applied on User console 
* [Console] Exclude crash occurred at Unity from the indicator.
    * Not collected from Search App Crash > App Crash Indicators. 
* [Console] Added the feature of reverting status before registration, after issue tracker is registered. 
* [Console] Emphasize actual symbol names applied for symbolication on the symbolic file management page. 

### Novermber 27, 2018
#### Feature Updates 
* [Console] Fixed an issue in which exception type is not properly judged when an Android crash occurs for Unity and the crash type is recorded as 'java.lang.Error'.
    * Fixed an issue in which access is unavailable to detail page from Web Console > Crash > Query Issues.
    * Fixed failed exposure of issue count per version from Web Console > Crash > Issue Statistics. 
* [Console] Updates for Alarm-related UX/UI  
    * Alarm registration 
    * History of alarms
    * Crash alarm registration 
    * History of crash alarms 
    * User-based alarm registration
    * History of user-based alarms 
* [Console] Added guides of symbol files for Android Unity on the Web Console > Setting > Uploading Symbol Files. 
* [Console] Changed validation for Network Insight URL. 

### October 23, 2018 
#### Feature Updates
* [Console] Closed log alarms (old)
    * [Relevant Notice](https://toast.com/support/notice/detail/1453435858K00594)

### September 18, 2018 
#### Feature Updates
* [Console] Share query for saving 

### September 4, 2018 
#### Feature Updates
* [SDK][[logback-3.0.2](/Download/#analytics-log-crash-search)]
    * Updated not to add reservation items, when Logncrash Appender has empty or null for non-default items of reservation words.
    * Set timeout for Longrash REST API.
    * Enable AsynAppender for Logback.

#### Bug Fixes
* [SDK][[logback-3.0.2](/Download/#analytics-log-crash-search)]
    * Fixed bugs in which reservation words, such as empty or null, were added. 

### July 24, 2018 

#### Feature Updates
* [Console] Changed UI for the setting page.

### June 26, 2018

#### Bug Fixes
* [SDK][[iOS-2.7.1](/Download/#analytics-log-crash-search)]
    * Fixed bugs in which crash occurred during initialization in duplicates. 

### June 5, 2018

#### Feature Updates
* [SDK][[Android-2.6.7](/Download/#analytics-log-crash-search)]
    * Changed operations for saved logs, to be sent without filtering.

#### Bug Fixes
* [SDK][[iOS-2.7.0](/Download/#analytics-log-crash-search)]
    * Changed internal logic of SDK. 
    
* [SDK][[Android-2.6.7](/Download/#analytics-log-crash-search)]
    * Fixed bugs in which logs were not sent in Android 4.1.2 or lower versions (bugs on Android-2.6.6 SDK).

* [SDK][[Unity-2.8.6](/Download/#analytics-log-crash-search)]
    * Fixed an issue in which the loglevel was set as fatal when Unity crash logs occurred on iOS. 

### May 29, 2018 

* [Console] Fixed an issue in which symbolication didn't work when bundles of duplicate names (e.g. Framework.UIKit, Accessibility.UIKit) exist among iOS crash symbolication.  

### May 09, 2018

#### Bug Fixes

* [SDK][[Unity-2.8.5](/Download/#analytics-log-crash-search)]
    * Roll back crash logtype occurred at Unity Script
        * Rolls back with crash occurred at Unity Script processed as Handled. 

### May 2, 2018 

#### Feature Updates

* [SDK][[AOS-2.6.6](/Download/#analytics-log-crash-search)]
    * Removed IP Address collection field 
        * Apply information collected from the server for "host" on console 

* [SDK][[Unity-2.8.4](/Download/#analytics-log-crash-search)]
    * Updated Call Android Native SDK API 

#### Bug Fixes

* [SDK][[AOS-2.6.6](/Download/#analytics-log-crash-search)] 
    * Fixed filter error in removing duplicates 

* [SDK][[iOS-2.6.10](/Download/#analytics-log-crash-search)]
    * Fixed the occurrence of crash during initialiation, when userID was nil
    * Fixed the CPU usage rate raised up to 100% when enableSyncStart was YES

### April 24, 2018

#### Bug Fixes
* [Console] Fixed invalid numbering of an issue, when integrated with app crash Gitlab 
* [Console] Fixed failed symbolication when symbol files for app crash are deleted and uploaded, still in the same version 
* [Console] Fixed failure in SMS alarm transfer when particular characters are included to an alarm
* [Console] Fixed failed SMS alarm transfer for app crash when a particular country code is included to an alarm recipient

### January 22, 2018 
#### Feature Updates
* [Console] Released Network Insights 

### December 21, 2017 
#### Feature Updates 
* [Console] Added query-based alarms

### October 26, 2017
#### Feature Updates
* [Console] Added the feature of alarm setting when a new crash occurs 

#### Bug Fixes
* [console] Modified to show error message when a session is expired 

### September 21, 2017 
#### Feature Updates
* [SDK] Added a function that does not automatically register CrashHandler during initialization (see MultihandlerSample)
* [SDK] Changed to allow transferring Unity Crash via CrashHandler registered externally (see MultihandlerSample)
* [SDK] Removed unnecessary SDKs through the optimization script (see Doc documents)
* [SDK] Allows the user to save settings at a time in need  
    * Updated Version: [toast-logncrash-unity-2.8.3](/Download/#analytics-log-crash-search)
* [Console] Changed the input method of log search time (to remove ms and specify timezone)
* [Console] Show total count as output when the distinct count is over 100 for a specific field 
* [Console] Deleted UIs of users experiencing crash on the trend page 
* [Console] Changed the mail format for crash alarms (deleted dmpData and formatted DmpReport) 
* [Console] Changed criteria of classifying Unity crashes 
    * Modified not to classify error-level logs of Unity as crashes
        * Search and query is available on the log search page 

#### Bug Fixes
* [SDK] Fixed an issue in which sessionID is updated when initialize is called many times 
* [SDK] Fixed the failed release of activity from the memory, if closed with BackKey, since SDK has saved its last status 
    * Updated Version: [toast-logncrash-android-2.6.4](/Download/#analytics-log-crash-search) / [toast-logncrash-unity-2.8.3](/Download/#analytics-log-crash-search)
* [SDK] Modified to include 'EMPTY CRASH FILE' to DmpData for transfer, if PLCrashReporter fails to create crash files. 
    * Updated Version: [toast-logncrash-ios-mac-sdk-2.6.7](/Download/#analytics-log-crash-search) [toast-logncrash-unity-2.8.3](/Download/#analytics-log-crash-search)
* [SDK] Fixed wrong display of CrashStyle and SymMethod, when navitve crash occurs on iOS SDK 
* [SDK] Fixed failed settings of userID on WeGL
* [SDK] Fixed an issue in which https protocol was not specified by the Unity ios wrapper class
    * Updated Version: [toast-logncrash-unity-2.8.3](/Download/#analytics-log-crash-search)

### July 20, 2017
#### Feature Updates
* [SDK] Support WebGL Platform 
    * Updated Version: [toast-logncrash-unity-2.7.4](/Download/#analytics-log-crash-search)
* [Console] Removed user count from the softing option on the page of crash list

#### Bug Fixes
* [Console] Fixed bugs in crash user layout 

### June 22, 2017 
#### Bug Fixes
* [SDK] Fixed an issue in which crash occurs due to the Delete bug of LFU when the duplicate control queue exceeds the maximum size  
    * Updated Version: [toast-logncrash-cpp-windows-sdk-2.5.4](/Download/#analytics-log-crash-search) / [toast-logncrash-csharp-windows-sdk-2.5.4](/Download/#analytics-log-crash-search)/ [toast-logncrash-androidndk-sdk-2.6.2](/Download/#analytics-log-crash-search)
* [SDK] Changed the method of saving Resend logs from 20MB by 2MB, to 2MB only  
* [SDK] Changed the size of Send Queue from 500 to 200 
* [SDK] Modified the transfer being disabled, when it is disconnected to the internet, to the file saving mode.  
* [SDK] When it is re-connected to the internet, logs saved in files are to be re-sent 
    * Updated Version: [toast-logncrash-cpp-windows-sdk-2.5.4](/Download/#analytics-log-crash-search) / [toast-logncrash-csharp-windows-sdk-2.5.4](/Download/#analytics-log-crash-search)
* [SDK] Fixed missing of some fields (country code, platform information, and etc.)
    * Updated Version: [toast-logncrash-android-2.6.2](/Download/#analytics-log-crash-search)
* [SDK] Errors are contained in errorCode and txterrorCode filds to be transferred 
    * Updated Version: [toast-logncrash-logback-sdk-2.2.7](/Download/#analytics-log-crash-search) / [toast-logncrash-log4j-sdk-2.2.7](/Download/#analytics-log-crash-search)

### June 19, 2017
#### Bug Fixes
* [SDK] Fixed an issue in which CPU usage rate reaches 99% since sleep is not available for SendThread 
* [SDK] Fixed failed release of a memory when 100 logs are sent per second  
    * Udated Version: [toast-logncrash-ios-unity-mac-sdk-2.6.6.1](/Download/#analytics-log-crash-search)

### May 25, 2017
#### Feature Updates
* [Console] Added autocomplete for the log search field name 
* [Console] Changed the display order and processed grey for UserID Colum on the table at the page bottom of the Crash > App Crash Indicators 
* [Console] Allows the user to turn on/off for the exposure of session log page
* [SDK] Integrated Unity Android and Android 
    * Updated Version: [toast-logncrash-android-2.6.1](/Download/#analytics-log-crash-search)
* [SDK] Added Enable/ Disable Hotfield
    * Updated Version: [toast-logncrash-android-2.6.1](/Download/#analytics-log-crash-search) / [toast-logncrash-androidndk-sdk-2.6.1](/Download/#analytics-log-crash-search)

#### Bug Fixes
* [SDK] Fixed redundant transfer of session logs when unity crash is resent
* [SDK] Fixed bugs in which the DeviceID field is missing 
    * Updated Version: [toast-logncrash-ios-unity-mac-sdk-2.6.5.1](/Download/#analytics-log-crash-search)

### April 20, 2017
#### Feature Updates
* [Console] Changed the page layout for app crash indicators 
    * Shows SDK version on the screen 
    * Shows both User/Device information on table 
    * Changed table header, "Version" -> "App Version (SDK version)"
* [Console] Changed page layout for crash map and added the number of devices on the map
* [Console] Activated opening new windows 
* [Console] Changed alarm delivery format (shows alarm name, instead of project name)
* [SDK] Added more features 
    * To ensure AddCustomField between the Init function and log delivery, added SendThread Lock 
        * Updated Version: [toast-logncrash-ios-unity-mac-sdk-2.6.0](/Download/#analytics-log-crash-search) / [toast-logncrash-android-unity-sdk-2.6.0](/Download/#analytics-log-crash-search) / [toast-logncrash-android-2.6.0](/Download/#analytics-log-crash-search)
* [SDK] Changed features 
    * Send Exception, errorCode, and RequestHeader fields in the analyzable format on console 
		* Changed field names into txtException, txterrorCode, and txtRequestHeader 
		* Updated Version: [toast-logncrash-log4j-sdk-2.2.6](/Download/#analytics-log-crash-search) / [toast-logncrash-log4j2-sdk-2.2.6](/Download/#analytics-log-crash-search)/ [toast-logncrash-logback-sdk-2.2.6](/Download/#analytics-log-crash-search)
		* When the alarm is set for the Exception,errorCode, and RequestHeader field, apply 2.6 and change it to txt\* field.  
    * Changed the sending method allowing logs to be collected up to 2M before sending
        * Updated Version: [toast-logncrash-ios-unity-mac-sdk-2.6.0](/Download/#analytics-log-crash-search) / [toast-logncrash-android-unity-sdk-2.6.0](/Download/#analytics-log-crash-search) / [toast-logncrash-android-2.6.0](/Download/#analytics-log-crash-search)
* [SDK] Integrated Unity-ios and ios SDKs
    * See README.md file within SDK file for changes 
    * [Toast-logncrash-ios-unity-mac-sdk-2.6.0](/Download/#analytics-log-crash-search)
    *  Deleted Toast-logncrash-unity-ios-sdk / toast-logncrash-ios-mac-sdk 

#### Bug Fixes
* Fixed failed snooze operations when the alarm cycle is not one minute 
### March 23, 2017
#### Feature Updates
* [Console] Updated crashes with failed dump analysis to provide statistics in the format of UNKNOWN crash 
* [Console] Shows guide message on the stack trace page when stack trace is unavailable 
    * Shows guide message on the stack trace page when stack trace is unavailable (when the error type is UNKNOWN) since symbol files are not registered 

#### Bug Fixes
* [Console] Fixed the broken display of the Real Time Monitoring tab on the English page of crash search 

### February 23, 2017
#### Feature Updates
* [API] [log Bulk upload](/Analytics/Log%20&%20Crash%20Search/ko/api-guide/) is available 
    * Sending REST API logs is available in the JSON array format. 
* [API] Added Long/ Double Options 
    * In sending REST API logs, fields starting with long or double can be saved in long or double type. 
    * Range search is available for long or double type on the log search page. 
* [SDK] Added CrashCallback 
    * [Windwos csharp SDK 2.5.2.1](/Download/#analytics-log-crash-search) / [Windows cpp SDK 2.5.2.1](/Download/#analytics-log-crash-search)

#### Bug Fixes
* [WEB] Fixed unavailability of deleting query on View Saved Queries 
* [WEB] Updated pagination so that a back button on issue details does not return to page 1 on the list
* [SDK] Fixed conflicts between threads 
    * [unity-android-sdk 2.5.6.0](/Download/#analytics-log-crash-search)
* [SDK] Fixed error in the binaryimagesort duplicate symbol, occurred when building external libray along with logncrash   
    * [unity-ios-sdk-2.5.2.6](/Download/#analytics-log-crash-search)
* [SDK] Fixed forced closure, on some devices, of an application before breakpad is completed
    * [androidndk-sdk 2.4.7.0](/Download/#analytics-log-crash-search)
* [SDK] Modified failed adding of customField under the Async mode 
    * [Log4j-sdk-2.2.5](/Download/#analytics-log-crash-search)/ [Logback-sdk-2.2.5](/Download/#analytics-log-crash-search)

### January 19, 2017
#### Feature Updates
* Changed criteria for version display of app crash indicators
    * Modified to show the version in which crash exists under execution, even if not occurred, from App Crash Indicators > Crash 
#### Bug Fixes
* Modified the Show/Hide All Logs feature on the Log Search page 

### Decembr 22, 2016
#### Feature Updates
* Restrict downloading of log files to be no more than 100 thousand on the Web page 
    * Send alarms on popup with over 100 thousand trials     
* [SDK] Added a feature to collect exceptions to the iOS/Android native level 
    * Updated Version: unity-android-sdk-2.5.1, unity-ios-sdk-2.5.1
* [SDK] Restrict the size of log duplicate queue to be no more than 1,000
    * Updated Version: Android-2.4.3, Android-NDK-2.4.5, iOS-2.4.1, unity-android-2.5.1, unity-ios-2.5.1

### December 8, 2016
#### Feature Updates
* When a user, who registered content for Query Issue > Issue Details > Comment, History, has been deleted from project members, the user is identified as "[Deleted Member]" on email.

#### Bug Fixes
* Fixed bugs in the log alarm setting, where log alarm list is not properly queried when "\" is included to the character strings included (excluded) to the filtering rule 
* Modified to show failure alarms when there's not a member list to newly save crash alarms 

### November 24, 2016
* [SDK] Changed the setting to get a host from internal thread, since the getaddrinfo function applied to get a host field hangs on some devices   
  * Updated Version: Android-NDK 2.4.4

### November 4, 2016
#### Bug Fixes
* [SDK] Changed logic to Thread, since Android 2.4.1 has a bug preventing AsyncTask from cancelled 
  * Updated Version: Android 2.4.2

### October 20, 2016
#### Feature Updates
* Collect DeviceID as original ID of device
    * Sending crash logs via new SDK allows DeviceID to be collected, and indicators by DeviceID are made available on Console > Log & Crash Search > Crashes > App Crash Indicators. 
* [SDK] When a log delivery is unavailable, it can be saved in a file to be transferred during normal communication.   
* [SDK] Applies duplicate log processing routine to all logs 
    * When duplicate log is enabled, same logs in the body and loglevel are not sent. 
    * If necessary, user's own control is available on a specific API.  
    * For more details, see Developer's Guide.
* [Console] Changed 'Session', 'User Count' from App Crash Indicators , to 'Execution Count', and 'User experiencing crash'. 

### September 29, 2016
#### Feature Updates
* Set alarm thresholds and added http callback 
    * Support operators (>,>=,=,<=,<) for comparing alarm thresholds 
    * Added the feature of More/Less as compared to n time ago  
    * Added snoozing 
* Added the UserTxtData field downloadable from the log search page 
    * Check "UserTxtData" on the Log Search page from [Download|View] 

#### Bug Fixes
* [SDK] Fixed repetitive attempts of initialization, for exceptional cases, due to failure in initializing log transfer objects 
    * Updated SDK: logback , log4j, log4j2
* [SDK] Fixed a bug in which value was not properly added to the log when UserID was set for the fixed init function 
    * Updated SDK: iOS

### September 12, 2016
#### Bug Fixes
* [SDK] Added exception processing codes for carrier and for cases in which the carrier value is returned to null 
    * Updated SDK: Unity(v.2.3.4)

### August 22, 2016
#### Feature Updates
* Changed the option and length restrictions of Custom Field Default 
    * Set false for 'Analyzed' when the custom field is created  
    * Changed the available log length for a transfer from 128byte to 2Kbyte
    * When a log transfer with 2Kbyte or more is required, specify txt prefix for the field name to create a custom field 
    * Field names (txt_description) starting with txt, such as txt*; string, or option [in], are saved as analyzed fields <br>
      Search by some character strings of a field value is available on the log search page 


### August 18, 2016
#### Feature Updates
* Allows ON/OFF for Log Transfers 
    * User can set On/Off for logs transferred via Log & Crash Search (General/Crash/Session Logs) and decide whether to collect on console.
    * Non-collected logs are not displayed on the screen and excluded from API or Storage charges. 
    * Updated SDK by adding the Log On/Off feature. 
        * Updated SDK(v.2.3.0): Unity, Android , Windows, and iOS

* [API] Added UserBinaryData field
    * Download is available on the log search page when log file or binary file is sent to the field 

#### Bug Fixes
* [Console] Fixed the speed issue of loading crash details  


### August 4, 2016
#### Feature Updates
* [SDK][Unity] Updated to 2.2.6 
    * Changed the format of saving SaveToFile
    * Modified to convert regular expression, by using JSON library
    * Limit the maximum file count to be saved up to 100
    * Limit the maximum queue count to remove duplicates up to 100  

#### Bug Fixes
* [API] Fixed an issue in which json array or object is converted to string, when sent to a specific field  

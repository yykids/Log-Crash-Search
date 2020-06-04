## Analytics > Log & Crash Search > Release Notes

### Feb. 25, 2020
#### Feature Updates
* [Console] Modified tooltip messages on the setting page of SDK log delivery. 
* [Console] Added, in query saving, the validity authetication process for Lucene query.
#### Bug Fixes 
* [Console] Fixed bugs in which particular Windows symbol files cannot be processed in uploading symbol files 
    * Due to many builds, if the age of Windows PDB exceeds 11, symbol files that are extracted afterwards may contain a guid which has more than 34 characters. The limit of 33 characters for a guid field has been lifted. 
* [Console] Fixed bugs, in which fields that are saved with the search of logs older than 30 days are not properoly exposed.


### Jan. 21, 2020
#### Feature Updates
* [Console] Changed how to locate the occurrence of iOS crashes 
* [Console] Allows additional display of information on iOS crashes  (on TOAST SDK iOS 0.21.0 or higher versions)

### Oct. 29, 2010
#### Feature Updates
* [Console] Added the feature of S3 uploading 
* [Console] Changed the error message for alarms activated due to invalid query of alarm 

### August 27, 2019
#### Bug Fixes 
- [Console] Fixed an event in which search of a particular query is unavailable from the list. 

### June 25, 2019
#### Updates/Changes 
* Fixed the (null) ((null)) symbolication result of some iOS crash logs   
* Increased the capacity limit of a single log case (general and crash) from 1MB to 2MB
* Modified to display actual phone numbers on the list of alarm recipients

#### Bug Fixes
* Allowed to query modified alarms from the list, when the last modifier has been excluded from project members   

### May 28, 2019
#### Bug Fixes
* [Console] Fixed abnormal operations in some pages for Windows 10 and Internet Explorer 11 
* [Console] Fixed the unavailability of interpreting some zip files when symbolized files were uploaded 
* [Console] Allows to immediately apply particular parts when language was changed on a web console 
* [Console] Fixed the alarm setting by which https callback setting was unavailable 

### March 27, 2019
#### Feature Updates
* [Console] Support analysis of crashes occured on iOS arm64e (requires compatible SDK.)
* [Console] Support analysis of crash occurred on Android NDK (requires compatible SDK.)
* [Console] Apply globalization (for Japanese) 국제화 적용 (일본어)

### January 15, 2019
#### Feature Updates
* [Console] Applied on User console 
* [Console] Exclude crash occurred at Unity from the indicator
    * Not collected from Search App Crash > App Crash Indicators 
* [Console] Added the feature of reverting status before registration, after issue tracker is registered 
* [Console] Emphasize actual symbol names applied for symbolication on the symbolic file management page 

### Novermber 27, 2018.11.27
#### Feature Updates 
* [Console] Fixed an issue in which exception type is not properly judged when an Android crash occurs for Unity and the crash type is recorded as 'java.lang.Error'
    * Fixed an issue in which access is unavailable to detail page from Web Console > Crash > Query Issues
    * Fixed failed exposure of issue count per version from Web Console > Crash > Issue Statistics 
* [Console] Updates for Alarm-related UX/UI  
    * Alarm registration 
    * History of alarms
    * Crash alarm registration 
    * History of crash alarms 
    * User-based alarm registration
    * History of user-based alarms 
* [Console] Added guides of symbol files for Android Unity on the Web Console > Setting > Uploading Symbol Files 
* [Console] Changed validation for Network Insight URL 

### October 23, 2018 
#### Feature Updates
* [Console] Closed log alarms (old)
    * [Relevant Notice](https://toast.com/support/notice/detail/1453435858K00594)

### September 18, 2018 
#### Feature Updates
* [Console] Share query for saving 

### September 04, 2018 
#### Feature Updates
* [SDK][[logback-3.0.2](/Download/#analytics-log-crash-search)]
    * Updated not to add reservation items, when Logncrash Appender has empty or null for non-default items of reservation words
    * Set timeout for Longrash REST API
    * Enable AsynAppender for Logback 

#### Bug Fixes
* [SDK][[logback-3.0.2](/Download/#analytics-log-crash-search)]
    * Fixed bugs in which reservation words, such as empty or null, were added 

### July 24, 2018 

#### Feature Updates
* [Console] Changed UI for the setting page 

### June 26, 2018

#### Bug Fixes
* [SDK][[iOS-2.7.1](/Download/#analytics-log-crash-search)]
    * Fixed bugs in which crash occurred during initialization in duplicates 

### June 05, 2018

#### Feature Updates
* [SDK][[Android-2.6.7](/Download/#analytics-log-crash-search)]
    * Changed operations for saved logs, to be sent without filtering

#### Bug Fixes
* [SDK][[iOS-2.7.0](/Download/#analytics-log-crash-search)]
    * Changed internal logic of SDK 
    
* [SDK][[Android-2.6.7](/Download/#analytics-log-crash-search)]
    * Fixed bugs in which logs were not sent in Android 4.1.2 or lower versions (bugs on Android-2.6.6 SDK)

* [SDK][[Unity-2.8.6](/Download/#analytics-log-crash-search)]
    * Fixed an issue in which the loglevel was set as fatal when Unity crash logs occurred on iOS 

### May 29, 2018 

* [Console] Fixed an issue in which symbolication didn't work when bundles of duplicate names (e.g. Framework.UIKit, Accessibility.UIKit) exist among iOS crash symbolication  

### May 09, 2018

#### Bug Fixes

* [SDK][[Unity-2.8.5](/Download/#analytics-log-crash-search)]
    * Roll back crash logtype occurred at Unity Script
        * Rolls back with crash occurred at Unity Script processed as Handled. 

### May 02, 2018 

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
    * 초기화 과정에서 UserID 의 값이 nil 일 때 Crash가 발생하던 문제 수정 Fixed the occurrence of crash during initialiation, when userID was nil
    * 초기화 과정에서 enableSyncStart 의 값이 YES 일 경우 CPU 이용률이 100%까지 올라가는 문제 수정 Fixed the CPU usage rate raised up to 100% when enableSyncStart was YES

### April 24, 2018

#### Bug Fixes
* [Console] 앱 크래시 Gitlab 이슈 연동 시, 이슈 번호가 잘못 채번되는 문제 수정 Fixed invalid numbering of an issue, when integrated with app crash Gitlab 
* [Console] 앱 크래시 용도의 심볼파일을 삭제 후 같은 버전으로 심볼파일 업로드 시, 정상적으로 심볼리케이션 되지 않는 문제 수정 Fixed failed symbolication when symbol files for app crash are deleted and uploaded, still in the same version 
* [Console] SMS 알람에서 특정 문자가 알람 내용에 포함되어 있을 때 알람이 전송되지 않는 문제 수정 Fixed failure in SMS alarm transfer when particular characters are included to an alarm
* [Console] 앱 크래시에서 알람 수신자에 특정 국가코드가 포함되어 앱 크래시 SMS 알람이 전송되지 않는 문제 수정 Fixed failed SMS alarm transfer for app crash when a particular country code is included to an alarm recipient

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
* [SDK] Added a function that does not automatically register CrashHandler during initialization (see MultihandlerSample 참고)
* [SDK] Changed to allow transferring Unity Crash via CrashHandler registered externally 외부에서 등록한 CrashHandler를 통해 Unity Crash를 전송할 수 있도록 변경 (see MultihandlerSample 참고)
* [SDK] Removed unnecessary SDKs through the optimization script 스크립트를 통한 필요없는 SDK 제거 (see Doc 문서 참고 )
* [SDK] Allows the user to save settings at a time in need  사용자가 Settings 객체를 원하는 시점에 저장할 수 있도록 변경
    * Updated Version: [toast-logncrash-unity-2.8.3](/Download/#analytics-log-crash-search)
* [Console] Changed the input method of log search time (to remove ms and specify timezone)로그 서치 시간 출력 방식 변경 (ms 단위 제거 및 timezone 명시)
* [Console] Show total count as output when the distinct count is over 100 for a specific field 특정 필드의 distinct count가 100을 넘으면 TOTAL count를 출력 
* [Console] Deleted UIs of users experiencing crash on the trend page 트렌드 페이지에서 crash를 겪은 사용자 UI 삭제
* [Console] Changed the mail format for crash alarms (deleted dmpData and formatted DmpReport) 크래시 알람 메일 포맷 변경(dmpData 삭제 및 DmpReport formatting)
* [Console] Unity 크래시 분류 기준 변경 Changed criteria of classifying Unity crashes 
    * Unity 발생되는 ERROR 레벨의 로그들에 대해서 크래시로 분류 하지 않도록 수정됨 Modified not to classify error-level logs of Unity as crashes
        * Search and query is available on the log search page 

#### Bug Fixes
* [SDK] Fixed an issue in which sessionID is updated when initialize is called many times 를 여러번 호출하는 경우 SessionID가 갱신 되는 문제 수정 
* [SDK] Fixed the failed release of activity from the memory, if closed with BackKey, since SDK has saved its last status 로 Activity를 종료한 경우, SDK에서 마지막 Activity 상태를 저장하고 있어 Activity가 메모리에서 해제 되지 않는 문제 수정
    * Updated Version: [toast-logncrash-android-2.6.4](/Download/#analytics-log-crash-search) / [toast-logncrash-unity-2.8.3](/Download/#analytics-log-crash-search)
* [SDK] Modified to include 'EMPTY CRASH FILE' to DmpData for transfer, if PLCrashReporter fails to create crash files. 가 Crash File을 생성하지 못하는 경우, 'EMPTY CRASH FILE'을 DmpData에 넣어 전송하도록 수정
    * Updated Version: [toast-logncrash-ios-mac-sdk-2.6.7](/Download/#analytics-log-crash-search) [toast-logncrash-unity-2.8.3](/Download/#analytics-log-crash-search)
* [SDK] iOS SDK에서 Native Crash 발생 시, CrashStyle, SymMethod가 잘못 표기되는 문제 수정 Fixed wrong display of CrashStyle and SymMethod, when navitve crash occurs on iOS SDK 
* [SDK] WebGL에서UserID가 설정되지 않던 문제 수정 Fixed failed settings of userID on WeGL
* [SDK] unity ios wrapper class에서 https 프로토콜이 지정되지 않던 문제 수정 Fixed an issue in which https protocol was not specified by the Unity ios wrapper class
    * Updated Version: [toast-logncrash-unity-2.8.3](/Download/#analytics-log-crash-search)

### July 20, 2017
#### Feature Updates
* [SDK] Support WebGL Platform 
    * Updated Version: [toast-logncrash-unity-2.7.4](/Download/#analytics-log-crash-search)
* [Console] 크래시 목록 화면 softing option에서 사용자수 제거 Removed user count from the softing option on the page of crash list

#### Bug Fixes
* [Console] Fixed bugs in crash user layout 

### June 22, 2017 
#### Bug Fixes
* [SDK] Fixed an issue in which crash occurs due to the Delete bug of LFU when the duplicate control queue exceeds the maximum size  중복제어 큐가 최대 사이즈가 넘은 경우, LFU 동작의 Delete 버그로 인해 Crash가 발생하는 현상 수정
    * Updated Version: [toast-logncrash-cpp-windows-sdk-2.5.4](/Download/#analytics-log-crash-search) / [toast-logncrash-csharp-windows-sdk-2.5.4](/Download/#analytics-log-crash-search)/ [toast-logncrash-androidndk-sdk-2.6.2](/Download/#analytics-log-crash-search)
* [SDK] ReSend 로그 저장 시 2MB씩 총 20MB저장하는 방식에서 2MB만 저장하도록 변경 Changed the method of saving Resend logs from 20MB by 2MB, to 2MB only  
* [SDK] Send Queue 사이즈를 500개에서 2000개로 변경 Changed the size of Send Queue from 500 to 200 
* [SDK] 인터넷이 연결되어 있지 않은 경우, 전송 동작을 하지 않는 방식에서 파일로 저장하도록 변경 Modified the transfer being disabled, when it is disconnected to the internet, to the file saving mode.  
* [SDK]인터넷 연결이 끊겼다가 다시 연결된 경우, 파일에 저장했던 로그를 재전송 하도록 변경 When it is re-connected to the internet, logs saved in files are to be re-sent 
    * Updated Version: [toast-logncrash-cpp-windows-sdk-2.5.4](/Download/#analytics-log-crash-search) / [toast-logncrash-csharp-windows-sdk-2.5.4](/Download/#analytics-log-crash-search)
* [SDK] 일부 필드(국가 코드, 플랫폼정보 등) 누락 현상 수정 Fixed missing of some fields (country code, platform information, and etc.)
    * Updated Version: [toast-logncrash-android-2.6.2](/Download/#analytics-log-crash-search)
* [SDK] 에러 내용을 errorCode와 txterrorCode 필드에 담아 전송하도록 변경 Errors are contained in errorCode and txterrorCode filds to be transferred 
    * Updated Version: [toast-logncrash-logback-sdk-2.2.7](/Download/#analytics-log-crash-search) / [toast-logncrash-log4j-sdk-2.2.7](/Download/#analytics-log-crash-search)

### June 19, 2017
#### Bug Fixes
* [SDK] SendThread에 Sleep이 없어 CPU 사용률이 99%가 되는 현상 수정 Fixed an issue in which CPU usage rate reaches 99% since sleep is not available for SendThread 
* [SDK] 초당 100건의 로그를 보내는 경우, 메모리 해제가 정상적으로 되지 않는 현상 수정 Fixed failed memory release when 100 logs are sent per second  
    * Udated Version: [toast-logncrash-ios-unity-mac-sdk-2.6.6.1](/Download/#analytics-log-crash-search)

### May 25, 2017
#### Feature Updates
* [Console] 로그서치 필드명 자동완성 기능 추가 Added autocomplete for the log search field name 
* [Console] Crashes > 앱 크래시 지표 페이지 하단 테이블 UserID Column 표시 순서 변경 및 Gray 처리 Changed the display order and processed grey for UserID Colum on the table at the bottom of the app crash indicators page 
* [Console] 세션로그 화면 노출 여부를 사용자가 on/off 할 수 있도록 기능 추가 Allows the user to turn on/off for the exposure of session log page
* [SDK] Integrated Unity Android and Android 통합 
    * Updated Version: [toast-logncrash-android-2.6.1](/Download/#analytics-log-crash-search)
* [SDK] Added Enable/ Disable Hotfield
    * Updated Version: [toast-logncrash-android-2.6.1](/Download/#analytics-log-crash-search) / [toast-logncrash-androidndk-sdk-2.6.1](/Download/#analytics-log-crash-search)

#### Bug Fixes
* [SDK] Unity Crash 재전송 시, Seesion 로그가 한 번 더 전송되는 동작 수정 Fixed redundant transfer of session logs when unity crash is resent
* [SDK] DevicID 필드가 누락되는 버그 수정 Fixed bugs in which the DeviceID field is missing 
    * Updated Version: [toast-logncrash-ios-unity-mac-sdk-2.6.5.1](/Download/#analytics-log-crash-search)

### April 20, 2017
#### Feature Updates
* [Console] 앱크래시지표 화면 레이아웃 변경 Changed the page layout for app crash indicators 
    * 앱크래시지표 화면에 SDK버전 표시 Shows SDK version on the screen 
    * 사용자 / 디바이스 정보 테이블에 같이 표시 Shows both User/Device information on table 
    * 테이블 헤더 변경 "버전" -> "앱버전 (SDK버전)" Changed table header, "Version" -> "App Version (SDK version)"
* [Console] 크래시맵 화면 레이아웃 변경 및 멥에 디바이스 수 추가 Changed page layout for crash map and added the number of devices on the map
* [Console] 새창 열기 기능 활성화 Activated opening new windows 
* [Console] 알람 발송 포맷 변경(프로젝트 이름 대신 알람 이름 노출 Changed alarm delivery format (show alarm name, instead of project name)
* [SDK] 기능 추가 Added more features 
    * To ensure AddCustomField between the Init function and log delivery, added SendThread Lock 함수와 Log 전송 사이의 AddCustomField를 보장하기 위하며, SendThread Lock 기능 추가
        * Updated Version: [toast-logncrash-ios-unity-mac-sdk-2.6.0](/Download/#analytics-log-crash-search) / [toast-logncrash-android-unity-sdk-2.6.0](/Download/#analytics-log-crash-search) / [toast-logncrash-android-2.6.0](/Download/#analytics-log-crash-search)
* [SDK] 기능변경 Changed features 
    * Send Exception, errorCode, and RequestHeader fields in the analyzable format on console 필드를 콘솔에서 분석 가능한 형태로 전송
		* Changed field names into txtException, txterrorCode, and txtRequestHeader 필드명으로 변경됨
		* Updated Version: [toast-logncrash-log4j-sdk-2.2.6](/Download/#analytics-log-crash-search) / [toast-logncrash-log4j2-sdk-2.2.6](/Download/#analytics-log-crash-search)/ [toast-logncrash-logback-sdk-2.2.6](/Download/#analytics-log-crash-search)
		* When the alarm is set for the Exception,errorCode, and RequestHeader field, apply 2.6 and change it to txt\* field 필드에 대해 알람설정이 된경우 2.6 적용 후 txt\* 필드로 수정이 필요함
    * Changed the sending method allowing logs to be collected up to 2M before sending최대 2M까지 로그를 모아 전송하도록 Send 방식 변경
        * Updated Version: [toast-logncrash-ios-unity-mac-sdk-2.6.0](/Download/#analytics-log-crash-search) / [toast-logncrash-android-unity-sdk-2.6.0](/Download/#analytics-log-crash-search) / [toast-logncrash-android-2.6.0](/Download/#analytics-log-crash-search)
* [SDK] Integrated Unity-ios and ios SDKs
    * See README.md file within SDK file for changes 변경사항은 SDK 파일내 README.md 파일 참고
    * [Toast-logncrash-ios-unity-mac-sdk-2.6.0](/Download/#analytics-log-crash-search)
    *  Deleted Toast-logncrash-unity-ios-sdk / toast-logncrash-ios-mac-sdk 삭제

#### Bug Fixes
* Fixed failed snooze operations when the alarm cycle is not one minute 알람 주기가 1분이 아닌 경우 snooze 가 동작 하지 않는 무제 수정
### March 23, 2017
#### Feature Updates
* [Console] Updated crashes with failed dump analysis to provide statistics in the format of UNKNOWN crash 덤프 분석에 실패한 크래시도 UNKNOWN 크래시 형태로 통계 정보를 제공 하도록 기능 개선
* [Console] Show guide message on the stack trace page when stack trace is unavailable 스택 트레이스를 표시할 수 없을때, 스택 트레이스 화면에 안내 문구 표시
    * Show guide message on the stack trace page when stack trace is unavailable (when the error type is UNKNOWN) since symbol files are not registered 심볼파일을 등록하지 않아서 스택 트레이스를 표시할 수 없을 때 (에러타입이 UNKNOWN일 때), 스택 트레이스 화면에 안내문구 표시

#### Bug Fixes
* [Console] 영문 크래시 서치 화면에서 Real Time Monitoring 탭 깨지는 현상 Fixed the broken display of the Real Time Monitoring tab on the English page of crash search 

### February 23, 2017
#### Feature Updates
* [API] [log Bulk upload](/Analytics/Log%20&%20Crash%20Search/ko/api-guide/) Available 기능 추가
    * REST API 로그 전송시 JSON array 형태로 로그 전송이 가능합니다. Sending REST API logs is available in the JSON array format. 
* [API] Added Long/ Double Options  옵션 추가
    * In sending REST API logs, fields starting with long or double can be saved in long or double type. 로그 전송시 long, double 로 시작하는 필드 사용시 long,double 타입으로 저장
    * 로그 검색 화면에서 long, double 타입 Range 검색이 가능합니다. Range search is available for long or double type on the log search page. 
* [SDK] Added CrashCallback 기능 추가
    * [Windwos csharp SDK 2.5.2.1](/Download/#analytics-log-crash-search) / [Windows cpp SDK 2.5.2.1](/Download/#analytics-log-crash-search)

#### 버그 수정 Bug Fixes
* [WEB] 저장된 쿼리 보기 페이지에서 쿼리 삭제 불가능한 문제 수정 Fixed unavailability of deleting query on View Saved Queries 
* [WEB] 이슈 상세에서 뒤로가기 클릭하면 이슈 목록 1페이지로 이동하지 않도록 pagination 개선 Updated pagination so that a back button on issue details does not return to page 1 on the list
* [SDK] Thread간의 충돌 현상 수정 Fixed conflicts between threads 
    * [unity-android-sdk 2.5.6.0](/Download/#analytics-log-crash-search)
* [SDK] 외부 라이브러리와 logncrash를 함께 빌드 시 binaryimagesort duplicate symbol 오류 수정 Fixed error in the binaryimagesort duplicate symbol, occurred when building external libray along with logncrash   
    * [unity-ios-sdk-2.5.2.6](/Download/#analytics-log-crash-search)
* [SDK] 일부 기기에서 breakpad 의 작업이 완료되기 전 어플리케이션이 강제로 종료 되는 현상 수정 Fixed forced closure, on some device, of an application before breakpad is completed
    * [androidndk-sdk 2.4.7.0](/Download/#analytics-log-crash-search)
* [SDK] Async 모드에서 customField 가 추가되지 않는 현상 수정 Modified failed adding of customField under the Async mode 
    * [Log4j-sdk-2.2.5](/Download/#analytics-log-crash-search)/ [Logback-sdk-2.2.5](/Download/#analytics-log-crash-search)

### January 19, 2017
#### Feature Updates
* 앱 크래시 지표 버전 표시 기준 변경 Changed criteria for version display of app crash indicators
    * 앱 크래시 지표 > 크래시가 발생하지 않았지만 실행수가 존재하는 버전도 표시 되도록 수정 Modified to show the version in which crash exists under execution, even if not occurred, from App Crash Indicators > Crash 
#### Bug Fixes
* Log Search 화면에 로그 모두 보이기/숨기기 기능 수정 Modified the Show/Hide All Logs feature on the Log Search page 

### Decembr 22, 2016
#### Feature Updates
* Restrict downloading of log files to be no more than 100 thousand on the Web page 화면에서 로그 파일 다운로드시 최대 10만개로 제한
    * 10만개 이상 시도시 팝업 알람 Send alarms on popup with over 100 thousand trials     
* [SDK] iOS/Android 의 네이티브 레벨 예외를 수집할수 있도록 기능 추가 Added a feature to collect exceptions to the iOS/Android native level 
    * Updated Version: unity-android-sdk-2.5.1, unity-ios-sdk-2.5.1
* [SDK] Restrict the size of log duplicate queue to be no more than 1,000
    * Updated Version: Android-2.4.3, Android-NDK-2.4.5, iOS-2.4.1, unity-android-2.5.1, unity-ios-2.5.1

### December 08, 2016
#### Feature Updates
* 이슈 조회 > 이슈 상세 > 코멘트, 히스토리 탭에서 내용을 등록한 사용자가 프로젝트 멤버에서 삭제 된 경우 When the user who registered content for Query Issue > Issue Details > Comment, History has been deleted from project members
  Show 이메일 노출 부분에 "[Deleted Member]" on email 로 표시 Shows

#### Bug Fixes
* 로그 알람 설정 시 필터링 규칙의 (비)포함 문자열에 "\"가 포함될 경우 로그 알람 목록이 조회되지 않는 버그 수정 Fixed bugs in the log alarm setting, where log alarm list is not properly queried when "\" is included to the character strings included (excluded) to the filtering rule 
* 크래시 알람 신규 저장 시 멤버 리스트가 없을 경우 실패 알람이 뜨도록 수정 Modified to show failure alarms when there's not a member list to newly save crash alarms 

### November 24, 2016
* [SDK] 일부 기기에서 host필드를 구하는데 사용되는 getaddrinfo 함수가 hang현상을 유발하여, host값은 내부 thread에서 구하도록 변경
  * Updated Version: Android-NDK 2.4.4

### November 04, 2016
#### Bug Fixes
* [SDK] Android 2.4.1 버전에서 AsyncTask가 Cancel 되지 못하는 버그가 있어, 해당 로직을 Thread로 변경
  * Updated Version: Android 2.4.2

### October 20, 2016
#### Feature Updates
* 기기의 고유 ID 값인 DeviceID 수집
    * 신규 SDK을 통한 Crash Log 전송시 DeviceID가 수집되어 Console > Log & Crash Search > Crashes > 앱 크래시 지표 화면에서
      DeviceID 기준으로 지표 확인이 가능합니다.
* [SDK] 로그 전송이 안되는 경우 파일로 저장 후 이후 정상 통신이 되는 경우 로그 파일 전송하도록 기능 변경됨.
* [SDK] 모든 로그에 대해 중복 로그 처리 루틴 적용
    * 중복 로그 기능이 켜져 있는 경우 Body 와 logLevel 의 내용이 같은 로그가 발생하면 전송하지 않습니다.
    * 필요한 경우 사용자가 별도의 API로 제어 가능하도록 기능 제공됨.
    * For more details, see Developer's Guide.
* [Console] Changed 'Session', 'User Count' from App Crash Indicators , to 'Execution Count', and 'User experiencing crash'. 앱 크래시 지표 화면 > '세션','사용자수' 타이틀 '실행 수' '크래시를 겪은 사용자'로 변경됨.

### September 29, 2016
#### Feature Updates
* 알람 임계치 설정 및 http Callback 기능 추가 Set alarm threshold and add http callback 
    * 알람 임계 값 비교 연산자 지원(>,>=,=,<=,<)
    * n 시간전 비교 이상/이하 기능 추가
    * Snooze 기능 추가
* Log Search 화면에서 다운로드 가능한 UserTxtData 필드 추가
    * "UserTxtData" 필드는 Log Search 화면에서 [다운로드|보기] 표시 하여 필드 내용을 바로 확인이 가능

#### Bug Fixes
* [SDK] Exception이 발생한 경우 , 로그 전송 객체를 초기화 하지 못하여 반복적으로 초기화를 재시도 하던 버그 수정
    * Updated SDK: logback , log4j, log4j2
* [SDK] init 함수에 UserID를 세팅하면 로그에 값이 정상적으로 추가되지 않던 버그 수정
    * Updated SDK: iOS

### September 12, 2016
#### Bug Fixes
* [SDK] Carrier와 Carrier 값이 null이 return되는 케이스에 대한 예외처리 코드 추가
    * Updated SDK: Unity(v.2.3.4)

### August 22, 2016
#### Feature Updates
* Custom Field Default 옵션 및 길이 제한 변경
    * Custom 필드 생성시 analyzed(분석여부) false 로 변경
    * 전송 가능한 로그 길이 128byte -> 2Kbyte 변경
    * 2Kbyte 이상의 로그 전송이 필요한 경우 Field 명에 txt prefix 지정하여 Custom field 생성
    * txt*; string, 옵션 [in] 필드 이름이 txt로 시작하는 필드(txt_description 등)는 분석(analyzed) 필드로 저장<br>
      로그 검색 화면에서 필드 값의 일부 문자열로 검색이 가능


### August 18, 2016
#### Feature Updates
* Log 전송 ON / OFF 기능 추가
    * Log & Crash Search 로 전송되는 로그(일반로그/크래시로그/세션로그)에 대해 사용자가 콘솔에서
      On/Off 설정, 수집여부를 결정할수 있습니다.
    * 수집되지 않은 로그는 화면에 노출되지 않고, API 및 Storage 요금에 포함되지 않습니다.
    * Log on/off 기능 추가로 SDK 업데이트 되었습니다.
        * 대상 SDK(v.2.3.0): Unity, Android , Windows, iOS

* [API] Added UserBinaryData field필드 추가 
    * 로그 파일이나 바이너리 파일을 위 필드로 전송시 로그 검색 화면에 다운로드 가능 Download is available on the log search page when log file or binary file is sent to the field 

#### Bug Fixes
* [Console] Fixed the speed issue of loading crash details  


### August 04, 2016
#### Feature Updates
* [SDK][Unity] Updated to 2.2.6 업데이트
    * SaveToFile 저장 포맷 변경 Changed the format of saving SaveToFile
    * Regular Expression, JSON 라이브러리를 사용하여 변환하도록 수정 Modified to convert by using regular expression, JSON library
    * 파일 최대 저장 개수 100개 제한 Limit the maximum file count to be saved up to 100
    * 중복 제거 큐 100개 제한 Limit the maximum queue count to remove duplicates up to 100  

#### Bug Fixes
* [API] 특정 필드에 json array나 object를 전송한 경우 string으로 변환 되는 현상 수정 Fixed an issue in which json array or object sent to a specific field to be converted to string 

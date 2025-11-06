```
PS C:\Windows> cd ../
PS C:\> cd /commands
cd : 'C:\commands' 경로는 존재하지 않으므로 찾을 수 없습니다.
위치 줄:1 문자:1
+ cd /commands
+ ~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (C:\commands:String) [Set-Location], ItemNotFoundException
    + FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.SetLocationCommand

PS C:\> pwd

Path
----
C:\


PS C:\> :/commands
:/commands : ':/commands' 용어가 cmdlet, 함수, 스크립트 파일 또는 실행할 수 있는 프로그램 이름으로 인식되지 않습니다. 이름이 정확한지
 확인하고 경로가 포함된 경우 경로가 올바른지 검증한 다음 다시 시도하십시오.
위치 줄:1 문자:1
+ :/commands
+ ~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (:/commands:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

PS C:\> cd C:\Commands
cd : 'C:\Commands' 경로는 존재하지 않으므로 찾을 수 없습니다.
위치 줄:1 문자:1
+ cd C:\Commands
+ ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (C:\Commands:String) [Set-Location], ItemNotFoundException
    + FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.SetLocationCommand

PS C:\> mkdir commands


    디렉터리: C:\


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:48                commands


PS C:\> ls


    디렉터리: C:\


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:48                commands
d-----      2025-11-06   오후 4:00                Develops
d-----      2019-12-07   오후 6:14                PerfLogs
d-r---      2025-10-29  오전 11:35                Program Files
d-r---      2025-09-16  오후 12:46                Program Files (x86)
d-----      2025-08-12   오후 2:22                Temp
d-r---      2025-08-11   오후 4:02                Users
d-----      2025-09-30   오전 9:32                Windows


PS C:\> cd .\commands\
PS C:\commands> mkdir Projects


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:48                Projects


PS C:\commands> ls


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:48                Projects


PS C:\commands> mkdir Logs


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:48                Logs


PS C:\commands> cd Logs
PS C:\commands\Logs> pwd

Path
----
C:\commands\Logs


PS C:\commands\Logs> cd ..
PS C:\commands> mkdir Data, Reports, Backup


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:49                Data
d-----      2025-11-06   오후 5:49                Reports
d-----      2025-11-06   오후 5:49                Backup


PS C:\commands> ;s
s : 's' 용어가 cmdlet, 함수, 스크립트 파일 또는 실행할 수 있는 프로그램 이름으로 인식되지 않습니다. 이름이 정확한지 확인하고 경로가
포함된 경우 경로가 올바른지 검증한 다음 다시 시도하십시오.
위치 줄:1 문자:2
+ ;s
+  ~
    + CategoryInfo          : ObjectNotFound: (s:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

PS C:\commands> ls


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:49                Backup
d-----      2025-11-06   오후 5:49                Data
d-----      2025-11-06   오후 5:48                Logs
d-----      2025-11-06   오후 5:48                Projects
d-----      2025-11-06   오후 5:49                Reports


PS C:\commands> cd C:\commands\Backup\
PS C:\commands\Backup> cd ..
PS C:\commands> pwd

Path
----
C:\commands


PS C:\commands> mkdir Test


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:50                Test


PS C:\commands> ls


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:49                Backup
d-----      2025-11-06   오후 5:49                Data
d-----      2025-11-06   오후 5:48                Logs
d-----      2025-11-06   오후 5:48                Projects
d-----      2025-11-06   오후 5:49                Reports
d-----      2025-11-06   오후 5:50                Test


PS C:\commands> mkdir Notes


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:50                Notes


PS C:\commands> ls


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:49                Backup
d-----      2025-11-06   오후 5:49                Data
d-----      2025-11-06   오후 5:48                Logs
d-----      2025-11-06   오후 5:50                Notes
d-----      2025-11-06   오후 5:48                Projects
d-----      2025-11-06   오후 5:49                Reports
d-----      2025-11-06   오후 5:50                Test


PS C:\commands> cd .\Notes\
PS C:\commands\Notes> pwd

Path
----
C:\commands\Notes


PS C:\commands\Notes> cd ../
PS C:\commands> mkdir Images, Videos, Docs


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:51                Images
d-----      2025-11-06   오후 5:51                Videos
d-----      2025-11-06   오후 5:51                Docs


PS C:\commands> ls


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:49                Backup
d-----      2025-11-06   오후 5:49                Data
d-----      2025-11-06   오후 5:51                Docs
d-----      2025-11-06   오후 5:51                Images
d-----      2025-11-06   오후 5:48                Logs
d-----      2025-11-06   오후 5:50                Notes
d-----      2025-11-06   오후 5:48                Projects
d-----      2025-11-06   오후 5:49                Reports
d-----      2025-11-06   오후 5:50                Test
d-----      2025-11-06   오후 5:51                Videos


PS C:\commands> cd .\Docs\
PS C:\commands\Docs> cd ../
PS C:\commands> ls


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:49                Backup
d-----      2025-11-06   오후 5:49                Data
d-----      2025-11-06   오후 5:51                Docs
d-----      2025-11-06   오후 5:51                Images
d-----      2025-11-06   오후 5:48                Logs
d-----      2025-11-06   오후 5:50                Notes
d-----      2025-11-06   오후 5:48                Projects
d-----      2025-11-06   오후 5:49                Reports
d-----      2025-11-06   오후 5:50                Test
d-----      2025-11-06   오후 5:51                Videos

```
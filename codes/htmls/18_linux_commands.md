~ $ cd C:commands
/bin/sh: cd: can't cd to C:commands: No such file or directory
~ $ pwd
/home/node
~ $ mkdir Commands
~ $ pwd
/home/node
~ $ ls -l
total 4
drwxr-sr-x    2 node     node          4096 Nov  7 03:42 Commands
~ $ cd commands
/bin/sh: cd: can't cd to commands: No such file or directory
~ $ pwd
/home/node
~ $ ls
Commands
~ $ cd -la
/bin/sh: cd: illegal option -l
~ $ ls -la
total 40
drwxr-sr-x    1 node     node          4096 Nov  7 03:42 .
drwxr-xr-x    1 root     root          4096 Aug  4 09:12 ..
-rw-------    1 node     node           105 Nov  7 03:44 .ash_history
drwxr-sr-x    4 node     node          4096 Nov  6 07:54 .cache
-rw-r--r--    1 node     node           270 Nov  7 03:40 .gitconfig
drwxr-sr-x    1 node     node          4096 Nov  7 02:45 .n8n
drwxr-sr-x    5 node     node          4096 Nov  6 07:54 .vscode-server
drwxr-sr-x    2 node     node          4096 Nov  7 03:42 Commands
~ $ pwd
/home/node
~ $ cd C:\Commands
/bin/sh: cd: can't cd to C:Commands: No such file or directory
~ $ pwd
/home/node
~ $ ls
Commands
~ $ ls -l
total 4
drwxr-sr-x    2 node     node          4096 Nov  7 03:42 Commands
~ $ ls -la
total 40
drwxr-sr-x    1 node     node          4096 Nov  7 03:42 .
drwxr-xr-x    1 root     root          4096 Aug  4 09:12 ..
-rw-------    1 node     node           144 Nov  7 03:44 .ash_history
drwxr-sr-x    4 node     node          4096 Nov  6 07:54 .cache
-rw-r--r--    1 node     node           270 Nov  7 03:40 .gitconfig
drwxr-sr-x    1 node     node          4096 Nov  7 02:45 .n8n
drwxr-sr-x    5 node     node          4096 Nov  6 07:54 .vscode-server
drwxr-sr-x    2 node     node          4096 Nov  7 03:42 Commands
~ $ mkdir Logs
~ $ cd Logs
~/Logs $ pwd
/home/node/Logs
~/Logs $ ../
/bin/sh: ../: Permission denied
~/Logs $ cd ../
~ $ cd ../
/home $ cd../
/bin/sh: cd../: not found
/home $ cd Commands
/bin/sh: cd: can't cd to Commands: No such file or directory
/home $ cd node
~ $ cd Commands
~/Commands $ pwd
/home/node/Commands
~/Commands $ mkdir Projects
~/Commands $ ls
Projects
~/Commands $ pwd
/home/node/Commands
~/Commands $ mkdir Logs
~/Commands $ cd logs
/bin/sh: cd: can't cd to logs: No such file or directory
~/Commands $ cd logs
/bin/sh: cd: can't cd to logs: No such file or directory
~/Commands $ ls -la
total 20
drwxr-sr-x    4 node     node          4096 Nov  7 03:47 .
drwxr-sr-x    1 node     node          4096 Nov  7 03:45 ..
drwxr-sr-x    2 node     node          4096 Nov  7 03:47 Logs
drwxr-sr-x    2 node     node          4096 Nov  7 03:46 Projects
~/Commands $ cd Logs
~/Commands/Logs $ pwd
/home/node/Commands/Logs
~/Commands/Logs $ cd ../
~/Commands $ mkdir Data, Reports, Backup
~/Commands $ ls
Backup    Data,     Logs      Projects  Reports,
~/Commands $ ls -la
total 32
drwxr-sr-x    7 node     node          4096 Nov  7 03:47 .
drwxr-sr-x    1 node     node          4096 Nov  7 03:45 ..
drwxr-sr-x    2 node     node          4096 Nov  7 03:47 Backup
drwxr-sr-x    2 node     node          4096 Nov  7 03:47 Data,
drwxr-sr-x    2 node     node          4096 Nov  7 03:47 Logs
drwxr-sr-x    2 node     node          4096 Nov  7 03:46 Projects
drwxr-sr-x    2 node     node          4096 Nov  7 03:47 Reports,
~/Commands $ cd Backup
~/Commands/Backup $ ls
~/Commands/Backup $ ls la
ls: la: No such file or directory
~/Commands/Backup $ ls -la
total 8
drwxr-sr-x    2 node     node          4096 Nov  7 03:47 .
drwxr-sr-x    7 node     node          4096 Nov  7 03:47 ..
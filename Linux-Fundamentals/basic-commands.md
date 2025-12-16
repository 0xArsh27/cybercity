# Linux Basic Commands

## User and System Information
`whoami` – Displays the currently logged-in user  
`id` – Shows user ID, group ID, and group memberships  
`hostname` – Displays the system hostname  

## File and Directory Management
`pwd` – Prints the current working directory  
`ls` – Lists files and directories  
`ls -la` – Lists all files including hidden ones with permissions  
`cd` – Changes the current directory  
`cd ..` – Moves to the parent directory  

`touch file` – Creates an empty file  
`mkdir dir` – Creates a directory  
`rm file` – Deletes a file  
`rm -r dir` – Deletes a directory recursively  
`cp src dst` – Copies a file or directory  
`mv src dst` – Moves or renames a file or directory  

## Viewing File Contents
`cat file` – Displays file contents  
`less file` – Views file contents page by page  
`head file` – Displays the first 10 lines of a file  
`tail file` – Displays the last 10 lines of a file  
`tail -f file` – Monitors a file in real time  

## System Monitoring
`uname -a` – Displays kernel and system information  
`uptime` – Shows how long the system has been running  
`df -h` – Displays disk usage in human-readable format  
`free -h` – Displays memory usage  

## Process Management
`ps aux` – Lists all running processes  
`top` – Shows real-time process usage  
`kill PID` – Terminates a process by process ID  

## Permissions and Ownership
`chmod` – Changes file permissions  
`chown` – Changes file owner and group  
`stat file` – Displays detailed file metadata  

## Searching and Finding
`grep 'pattern' file` – Searches for 'pattern' in the file  
`find /path -name 'filename'` – Searches for 'filename' in the specified path  
`which cmd` – Shows the full path of a command  

## Networking
`ip a` – Displays network interfaces  
`ip r` – Displays the routing table  
`ss -tuln` – Lists listening network ports  
`ping host` – Tests network connectivity  

## Miscellaneous
`history` – Displays command history  
`man cmd` – Opens the manual page for a command  
`cmd --help` – Displays help for a command  
`clear` – Clears the terminal screen

# What is kernel? 
A kernel is the core of OS, that interacts with the hardware in your computer.

# How to know the kernel version ?
`uname -r`
# what is difference between grep -i and grep -v?
- -i: case insensitive
- -v: gives search results, which doesn't match the pattern

# what is sudo?
through which a user can provided root access.

# How to list the IP address ?
`ip a`
`ifconfig -a`

## how to list only IPV4/V6 addresses ?
## How to list a particular ethernet interface ?
# How to check disk free space ?
`df -ah`
```
-a  - all fs
-h  -  Human readablee
```

## How to check the directory size
`du -sh <folder>`

## List all files and directories
`du -ash`

# How to know the service status
`service <service_name> status`
`systemctl status <service_name>`

# How to check open ports

# What are the checks to be done when a Linux build server become slow suddenly? 
Perform a check on the following items: 
1. System Level Troubleshooting: 
    You need to make checks on various factors like application server log file, WebLogic logs, Web Server Log, Application Log file, HTTP to find if there are any issues in server receive or response time for deliberateness. Check for any memory leakage of applications. 
2. Application Level Troubleshooting: Perform a check on Disk space, RAM and I/O read-write issues. 
3. Dependent Services Troubleshooting: Check if there is any issues on Network, Antivirus, Firewall, and SMTP server response time.

# Soft link and hard link 
# Super block in file system
super block contains information about the file system
used data blocks
no of free inodes

# What are the various stages of a linux process ?
- waiting - In this process, job waits for resources
- running - job is being executed
- stopped - Job is either successfully executed or stopped by user
- zombie - It is know as zombie, because the process has stopped but still active in process table.


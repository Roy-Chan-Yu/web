## Linux Commands

## ls

###  represented by a forward slash (/) 

```bash
ls /
```

### used to display only subdirectories.
```bash
ls -d */
```

### print the list in reverse order.

```bash
ls -r
```

---

```bash
ls -R
```

## Linux Copy File

```bash
cp <existing file name> <new file name>  
```

- cp:omitting directory 因为dir目录下存在其他目录或文件存在，不可只使用cp命令实现复制操作

```bash
cp -r<existing file folder> <new file folder>
```

## Move File(Rename File)

```bash
mv dir tmp
```

## Rename option

```bash
rename 's/old-name/new-name/' files  
```

## File Content


## head default 10
```bash
head <file name> <file name>  
```

##  head -n
- display the specified number of lines.

```bash
head -n <file name>
```

## tail

-  display the last ten lines of one or more files.//default 10

```bash
tail -n <number> <file name>  
```

## tac command
- cat -reverse
```bash
tac fileName 
```

## more command

- Enter key: To scroll down page line by line.
- Space bar: To go to next page.
- b key: To go to the backward page.
- `/ key`: Lets you `search the string`.

## Ping command
- the ping used to `check the connection between two nodes`.

```bash
ping <destination> 
```

## Host command
- It performs the DNS lookup for DNS Query.

## Su command
- allows you to run a shell as another user.
- Default su - Root
```bash
su - $username
```

### sudo su -
- By default, some <font color="red">Linux systems like `Ubuntu`, don't have a password set for root user</font>. It means you `can't login as root user`.
- sudo su - a user can become root user `without typing password for root`.

## groupadd  
- execute the groupadd command.

```bash
sudo groupadd jtpGroup 
```

## add a user to a Group

```bash
sudo useradd user1
```

## check the user-group ID on machine

```bash
id
```

---
# stdio

## Cat command

```bash
cat <fileName>
```

## stdio

- '>' overwrite the file
- '>>' do not overwrite the file
```bash
ls *.txt | cat > txtFile  
```

## Tr command

- stands for 'translate'

```bash
cat file | tr <'old'> <'new'>  
```


## Find command
- helps us to find a `particular file within a directory`.

```bash
find <location> <comparison-criteria> <search-term>  
```

- `.` : For current directory name
- `/` : For the root directory

###　Find files by name
```bash
find . -name "*.txt"   
```
### Find files by type
- f: regular file
- d: directory
- l: symbolic links
- c: character devices
- b: block devices

```bash
find . -type d -name "*.bak"    
```

### Find files by modification time
- files and folder

```bash
find ./Newdirectory -mtime -1  
```

### Find text within multiple files
- We can `make another combination of the find command with the grep command` to find the text from the various files

- 搜尋並刪除所有大過 100MB 的檔案
```bash
find /path/to -size +100M -exec /bin/rm {} \;
```

## df command
- Disk space used in the file system. `df stands for "disk filesystem`.
- Human-readable
```bash
df -h
```

## File Permissions
---

## charp command

```bash
sudo chgrp -R javatpoint
```

## chmod command

```bash
chmod u+x file  
```

## chown command

```bash
sudo chown <username> <File name>  
```

## Symbolic Links
- Symbolic links are also called `soft-links`.

```bash
ln -s xyz symlink_to_xyz 
```

## Network Command

## find Command

```bash
find ./ -type f -name '*.md'
```

## Find directory

```bash
find ./Newdirectory -mtime -1
```

## 檔案大小大於100M

```bash
sudo find / -type f -size +100M -exec ls -lh {} \; | awk '{ printf("%-100s \t %s\n", $9, $5) }'
```

## 查找三天內有異動的檔案

```bash
find ./ -mtime -7
```

> -mtime 搜尋檔案的修改時間(天),<br> -mmin 搜尋檔案的修改時間(分鐘),<br> -ctime 搜尋檔案的建立時間(天),<br> -cmin 搜尋檔案的建立時間(分鐘),<br> -atime 搜尋檔案的最後開啟時間(天),<br> -amin 搜尋檔案的最後開啟時間(分鐘)

## disk space

```bash
df -h
```

## softlink

- 使用絕對路徑

```bash
sudo ln -s /請改為jboss的路徑/jboss-as-7.2.0.Final /usr/share/jboss-as
```

- 使用相對路徑

```bash
ln -s sourcePath
```

- 移除連結

```bash
rm -f lnFile
```

## netWork

- Maintaining a system's network is a task of System/Network administrator. Their task `includes network configuration and troubleshooting`.

## Networking and troubleShooting command

## ifconfig

- It display route and network interface.

## traceroute

- "*" means the loss of the packet.

```bash
traceroute javapoint.com
```

## PING

- DNS , IP

```bash
ping <destination>
```

## netstat command

---

- system administrators
- displays all the socket connections (including `TCP, UDP`)
- display the pending for connections.

netstat -a All connections
netstat -at TCP or UDP connections
netstat -au only UDP connections.
netstat -ant

## 查找CLOSE_WAIT 數

### 查找CLOSE_WAIT 數量

```bash
netstat -n | awk '/^tcp/ {++S[$NF]} END {for(a in S) print a, S[a]}'
```

### 查看CLOSE_WAIT的IP:PORT

```bash
netstat -tulnap | grep CLOSE_WAIT | | sed -e 's/::ffff://g' | awk '{print $4,$5}' | sed 's/:/ /g'
```

## CLOSE_WAIT

```bash
netstat -tnpa | grep CLOSE_WAIT
```

## nslookup

- used to find`DNS related query`.

```bash
nslookup javatpoint.com
```

## host

- It also performs DNS lookups related to the DNS query.
- host command's `default behavior displays a summary of its command-line arguments` and supported options.

```bash
host www.google.com
```

## Curl & Wget(重要)

- These commands are used to `download a file from the internet using CLI`.
- Without opion, the file will be saved in `the current directory`.

```bash
curl -O<fileLink>
```

- used to `download or upload data to a server via supported protocols` such as HTTP, FTP, IMAP, SFTP, TFTP, IMAP, POP3, SCP, etc.

- is a `remote utility, so it works without user interaction`.

## curl版

```bash
curl --version
```

```bash
curl [options][URL...]
```

## Download the content

```bash
curl -o /home/javatpoint/Documents/linux.html https://www.javatpoint.com/linux-tutorial  
```

## Download the file

```bash
curl -o /home/javatpoint/Documents/ubuntu20.04.iso https://ubuntu.com/download/desktop/thank-you?version=20.04&architecture=amd64  
```

## Curl HTTP Headers

```bash
curl -I www.javatpoint.com
```

## wget commands

|Option |Function|
|-------|--------|
|wget <URL>|Download single file|
|wget -O <fileName> <URL>|Store with a different file name|
|wget --limit-rate=<Numberk> <URL>|Specify download rate/speed|
|wget -o <logFile> <URL>|Redirect downloading file to the log file|

## PS commands

- The ps command is used to view currently running processes on the system.

|Option |Function|
|-------|--------|
|ps -ef/ ps -aux|List currently running process in full format|
|ps -ax |List currently running process|
|ps -u <username>|List process for specific user|
|ps -p <PID>|List process with given PID|
|ps --sort pmem|Find memory leak|
|ps -U root -u root u|Show process running by root|

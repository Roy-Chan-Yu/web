## System Admin Command

- handles servers, has to manage system `performance and security without exceeding the budget` 預算 to meet users need.

## Linux Service

- starts, stop and restart a daemon or services by calling the script. are stored in `/etc/init.d directory`.

- start command

```bash
service service_name start
service service_name restart
service service_name stop
service service_name status
```

## Linux Kill

- terminate a process,u need the PID of the process.
- kill command sends signal to the specified process

```bash
kill -SIGNAL PID  
```

|Signal Name|Signal Number|Signal Use                |
|-----------|-------------|--------------------------|
|SIGNULL    |0            |NULL, check access to PID |
|SIGHUP     |1            |Hangup                    |
|SIGINT     |2            |Interrupt                 |
|SIGQUIT    |3            |Quit                      |
|SIGKILL    |9            |Kill                      |
|SIGTERM    |15           |Terminate                 |
|SIGSTOP    |24           |Stop                      |
|SIGTSTP    |25           |Stop/pause the process    |
|SIGCONT    |26           |Continue a stopped process|

## 刪除進程(by Name)

```bash
ps aux | grep qemu | awk '{print $2}'|xargs kill -9

kill -9 `ps aux | grep 'jboss-5.1.0.GA_gscmpurd' | awk '{ print $2 }' ` > /dev/null
```

## 刪除進程(by port)

```bash
kill -9 $(lsof -t -i:443)
kill -9 $(lsof -t -i:3000 -sTCP:LISTEN)
```

## Shutdown & reboot

```bash
shutdown -r
```

```bash
Reboot
```

## Disk Usage

```bash
du -h
```

## Linux mount
-  `attaches the filesystem` of an `external device to the filesystem` of a system
-  mounts the external storage devices like `hard disks, pen drives, USBs` etc...
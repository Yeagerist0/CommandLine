# Question 4: System Monitoring

## 1. System Uptime Verification
**Command:**
```bash
uptime -p
```
**Output:**
```
up 10 hours, 3 minutes
```
**Explanation:**
`uptime -p` displays the system uptime in a pretty, human-readable format.

## 2. User Process Listing
**Command:**
```bash
ps -u $(whoami)
```
**Output:**
```
    PID TTY          TIME CMD
   1716 ?        00:00:00 systemd
   ...
```
**Explanation:**
`ps -u $(whoami)` lists all processes running under the current user's account.

## 3. CPU Usage Analysis
**Command:**
```bash
top -b -n 1 -u $(whoami) | head -n 12
```
**Output:**
```
    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
  73463 hitarth   20   0 5706700   1.1g  60984 S  36.4   7.1  30:56.71 stremio
```
**Explanation:**
`top` displays real-time system information. The output shows that `stremio` is currently consuming the highest CPU (36.4%) among the user's processes.

## 4. Background Process Execution
**Command:**
```bash
sleep 300 &
```
**Output:**
```
[1] 103371
```
**Explanation:**
The `&` operator runs the `sleep 300` command in the background, returning the job ID and PID immediately.

## 5. Process Priority Management
**Command:**
```bash
renice +10 -p 103371
```
**Output:**
```
103371 (process ID) old priority 5, new priority 10
```
**Explanation:**
`renice` changes the priority of a running process. We increased the niceness value to 10, making the process lower priority.

## 6. Memory Usage Monitoring
**Command:**
```bash
free -h
```
**Output:**
```
               total        used        free      shared  buff/cache   available
Mem:            14Gi        10Gi       444Mi       123Mi       4.8Gi       4.8Gi
```
**Explanation:**
`free -h` displays the total, used, and free memory in a human-readable format (GiB/MiB).

## 7. Disk Space Inspection
**Command:**
```bash
df -h ~
```
**Output:**
```
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p8  233G  110G  112G  50% /
```
**Explanation:**
`df -h ~` shows the disk space usage for the file system containing the home directory.

## 8. Shell Identification
**Command:**
```bash
echo $SHELL
```
**Output:**
```
/usr/bin/zsh
```
**Explanation:**
The `$SHELL` environment variable stores the path to the current user's default shell.

## 9. Output Redirection
**Command:**
```bash
uname -a > system_report.txt
```
**Explanation:**
The output of `uname -a` (system information) is redirected to the file `system_report.txt`.

## 10. Disk Usage Visualization
**Command:**
```bash
ncdu
```
**Output:**
```
ncdu not found
```
**Explanation:**
`ncdu` (NCurses Disk Usage) is a disk usage analyzer with an ncurses interface. It provides a navigable, visual representation of directory sizes. It was not installed on this system, but typically it allows you to browse directories and see which ones consume the most space.

# Question 1: Environment Verification

## 1. User Identity Verification
**Command:**
```bash
id
```
**Output:**
```
uid=1000(hitarth) gid=1000(hitarth) groups=1000(hitarth),4(adm),20(dialout),24(cdrom),25(floppy),27(sudo),29(audio),30(dip),44(video),46(plugdev),100(users),101(netdev),103(scanner),116(bluetooth),121(lpadmin),124(wireshark),133(kaboxer),985(ollama)
```
**Explanation:**
The `id` command displays the current user's ID (uid), group ID (gid), and the groups the user belongs to. In this case, the user is `hitarth` and belongs to groups like `sudo`, `adm`, etc.

## 2. Workspace Validation
**Command:**
```bash
pwd && ls -l
```
**Output:**
```
/home/hitarth/Commandline/Question_1
total 4
-rw-rw-r-- 1 hitarth hitarth 115 Jan  2 20:06 log.txt
```
**Explanation:**
`pwd` shows the current working directory, which is `/home/hitarth/Commandline/Question_1`. `ls -l` lists the files in the directory in long format, showing permissions, owner, size, and modification date.

## 3. Environment Confirmation File
**Command:**
```bash
echo "Linux user environment verified" > user_info.txt
```
**Output:**
(No output on success)
**Explanation:**
The `echo` command prints the string "Linux user environment verified", and the `>` operator redirects this output to a new file named `user_info.txt`.

## 4. File Integrity Check
**Command:**
```bash
wc -c user_info.txt
```
**Output:**
```
32 user_info.txt
```
**Explanation:**
The `wc -c` command counts the number of bytes (characters) in the file `user_info.txt`. It shows 32 characters.

## 5. Learning the Tools
**Command:**
```bash
man mkdir
```
**Explanation:**
The `man mkdir` command opens the manual page for the `mkdir` command. One useful option is `-p` (parents), which allows creating parent directories as needed (e.g., `mkdir -p a/b/c` creates `a`, `b`, and `c` if they don't exist).

## 6. Home Directory Inspection
**Command:**
```bash
ls -l ~ | sort
```
**Output:**
```
-rw-r--r--  1 hitarth hitarth       1722 Jan  1 23:20 ffuf_permissions.json
-rw-rw-r--  1 hitarth hitarth          0 Dec 16 18:42 page_source.html
... (truncated)
```
**Explanation:**
`ls -l ~` lists the contents of the home directory in long format. The `| sort` pipe sends this output to the `sort` command, which sorts the lines alphabetically.

## 7. Log Investigation
**Command:**
```bash
grep "admin" log.txt
```
**Output:**
```
User admin logged in.
Error: admin permission denied.
```
**Explanation:**
The `grep` command searches for the string "admin" inside `log.txt` and prints only the matching lines.

## 8. System Information Check
**Command:**
```bash
uname -r
```
**Output:**
```
6.12.38+kali-amd64
```
**Explanation:**
The `uname -r` command displays the release version of the Linux kernel currently running.

## 9. Network Connectivity Test
**Command:**
```bash
ping -c 4 www.google.com
```
**Output:**
```
PING www.google.com (142.250.67.164) 56(84) bytes of data.
64 bytes from bom12s07-in-f4.1e100.net (142.250.67.164): icmp_seq=1 ttl=118 time=27.5 ms
...
--- www.google.com ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3004ms
```
**Explanation:**
The `ping` command sends ICMP ECHO_REQUEST packets to the target host. The `-c 4` option limits it to 4 packets. The output confirms connectivity with 0% packet loss.

## 10. System Health Awareness
**Command:**
```bash
uptime
```
**Output:**
```
 20:07:02 up 10:02,  1 user,  load average: 2.14, 1.81, 1.39
```
**Explanation:**
The `uptime` command shows the current time, how long the system has been running (10 hours, 2 minutes), the number of logged-in users, and the system load averages for the past 1, 5, and 15 minutes.

# Question 3: Links and Disk Usage

## 1. File Creation
**Command:**
```bash
touch sample_data.txt && echo "Sample Data" > sample_data.txt
```
**Explanation:**
Created a file `sample_data.txt` and added some text to it.

## 2. Hard Link Creation
**Command:**
```bash
ln sample_data.txt sample_hard.txt
```
**Explanation:**
`ln` creates a hard link named `sample_hard.txt` pointing to the same inode as `sample_data.txt`.

## 3. Symbolic Link Creation
**Command:**
```bash
ln -s sample_data.txt sample_soft.txt
```
**Explanation:**
`ln -s` creates a symbolic (soft) link named `sample_soft.txt` that points to the path of `sample_data.txt`.

## 4. Inode Verification
**Command:**
```bash
ls -i sample_data.txt sample_hard.txt sample_soft.txt
```
**Output:**
```
11149062 sample_data.txt  11149062 sample_hard.txt  11149063 sample_soft.txt
```
**Explanation:**
`ls -i` displays the inode numbers. `sample_data.txt` and `sample_hard.txt` share the same inode (11149062), while `sample_soft.txt` has a different inode (11149063).

## 5. Inode Analysis
**Explanation:**
`sample_data.txt` and `sample_hard.txt` share the same inode because a hard link is just another name for the same file data on the disk. `sample_soft.txt` is a separate file that contains a reference to the original file, so it has a different inode.

## 6. File Metadata Inspection
**Command:**
```bash
ls -l sample_data.txt
```
**Output:**
```
-rw-rw-r-- 2 hitarth hitarth 12 Jan  2 20:07 sample_data.txt
```
**Explanation:**
`ls -l` shows metadata. The link count is 2 (original + hard link).

## 7. Disk Usage Check
**Command:**
```bash
du -h .
```
**Output:**
```
8.0K    .
```
**Explanation:**
`du -h` displays the disk usage of the current directory in human-readable format.

## 8. File Size Overview
**Command:**
```bash
ls -lh
```
**Output:**
```
total 8.0K
-rw-rw-r-- 2 hitarth hitarth 12 Jan  2 20:07 sample_data.txt
-rw-rw-r-- 2 hitarth hitarth 12 Jan  2 20:07 sample_hard.txt
lrwxrwxrwx 1 hitarth hitarth 15 Jan  2 20:07 sample_soft.txt -> sample_data.txt
```
**Explanation:**
`ls -lh` lists files with sizes in human-readable format. The soft link is very small (15 bytes) as it only stores the path.

## 9. Link Deletion Test
**Command:**
```bash
rm sample_soft.txt && ls -l sample_data.txt
```
**Output:**
```
-rw-rw-r-- 2 hitarth hitarth 12 Jan  2 20:07 sample_data.txt
```
**Explanation:**
Deleting the soft link does not affect the original file. The link count remains 2 because the hard link still exists.

## 10. Disk Utility Demonstration
**Command:**
```bash
du -h . && df -h .
```
**Output:**
```
8.0K    .
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p8  233G  110G  112G  50% /
```
**Explanation:**
`du` estimates file space usage (directory size), while `df` reports file system disk space usage (total, used, available on the partition).

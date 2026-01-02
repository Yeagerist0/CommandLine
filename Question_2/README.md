# Question 2: File and Directory Management

## 1. Project Workspace Setup
**Command:**
```bash
mkdir documents
```
**Explanation:**
The `mkdir` command creates a new directory named `documents`.

## 2. File Creation
**Command:**
```bash
cd documents && touch plan.txt
```
**Explanation:**
`cd` changes the current directory to `documents`, and `touch` creates an empty file named `plan.txt`.

## 3. Content Addition
**Command:**
```bash
echo "Project Plan: Complete Lab" > plan.txt
```
**Explanation:**
`echo` writes the text "Project Plan: Complete Lab" and `>` redirects it into `plan.txt`, overwriting any existing content.

## 4. File Metadata Verification
**Command:**
```bash
ls -l plan.txt
```
**Output:**
```
-rw-rw-r-- 1 hitarth hitarth 27 Jan  2 20:07 plan.txt
```
**Explanation:**
`ls -l` displays the file metadata. It shows that the file is owned by `hitarth` and has read/write permissions for the owner.

## 5. File Duplication
**Command:**
```bash
cp plan.txt plan_copy.txt
```
**Explanation:**
The `cp` command creates a copy of `plan.txt` named `plan_copy.txt` in the same directory.

## 6. Directory Renaming
**Command:**
```bash
cd .. && mv documents project_documents
```
**Explanation:**
`cd ..` moves back to the parent directory. `mv` renames the `documents` directory to `project_documents`.

## 7. Archival Structure
**Command:**
```bash
mkdir project_documents/archive
```
**Explanation:**
`mkdir` creates a subdirectory named `archive` inside `project_documents`.

## 8. File Organization
**Command:**
```bash
mv project_documents/plan_copy.txt project_documents/archive/
```
**Explanation:**
The `mv` command moves the file `plan_copy.txt` from `project_documents` to the `archive` subdirectory.

## 9. Recursive Listing
**Command:**
```bash
ls -R project_documents
```
**Output:**
```
project_documents:
archive  plan.txt

project_documents/archive:
plan_copy.txt
```
**Explanation:**
`ls -R` lists the contents of the directory and all its subdirectories recursively, showing the full structure.

## 10. Path Verification
**Command:**
```bash
readlink -f project_documents/archive/plan_copy.txt
```
**Output:**
```
/home/hitarth/Commandline/Question_2/project_documents/archive/plan_copy.txt
```
**Explanation:**
`readlink -f` displays the canonical absolute path of the file, confirming its new location.

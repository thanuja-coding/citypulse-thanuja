# Atria-CityPulse

This repository documents basic Linux command-line tasks and includes screenshots of the commands being run in the terminal.

## Task 1: Remove Directories

Use `mkdir` to create a directory and `rmdir` to remove an empty directory.

```bash
mkdir temp-dir
ls
rmdir temp-dir
ls
```

`rmdir` only works when the directory is empty. Use `rm -r` or `rm -rf` to remove directories that contain files or subdirectories.

![Removing an empty directory](images/task1.png)

## Task 2: Remove Files and Directories Recursively

Use `rm` to remove a file and `rm -r` or `rm -rf` to remove a directory and everything inside it.

```bash
# Remove a file
touch filename.txt
rm filename.txt

# Remove a directory and all its contents
mkdir folder-name
touch folder-name/file1.txt
rm -r folder-name

# Remove a directory and its contents without prompting
mkdir folder-name
touch folder-name/file1.txt
rm -rf folder-name
```

> Warning: `rm -rf` permanently deletes data. Double-check the path before running it.

![Removing files and directories](images/task2.png)

## Task 3: Rename Files and Check Disk Usage

### Rename a File or Directory

The `mv` command renames a file or directory:

```bash
mv old-name.txt new-name.txt
mv old-folder-name new-folder-name
```

To move a file into a folder:

```bash
mv filename.txt folder/filename.txt
```

![Renaming files and folders](images/task3-rename.png)

### Check Disk Usage

Use `df -h` to see the disk space available on mounted filesystems:

```bash
df -h
```

Use `du -h` to show the size of files and directories:

```bash
# Show the size of the current directory and its subfolders
du -h

# Show only the total size of the current directory
du -sh

# Show the size of a specific folder
du -sh images
```

![Checking disk usage](images/task3-disk.png)

## Task 4: Linux Permissions

Linux files and directories have three permission types:

| Permission | Symbol | Meaning |
| --- | --- | --- |
| Read | `r` | View file contents or list directory contents |
| Write | `w` | Modify a file or change directory contents |
| Execute | `x` | Run a file as a program or enter a directory |

Permissions are assigned to:

- The file owner
- The owner's group
- Other users

Use `chmod` to change permissions:

```bash
# Add execute permission for the owner
chmod u+x script.sh

# Give the owner read and write permissions
chmod u+rw file.txt

# Make a file readable and writable by everyone
chmod 666 file.txt

# Give the owner full permissions and others read/execute permissions
chmod 755 script.sh
```

View permissions with:

```bash
ls -l
```

Example permission modes:

- `644`: owner can read/write; group and others can read
- `755`: owner can read/write/execute; group and others can read/execute
- `777`: all users have read, write, and execute permissions

![Changing file permissions](images/task4.png)

## Task 5: List Running Processes

Use `ps` to view processes for the current terminal:

```bash
ps
```

Use `ps aux` to list processes from the entire system:

```bash
ps aux
```

To search for a specific process:

```bash
ps aux | grep process-name
```

An alternative, interactive process viewer is:

```bash
top
```

Press `q` to exit `top`.

![Listing running processes](images/task5.png)

## Screenshot Summary

| Screenshot | Description |
| --- | --- |
| `images/task1.png` | Creating and removing an empty directory |
| `images/task2.png` | Removing files and directories recursively |
| `images/task3-rename.png` | Renaming files and folders |
| `images/task3-disk.png` | Checking disk usage |
| `images/task4.png` | Changing file permissions |
| `images/task5.png` | Listing running processes |
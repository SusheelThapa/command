# `ls`

## Description

`ls` is a standard Unix utility that lists the files in the directory specified in the path. By default it lists the files in the current directory. It is similar to `dir` command in Windows.

It can be modified with flags to further improve its functionality.

The command syntax is:

```shellv
ls [flags] [path to directory]
```

---

## Flags

Some of the popular flags that are used with `ls` command are as follows:

- [`-a` or `--all`](#a): lists hidden items
- [`-l`](#l): display more information about the items.
- [`--help`](#help): get more information about the command and uncommon flags. 

### `-a`

**Description:**

With the `-a` option, the `ls` command will show hidden files and sub-folders. By defaultfiles and folders beginning with `.` are hidden and they are not listed when doing a typical `ls` command

**Usage:**
Consider we are inside a folder that contains three files: `file1.txt`, `file2.txt` and a hidden file `.file.txt`. If we want to see the hidden file we need to use the `-a` flag as:

```shell
ls -a
```

_Output:_

```
.file.txt  file1.txt  file2.txt
```

### `-l`

**Description:**

With the `-l` flag, the `ls` command will list the files in the current directory in a detailed, long-form format.

**Usage:**
Taking the example from above we can enter the following into the terminal
```shell
ls -l
```

_Output:_

```shell
-rw-r--r-- 1 username groupname 1024 Nov  5 12:40 file1.txt
-rw-r--r-- 1 username groupname 1024 Nov  5 12:40 file2.txt
```

Let's interpret the first line of output to better understand the flag.

* `-rw-r--r--`: This represents the file permissions and file type. It indicates that file1.txt is a regular file (- indicates a regular file, d would indicate a directory). The rw-r--r-- part represents the permissions for the file (read, write for the owner, read for the group, and read for others).

* `1`: This shows the number of hard links to the file or directory. In this case, it's 1.

* `username`: This is the owner of the file.

* `groupname`: This is the group associated with the file.

* `1024`: This is the file size in bytes.

* `Nov 5 12:40`: These are the date and time of last modification.

* `file1.txt`: This is the name of the file.

### `--help`

**Description:**

With the `--help` option, the `ls` command will show other flags and options for the command that are not commonly used.

**Usage:**

```shell
ls --help
```

## Additional Information

As seen in example 1, the flags can be combined. This is common for all commands in linux that do not take a parameter after the flag.  Hence the `-l` and `-a` flag can be combined to `-la` flag.

## Exercises

1. Use the `--help` flag and find the flag to    recursively list the items in a folder.

2. Navigate to the `/usr/bin` directory and find out the tools installed in your system.

3. Find the number of pictures in your system. Hint: `wc` command prints the number of newline, words and bytes for each file.

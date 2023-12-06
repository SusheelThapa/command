# `chown`

## Description

`chown` stands for change owner which changes user or group ownership of a file, directory, or symbolic link. Every file or directory has group or user ownership in Linux. Since multiple users and groups can use same Linux system, they all have unique names and IDs. Name and ID of a user and a group can be same.

For displaying the owner of any file or folder, one can use 

```shell
ls -l [file or folder name]
```

Example: 

```shell
ls -l test.txt 
```

_Output:_
```shell
-rw-rw-r-- 1 sasa sasa 0 Dec  3 21:42 test.txt
```

In above output section, first `sasa` denotes user and second `sasa` denotes its group.

You can also check the ownership of any folder. Suppose you are in folder which contains `test_folder` which you can check by using `ls` command then type command below to see ownership of your `test_folder`.

Examples: 

```shell
ls -l 
```

_Output:_
```shell
drwxrwxr-x  2 sasa sasa    4096 Dec  3 21:42  test_folder
```

### 1. Changing ownership of file to another user.

First, checking the ownership of file from the command below:

```shell
ls -l test.txt
```

Suppose output is:

```shell
-rw-rw-r-- 1 sasa sasa 0 Dec  3 21:42 test.txt
```

Now, suppose I want to change it to the user `root` from the user `sasa`; this can be done using the command below:

```shell
sudo chown root test.txt
```

_Output:_
```shell
-rw-rw-r-- 1 root sasa 0 Dec  3 21:42 test.txt

```

In above output section, ownership changed to user `root` from user `sasa`. Group `sasa` still has ownership. 

##### _Note:_

You can also use owner `user_id` in place of owner to change ownership in above example like: 
    
```shell
id -u user_name
```

Suppose, output is 1000.
Now, you can replace `user_name` with its `user_id`. 
Example: In place of `sudo chown user_name test.txt`, you can use the command below:

```shell
sudo chown 1000 test.txt
```

##### _Another Note:_

For changing ownership of folder, you can do it similarly like:

```shell
sudo chown root test_folder
```

It gives ownership of test_folder to `root` user.

### 2. Changing the group of a file. 

First, checking the ownership of file from the command below:

```shell
ls -l test.txt
```
Suppose output is:

```shell
-rw-rw-r-- 1 sasa sasa 0 Dec  3 21:42 test.txt
```

Now, suppose I want to change it to group `root` then it can be done by command below: 

```shell
sudo chown :root test.txt
```

_Output:_
```shell
-rw-rw-r-- 1 root root 0 Dec  3 21:42 test.txt
```

Group of file `test.txt` changed from `sasa` to `root`.

##### _Note:_

You can also use owner `group_id` in place of `group` to change ownership in above example like: 
    
```shell
id -g group_name
```
Example: 

```shell
id -g root
```
Suppose, output is 0.

Now, you can replace `group_name` with its `group_id`. 

Example:
 
In place of `sudo chown group_name test.txt`, you can use the command below:

```shell
sudo chown :0 test.txt
```

### 3. Changing both file ownership and group at once. 

First checking the ownership of file from the command below:

```shell
ls -l test.txt
```

Suppose output is:

```shell
-rw-rw-r-- 1 root root 0 Dec  3 21:42 test.txt
```

Now, suppose I want to change it to user `sasa` and group `sasa` then it can be done by the command below:

```shell
sudo chown sasa:sasa test.txt
```

_Output:_
```shell
-rw-rw-r-- 1 sasa sasa 0 Dec  3 21:42 test.txt
```

Ownership changed to user `sasa` and  group `sasa`.

### 4. Changing owner of multiple files 

You can use different files with space in between them to change ownership of multiple files at once. 

```shell
sudo chown owner_name file1 file2 file3 
```

### 5. Copying owner and group of file to another file. 

Syntax: 
```shell
sudo chown --reference=source_file destination_file
```

## Flags
-   [`--reference`](#reference)
-   [`-v, --verbose`](#verbose)
-   [`-c, --changes`](#changes)
-   [`-R, --recursive`](#recursive)
-   [`--from=CURRENT_OWNER:CURRENT_GROUP`](#from)


<div id="reference"></div>

### --reference

**Description:** 

`--reference=RFILE`: Reference a file to use its owner and group for another file (use `RFILE`'s owner and group rather than specifying `OWNER:GROUP` values)

**Usage:** 

```shell
sudo chown --reference=reference_file target_file
```

<div id="verbose"></div>

### -v, --verbose

**Description:** 

Verbose, its prints what action has happened when used.

**Usage:** 

```shell
sudo chown -v new_owner:new_group target_file
```

<div id="changes"></div>

### -c, --changes

**Description:** 

Like verbose but report only when a change is made.

**Usage:**
 
```shell
sudo chown -c new_owner:new_group target_file
```

<div id="recursive"></div>

### -R, --recursive

**Description:** 

Operates in files and directory recursively.

**Usage:** 

```shell
sudo chown -R new_owner:new_group target_directory
```

<div id="from"></div>

### --from=CURRENT_OWNER:CURRENT_GROUP

**Description:** 

Change the owner and/or group of each file only if its current owner and/or group match those  specified  here. Either may be omitted, in which case a match is not required for the omitted attribute

**Usage:** 

```shell
sudo chown --from=current_owner:current_group new_owner:new_group target_file
```

## Use Case
Imagine you're managing a shared project on a Linux server, and a team member has recently left the project, leaving behind some crucial files in their home directory. To ensure continued access and collaboration, you need to transfer ownership of the files to a new team member. Using the `chown` command, you can swiftly change the ownership of the entire directory, including its subdirectories and files, to the new team member's user and group, ensuring seamless collaboration without any disruption in accessing or modifying the project files. The command would look something like this: 

```shell
sudo chown -R new_user:new_group /home/old_user/project.
```


## Exercises

####  Exercise 1: Change Ownership of a File

You have a file named `important_document.txt` in your home directory, and you want to change its ownership to a user named `secure_user` and a group named `restricted_group`. Use the `chown` command to accomplish this task.

####  Exercise 2: Recursively Change Ownership of a Directory

You have a directory named `project_files` in your home directory, and it contains multiple subdirectories and files. You want to change the ownership of the entire directory and its contents to a user named `project_owner` and a group named `project_group`. Use the `chown` command with the recursive flag to achieve this.

####  Exercise 3: Copy Ownership from a Reference Directory

You have two directories, `source_directory` and `destination_directory`. You want to set the ownership of the `destination_directory` to match that of the `source_directory`. Use the `chown` command with the `--reference` flag to copy the ownership from the source to the destination.
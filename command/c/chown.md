# `chown`

## Description

`chown` stands for change owner which changes user or group ownership of a file, directory, or symbolic link. Every file or directory has group or user ownership in Linux. Since multiple users and groups can use same linux system so they all have unique names and IDs. Name and ID of a user and a group can be same. 

For displaying the owner of any file or folder, one can use 
```shell
ls -l [file or folder name]
```

example: 

```shell
ls -l test.txt 
```

_Output:_
```shell
-rw-rw-r-- 1 sasa sasa 0 Dec  3 21:42 test.txt
```

In above output section first 'sasa' denotes user and 'sasa' second denotes its group.



You can also check the owner ship of any folder. You should be in position where when typed `ls` shows your directory `test_folder` (example folder), then type below command to see owner ship of your `test_foler`.

eg: 
```shell
ls -l ./
```

_Output:_
```shell
drwxrwxr-x  2 sasa sasa    4096 Dec  3 21:42  test_foler

```

### 1. Changing ownership of file to another user.

 After executing below command ownership of `test.txt` changes from `sasa` to `root` .

```shell
    sudo chown root test.txt
```

_Output:_
```shell
    -rw-rw-r-- 1 root sasa 0 Dec  3 21:42 test.txt

```

In above output section, ownership changed to user `root` from user `sasa`. Group `sasa` still has also ownership. 

_Note:_

You can also use owner userid in place of owner to change ownership in above example like: 
    
```shell
    id -u user_name
```
Suppose, output is 1000.

Now you can replace user_name with its user_id. 
eg: In place of "sudo chown user_name test.txt", you can use below:

```shell
sudo chown 1000 test.txt

```

_Another Note:_
For changing ownership of folder, you can do it similarly like:

```shell
sudo chown root test_folder
```
It gives ownership of test_folder to user `root`.
 

### 2. Changing the group of a file. 

```shell
sudo chown :root test.txt
```

_Output:_
```shell
-rw-rw-r-- 1 root root 0 Dec  3 21:42 test.txt

```

Here group of file `test.txt` changed from `sasa` to `root`.

### 3. Changing both file ownership and group at once. 

```shell
sudo chown sasa:sasa test.txt
```

_Output:_
```shell
-rw-rw-r-- 1 sasa sasa 0 Dec  3 21:42 test.txt

```

Ownership changed to user `sasa` and  group `sasa`.

_Note:_
```shell
You can use -v after  chown (verbose), it will display the changes made in format something like this: 
"changed ownership of 'test.txt' from 
root:root to sasa:sasa "
```

### 4. Changing owner of multiple files 
You can use different files with space in between them to change ownership of multiple files at once. 

```shell
sudo chown owner_name file1 file2 file3 
```
## Flags

### Flag/Option 1

**Description:** Explain the purpose and function of the first flag/option.

**Usage:** Provide examples of how to use it.

### Flag/Option 2

## Examples

Background for examples is must

## Additional Information

## Exercises
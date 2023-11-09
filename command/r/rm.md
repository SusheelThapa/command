# `rm`

## Description

`rm` is a standard Unix utility that removes files and directories. It should be used carefully as the items deleted with `rm` are permanently deleted and do not remain in `trash` folder.

It can be modified with flags to further improve its functionality.

The command syntax is:

```shell
rm [flags] [file / directory]
```

## Flags

Some of the popular flags that are used with `rm` command are as follows:

- [`-d`](#d): deletes empty directories.
- [`-f`](#f): deletes an item even if it is locked or protected without prompting for confirmation.
- [`-i`](#i): prompts before every removal.
- [`-r`](#r): removes directories and their contents recursively.
- [`-v`](#v): lists what is being deleted.
- [`--help`](#-help): get more information about the command and uncommon flags. 

### `-d`

**Description:**

By default, `rm` command primarily deletes just files and not folders. We use another command `rmdir` for removing empty directories. This same functionality can also be done with the `rm` command and the `-d` flag. In summary, `-d` flag is used to delete empty directories.

**Usage:**
Consider we have an empty folder `test`. If we want to delete the folder, we need to use the `-d` flag as:

```shell
rm -d test
```

_Output:_

No Output, use `ls` command to verify.


### `-f`

**Description:**

With the `-f` flag, the `rm` command will forcefully delete a file without prompting for confirmation even when it is protected.

**Usage:**
Let us assume that we are in a folder `test` which contains a file `file1.txt` which is _write-protected_.

**Without the `-f` flag:**
```shell
rm file1.txt
```

_Output:_

```
rm: remove write-protected regular empty file 'file1.txt'?
```

**With the `-f` flag:**
```shell
rm -f file1.txt
```

_Output:_

No Output, use `ls` command to verify.


### `-i`

**Description:**

With the `-i` flag, the `rm` command will prompt the user before deleting any file.

**Usage:**
Taking the example from above we can enter the following into the terminal

```shell
rm -i file1.txt
```

_Output:_

```
rm: remove regular empty file 'file1.txt'? 
```

If you press `Y` then the file will be deleted and if you press `N` then the file will not be deleted.

### `-r`

**Description:**

With the `-r` option, the `rm` command will recursively delete everything inside a directory. This effectively extends the functionality of `rm` command from just files to both files and directories.

**Usage:**
Taking the example where we have files `.file.txt`, `file1.txt` and `file2.txt` in a folder called `test`. The flag will be more clear if we pair the `-r` flag with the `-i` flag as:

```shell
rm -ri test
```

_Output:_

```
rm: descend into directory 'test'? Y
rm: remove regular empty file 'test/file2.txt'? N
rm: remove regular empty file 'test/.file.txt'? N
rm: remove regular empty file 'test/file1.txt'? N
rm: remove directory 'test'? N
```

This shows exactly how the `-r` flag traverses into the directory. Without the `-i` flag, there will be no output and the files are simply deleted.

### `-v`

**Description:**

With the `-v` option, the `rm` command will show details for the deleted file.

**Usage:**
Taking the example where we have files `.file.txt`, `file1.txt` and `file2.txt` in a folder called `test`. The flag will be more clear if we pair the `-r` flag with the `-v` flag as:

```shell
rm -rv test
```

_Output:_

```
removed 'test/file2.txt'
removed 'test/.file.txt'
removed 'test/file1.txt'
removed directory 'test'
```

Without the `-v` flag, there will be no output and the files are simply deleted.

### `--help`

**Description:**

With the `--help` option, the `rm` command will show other flags and options for the command that are not commonly used.

**Usage:**

```shell
rm --help
```

## Examples

1. To remove `file` from a folder `Sample`:
   ```shell
   rm Sample/file
   ```

2. To remove a protected `file` from a folder `Sample`:
   ```shell
   rm -f Sample/file
   ```

3. To list the files being deleted from a folder `Sample`:
   ```shell
   rm -rv Sample
   ```

## Additional Information

Wildcards such as `*` or `?` can be used with the `rm` command. For example: Let us consider that we have a `Pictures` folder that contains 50 pictures of the type `personal1.png, personal2.png` and so on. It also contains 50 more pictures of the type `work1.png, work2.png` and so on. If you're tasked with deleting the `work` pictures only then it can be tedious to remove it one by one. In that case we use the `?` wildcard as shown below:

```shell
rm work?.png
```

Note: `*` matches one or more occurrences of any character, including no character and `?`  matches a single occurrence of any character.

## Exercises

1. Create a folder `test` containing files `normalFile.txt`, `.hiddenFile.txt`. Remove the write permission of `normalFile.txt` and try deleting it with the `rm` command and observe the result. Hint: You may need to use `mkdir`, `touch` and `chmod` commands as well.

2. Use the above exercise and find a suitable flag and delete `normalFile.txt`. 

3. Use the `verbose` option to delete the `.hiddenFile.txt`.

4. Delete the now empty `test` folder with the `rm` command and suitable flag.

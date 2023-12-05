# Command Name
`pwd`
## Description
`pwd` command prints the complete path of the working directory to standard output in UNIX-like and other operating systems. It stands for Print Working Directory. It is equivalent to the Windows `cd` command.
The syntax of `pwd` command in Linux is:
```shell
pwd[OPTIONS]
```
## Flags
The `pwd` command accepts two flags for specific behaviour:
`pwd -L` and `pwd -P`
### Flag/Option 1
`-L`
**Description:** 
The `-L` flag is used to print symbolic links; in Linux, it points towards the file or folder where your are currently working in. This is; symbolic links are resolved and the actual path to the directory is displayed. The `-L` option is used to explicitly request the logical path, and it's the default behaviour.
**Usage:** #Provide examples of how to use it.
When you navigate to the directory through this link and use `pwd -L` , it will show the actual path:

### Flag/Option 2
If you want to see the physical path without following symbolic links, you can use the `-P` option.
 ```shell
 $ pwd -P
   /actual/path/without/symlinks
 ```
## Examples
```shell
$pwd
home/user/documents

```
In this case, the user is located in the `documents` directory within the `user` home directory, which is under the root directory (`/`).
<!-- Background for examples is must -->

## Additional Information
-`pwd` can be used with other commands that require directory paths as arguments. To list the contents of the current directory, you can use:
```shell
$ ls $(pwd)
```
- `pwd` can be used to refer to the manual pages using the `man` command for more detailed information.
```shell
$ man pwd
```
## Exercises

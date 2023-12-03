# `mkdir`

## Description

`mkdir` is a standard Unix command that stands for "make directory," serving as a fundamental tool for creating folders within a file system. It allows users to specify directory names as arguments, creating the corresponding directories. The name "mkdir" is derived from its primary function of making directories.

The `mkdir` command syntax is:

```shell
mkdir [OPTION] DIRECTORY...
```

**OPTION**: Optional flags that modify the behavior of the command.
**DIRECTORY**: The name of the directory or directories to be created.

## Flags

Some of the flags that are used with `mkdir`command are given below:

- [`-p`](#p) or [`--parents`](#par): Create parent directories if they do not exist.
- [`-m`](#m) or [` --mode=MODE`](#mod) : Set the permissions of the newly created directories.
- [`-v`](#v) or [`--verbose`](#ver):Print a message for each created directory. 
- [`-h`](#h) or [`--help`](#hep) :Display help information about the mkdir command.

### `-p`

**Description**

The `-p` flag, short for "parents," is useful for creating nested directories by automatically creating missing parent directories in the specified path.This eliminates the need for manual creation of intermediate directories.

**Usage**

The `-p`flag is commonly used when creating directories with multiple levels of nesting or when the exact directory structure is not known beforehand. For instance, to create a directory named `Documents/Reports/Q1`you can use the following command:

```Bash
mkdir -p Documents/Reports/Q1
```

This command will create the entire directory path, including the `Documents` and `Reports` directories, if they do not exist.

### `-m`

**Description**

The `-m` flag in the `mkdir` command, meaning "mode," sets permissions for newly created directories. It controls access and modification rights, accepting parameters in numeric or symbolic format.

**Usage**

The `-m` flag in mkdir controls access rights for new directories. For instance, to create an `Images` directory with user read/write/execute and group/others read/execute permissions, use:

```Bash
mkdir -m 755 Images
```

This command will set the permissions of the `Images` directory to `755`, which corresponds to the specified access rights.

### `-v`
**Description**

The `-v` flag in the `mkdir` command, standing for "verbose," prints detailed information about each created directory. It is handy for debugging or obtaining a thorough log of the command's actions.

**Usage**
The `-v` flag in `mkdir` is useful for troubleshooting or tracking batch operations. For example, to create a "Videos" directory with a message for each created directory, use:

```Bash
mkdir -v Videos
```

This command will create the `Videos` directory and display a message indicating the creation of each directory in the path.

### `-h`

**Description**

The `-h` flag, short for "help," displays help information about the mkdir command, including its syntax, available options, and usage examples.

**Usage**

The `-h` flag is commonly used to quickly reference the mkdir command's usage and available options. For instance, to display help information for the mkdir command, you can use the following command:

```Bash
mkdir -h
```

This command will provide a brief summary of the mkdir command's usage and available flags.

## Additional Information
- The `mkdir` command can be used to create multiple directories simultaneously by providing multiple directory names as arguments.
   ```bash
    mkdir dir1 dir2 dir3
   ```

- If a directory with the specified name already exits, `mkdir` will return an error unless the `-p` option is used.

  Example:
  ```bash
   mkdir -p /path/to/parent/directory/new_directory

  ```
  This command will create the directory new_directory and, if necessary, the parent directories (parent, directory, to) in the specified path.

## Exercises
1. Use `mkdir` command to create a new directory named `my_directory`.

2. Use the `-p` flag to create the `my_directory` directory and its parent directories if they don't already exit.

3. Use the `-m` flag to set the permission of the `my_directory` directory to `0775`.

4. Use the `-v` flag to print a message to the console indicating that the `my_directory` directory was created.
# `touch`

## Description

The `touch` command is a standard command used in the unix/linux operating system which is used to create, change and modify the timestamps of a file. 

It is used to create a file without any content. 

The syntax for `touch` command is:

```shell
touch [flags] [file_names]
```

## Flags

Some of the flags that are used with `touch` command are as follows:

- [`-a`](#a) : only to change access time of the file.
- [`-c`](#c) or `--no-create`: do not create any files.
- [`-d`](#d) or `--date=string`: parse string and use it instead of current time.
- [`-m`](#m) : change only the modification time.
- [`-r`](#r) or `--reference=file` : use this file's times instead of current time.
- [`-t`](#t) stamp : use [[cc]yy]mmddhhmm[.ss] instead of current time.

- [`--help`](#-help) : get more information about this command. 

### `-a`

**Description:**

It changes the access time of the file and does not change the modification time unless `-m` is also specified.

**Usage:**

Consider we want to change access time of a file `file1.txt`, make sure you are in the correct directory then:

```shell
touch -a file1.txt
```

You can use the `stat` command to check the updated time:
```shell
stat file1.txt
```
### `-c`

**Description:**

Using this flag, it does not create the file if it does not already exist. No diagnostic messages are written concerning this condition and it is usually used with other flags.

**Usage:**

If we want to update the the access time of a file only if it exists then:
```shell
touch -c -a file1.txt
```

### `-d`

**Description:**

The `touch` command uses the `-d` option to set a timestamp using a date string. the date string is a flexible time format and accepts many different human-readable textual forms. some examples are:

- calender dates `11 november 2023`.
- time of day `9:08pm`.
- days of the week `sunday`.
- relative time `yesterday`, `next tuesday` etc.

**Usage:**

Let us use this flag to change the access and modify time of the file `file1.txt`:
```shell
touch -d "8 march 2023" file1.txt
```
Also,
```shell
touch -d "yesterday" file1.txt
```

### `-m`

**Description:**

This flag is used to change modification time of the file. the `-m` option changes the modification time to the current timestamp by default.

**Usage:**

If we want to update the the modificationtime of a file `file1.txt` then:
```shell
touch -m file1.txt
```

### `-r`

**Description:**

The `touch` command offers a useful option to change a file's timestamp based on another file's timestamp.

**Usage:**

Let's update timestamp of `file1.txt` using `file2.txt` as reference. 

```shell
touch -r <reference file> <file>
```
```shell
touch -r file2.txt file1.txt
```

### `-t`

**Description:**

Using `-t` we can explicitly state the timestamp. it is used in combination with other flags. the time is given in `yymmddhhmm`.

**Usage:**

Using following command timestamp is changed to `2023 nov 12, 9:34pm`:

```shell
touch -t yymmddhhmm filename
```
```shell
touch -t 2311122134 file1.txt
```

### `--help`

**Description:**

With the `--help` option, the `touch` command will show flags and options for the command.

**Usage:**

```shell
touch --help
```

## Additional Information

We can use all of the above flags with multiple files.
```shell
touch file1.txt file2.txt file3.txt
```

This command creates these files if they do not exist and update their timestamp.

We can also use regular expression like `*.c` to modify timestamp of files at once.
```shell
touch -m *.cpp
```

## Exercises:

1. Use `touch` command to create a new file `file`.
2. Use `-d` flag to update timestamp of `file` to `2024 dec 10`.
3. Use `-r` to update timestamp of `file` using existing file.
4. Update access time of `file` using `-t` to any date.

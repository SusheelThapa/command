# `touch`

## Description

The `touch` command is a standard command used in the UNIX/Linux operating system which is used to create, change and modify the timestamps of a file. 

It is used to create a file without any content. 

Syntax for `touch` command is:

```shell
touch [flags] [file_names]
```

## Flags

Some of the flags that are used with `touch` command are as follows:

- [`-a`](#a) : only to change access time of the file.
- [`-c`](#c) or `--no-create`: do not create any files.
- [`-d`](#d) or `--date=STRING`: parse STRING and use it instead of current time.
- [`-m`](#m) : change only the modifcation time.
- [`-r`](#r) or `--reference=FILE` : use this file's times instead of current time.
- [`-t`](#t) STAMP : use [[CC]YY]MMDDhhmm[.ss] instead of current time.

- [`--help`](#help) : get more information about this command. 

### `-a`

**Description:**

It changes the access time of the file and does not chage the modification time unless -m is also specified.

**Usage:**

Consider we want to change access time of a file `file1.txt`, make sure you are in the correct directory then:

```shell
touch -a file1.txt
```

You can use the following command to check the udpated time:
```shell
stat file1.txt
```
### `-c`

**Description:**

Using this flag, it does not create the file if it does not already exist. No diagnostic messages are written concerning this condition. It is usually used with other flags.

**Usage:**

If we want to update the the access time of a file only if it exists then:
```shell
touch -c -a file1.txt
```

### `-d`

**Description:**

The `touch` command uses the `-d` option to set a timestamp using a date string. The date string is a flexible time format and accepts many different human-readable textual forms. some examples are:

- Calender dates `11 November 2023`.
- Time of day `9:08pm`.
- Days of the week `Sunday`.
- Relative time `yesterday`, `next tuesday` etc.

**Usage:**

Let us use this flag to change the access and modify time of the file `file1.txt`:
```shell
touch -d "8 March 2023" file1.txt
```
Also,
```shell
touch -d "yesterday" file1.txt
```

### `-m`

**Description:**

This flag is used to change modification time of the file. The `-m` option changes the modification time to the current timestamp by default.

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

Using `-t` we can explicitly state the timestamp. It is used in combination with other flags. The time is given in `YYMMDDHHMM`.

**Usage:**

Using following command timestamp is changed to `2023 Nov 12, 9:34pm`:

```shell
touch -t YYMMDDHHMM filename
```
```shell
touch -t 2311122134 file1.txt
```

### `-help`

**Description:**

With the `--help` option, the `touch` command will show flags and options for the command.
**Usage:**

```shell
touch --help
```

## Aditional Information

We can use all of the above flags with multiple files.
```shell
touch file1.txt file2.txt file3.txt
```

This command creates these files if they do not exist and update their timestamp.

We can also use regular expression like `*.c` to modify timestamp of files at once.
```shell
touch -m *.cpp
```

## Exercises

1. Use `touch` command to create a new file `FILE`.
2. Use `-d` flag to update timestamp of `FILE` to `2024 Dec 10`.
3. Use `-r` to update timestamp of `FLIE` using existing file.
4. Udpate access time of `FILE` using `-t` to any date.

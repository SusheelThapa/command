# `echo`

## Description

`echo` is a standard Unix utility that displays a line of text in the terminal.

The command syntax is:

```shell
echo [flags] [text]
```

## Flags

Here are some flags associated with `echo`.

- [`-e`](#e): enable interpretation of backslash escapes.
- [`-E`](#E): disable interpretation of backslash escapes.
- [`-n`](#n): do not output the trailing newline.
- [`--help`](#-help): get more information about the command 

### `-e`

**Description:**

With the `-e` option, the `echo` command will interpret escape characters such as `\t` and `\n`.

**Usage:**
Let us assume we want to display the word `Hello World` into the terminal such that the words are separated by a tab. We will do this as:

```shell
echo -e "Hello\tWorld"
```

Since `-e` is the default flag, we can ommit it and still get the same result.

```shell
echo "Hello\tWorld"
```

_Output:_

```
Hello   World
```

### `-E` {#E}

**Description:**

With the `-E` option, the `echo` command will interpret escape characters such as `\t` and `\n` as characters and not escape characters.

**Usage:**
Taking above example with `-E` flag:
```shell
echo -E "Hello\tWorld"
```

_Output:_

```
Hello\tWorld
```

### `-n`

**Description:**

With the `-n` option, the `echo` command will not output the trailing new line. This is useful for when you're writing multiple `echo` statements in a script as described in the [example](#examples) section.

**Usage:**
```shell
echo -n "Hello World"
```

_Output:_

```
Hello World
```

### `--help`

**Description:**

With the `--help` option, the `echo` command will show other flags and options for the command that are not commonly used.

**Usage:**

```shell
echo --help
```

## Examples

1. Let's say you are writing a shell script that   displays a progress message with a series of dots to indicate a task is in progress. You want the dots to appear on the same line, without a newline character between them.

    **Without `-n` flag**:
    Assume the contents of a `test` file are as follows:
    ```shell
    echo "Task in progress"
    echo "..."
    ```

    Executing the file, the output will be:
    ```
    Task in progress
    ...
    ```

    **With `-n` flag:**
    Assume the contents of a `test` file are as follows:
    ```shell
    echo -n "Task in progress"
    echo "..."
    ```

    Executing the file, the output will be:
    ```
    Task in progress...
    ```

2. Printing words in a separate line
    ```shell
    echo -e "Hello\nWorld"
    ```

    The output will be:
    ```
    Hello
    World
    ```

3. Printing the escape charactes as is:
    ```shell
    echo -E "Hello\nWorld"
    ```

    The output will be:
    ```
    Hello\nWorld
    ```

## Additional Information

`echo` command is frequently used to redirect user input to a file such as:
```shell
echo "Save this file" > file.txt
```
Now the content of `file.txt` will be:
```
Save this file
```

## Exercises

1. Use the `--help` flag and print a `\` into the terminal.

2. Create a file with your name with the `echo` command and the `>` redirect operator.

3. Create a file with two lines `Hello` and `World` using a single `echo` command and the `>` redirect operator.

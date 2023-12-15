# `strings`

## Description

The `strings` command is a utility that extracts printable character sequences from binary files. It is often used to analyze and display human-readable text embedded in binary data, such as executable files or libraries. The primary purpose is to reveal strings of characters, such as ASCII or Unicode text, within a given file.

The syntax for the command is:

```shell
strings [options] [file...]
```


## Examples

1.  **Extract Strings from an Executable:**

    To extract strings from an executable file, we can use the `strings` command with the path to the executable file.
    
    ```shell
    strings /path/to/executable
    ```

2.  **Display Strings with Minimum Length:**

    To display strings with a minimum length, we can use the `-n` option with the `strings` command. For example, to display strings with a minimum length of 10 characters, we can use the following command:

    ```shell
    strings -n 10 /path/to/binary_file
    ```

3.  **Output to a file:**

    To output the extracted strings, we can use the `>` operator with the `strings` command. For example, to output the extracted strings to a file named `output.txt`, we can use the following command:

    ```shell
    strings /path/to/binary_file > output.txt
    ```


## Exercises

Download [tampered_garden.jpg](https://file.io/opuRdis1xqCj)

1.  Extract and display all printable character sequences from the file `tampered_garden.jpg`.

2.  Display only strings with a minimum length of 15 characters the binary file `tampered_garden.jpg`.

3.  Save the output of exercise no. 1 to a file named `output.txt`, with each result prefixed with its offset within the file.

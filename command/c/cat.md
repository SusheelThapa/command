# `cat`

## Description

`cat` is a standard Unix utility that reads files sequentially, writing them to standard output. The name is derived from its function to (con)**cat**enate files(from Latin _catenare_).

The other primary purpose of `cat`, aside from concatenation, is **file printing** i.e. _allowing the computer user to view the contents of a file._

The command syntax is:

```shell
cat [flags] [file_names]
```

The `cat` utility serves a dual purpose: _[concatenating](#concatenation) and [printing](#printing)._

### _Printing:_

With a single argument, it is often used to print a files to a user's terminal.

Suppose you have a file with name`file.txt` with following lines.

> This is file.txt.

Let's use `cat` command to print the content of `file.txt`.

```shell
cat file.txt
```

_Output:_

```
This is file.txt.
```

---

### _Concatenation:_

With more than one argument, it concatenates several files and combined result is by default printed to the terminal, but user often redirects the result into another files.

Suppose we have two files named `file1.txt` and `file2.txt` with following lines.

_`file1.txt`_

> This is file1.txt

_`file2.txt`_

> This is file2.txt

Let's use `cat` command to concatenate `file1.txt` and `file2.txt`

```shell
cat file1.txt file2.txt
```

_Output:_

```
This is file1.txt.This is file2.txt
```

_Redirection:_

```shell
cat file1.txt file2.txt > file3.txt
```

_Output:_

_`file3.txt` will be created which will contain the output of `cat file1.txt file2.txt`i.e.`This is file1.txt.This is file2.txt.`_

Note:

- _`>` is used to overwrite (“clobber”) a file and `>>` is used to append to a file. When you use `cat file1.txt file2.txt > file3.txt`, the output of ` cat file1.txt file2.txt`` will be written to  `file3.txt` and if a file named file was already present, its contents will be overwritten._
- _`>>` is used to append to a file. When you use `cat file1.txt file2.txt >> file3.txt`, the output of `cat file1.txt file2.txt` will be written to file and if the file named file was already present, the file will now contain its previous contents and also the contents of `cat file1.txt file2.txt`, written after its older contents of file._

## Flags

Some of the popular flags that are used with `cat` command are as follows:

- [`-n`](#n): number all output lines
- [`-s`](#s): suppress repeated empty output lines.
- [`-b`](#b): number only non-blank output lines.
- [`-v`](#v): display nonprinting characters, excepts for tabs and the end of line character.
- [`-e`](#e): implies [`-v`](#v) but also display tabs as `$`.
- [`-t`](#t): implies [`-v`](#v) but also display tabs as `^I`.

### `-n`

**Description:**

With the `-n` option, the `cat` command will prefix each output lines by its line number.

**Usage:**

```shell
cat -n longtext.txt
```

_Output:_

```
1	Lorem Ipsum is simply dummy t
2
3
4	It has survived not only five
5
6
7	was popularised in the 196
8
9
0	publishing software like Ald
```

### `-s`

**Description:**

With the `-s` option, the `cat` command will collapse multiple consecutive empty lines into one empty line.

**Usage:**

```shell
cat -s longtext.txt
```

_Output:_

```shell
Lorem Ipsum is simply dummy t

It has survived not only five

was popularised in the 196

publishing software like Ald
```

### `-b`

**Description:**

With `-b` options, the `cat` command will number only non-blank output lines ignoring the empty ones.

**Usage:**

```shell
cat -b longtext.txt
```

_Output:_

```
1	Lorem Ipsum is simply dummy t


2	It has survived not only five


3	was popularised in the 196


4	publishing software like Ald
```

### `-v`

**Description:**

With `-v` optiton, the `cat` command will display all the non-printing characters with **caret** and meta notation, except the line feed and tabulation.

With `-v` option, control characters will appear as a caret(`^`) followed by the appropriate ASCII characters(e.g., the \_carriage_return, byte 13, is displayed as `^M` because `M` in ASCII is 64 +13), and character with the high-order bit set will appear in "meta" notation `M-` followed by the representation corresponding to the 7 lower bits(e.g., the byte 141 will be displayed as `M-^M` because 141 is 128 + 13)

**Usage:**

```shell
cat -v cat.jpeg
```

_Output:_

```
M-^?M-XM-^?M-`^@^PJFIF^@^A^A^A^@^@^@^@^@^@M-^?M-a^@.Exif^@^@MM^@*^@^@^@^H^@^B@^@^@^C^@^@^@^A^@d^@^@@^A^@^A^@^@^@^A^@^@^@^@^@^@^@^@M-^?M-[^@C^@
^G^G    ^G^F
        ^H      ^K^K
^L^O^Y^P^O^N^N^O^^^V^W^R^Y$ &%# #"(-90(*6+"#2D26;=@@@&0FKE>J9?@=M-^?M-[^@C^A^K^K^K^O^M^O^]^P^P^]=)#)==================================================M-^?M-@^@^Q^H^As^AM-Z^C^A"^@^B^Q^A^C^Q^AM-^?M-D^@^_^@^@^A^E^A^A^A^A^A^A^@^@^@^@^@^@^@^@^A^B^C^D^E^F^G^H
^KM-^?M-D^@M-5^P^@^B^A^C^C^B^D^C^E^E^D^D^@^@^A}^A^B^C^@^D^Q^E^R!1A^F^SQa^G"q^T2M-^AM-^QM-!^H#BM-1M-A^URM-QM-p$3brM-^B
^V^W^X^Y^Z%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyzM-^CM-^DM-^EM-^FM-^GM-^HM-^IM-^JM-^RM-^SM-^TM-^UM-^VM-^WM-^XM-^YM-^ZM-"M-#M-$M-%M-&M-'M-(M-)M-*M-2M-3M-4M-5M-6M-7M-8M-9M-:M-BM-CM-DM-EM-FM-GM-HM-IM-JM-RM-SM-TM-UM-VM-WM-XM-YM-ZM-aM-bM-cM-dM-eM-fM-gM-hM-iM-jM-qM-rM-sM-tM-uM-vM-wM-xM-yM-zM-^?M-D^@^_^A^@^C^A^A^A^A^A^A^A^A^A^@^@^@^@^@^@^A^B^C^D^E^F^G^H
```

### `-e`

**Description:**

The `-e` options works like the `-v` option, except it will also add a dollar sign(`$`) before each _line-feed_ character, thus explicitly showing the end of lines.

**Usage:**

```shell
cat -e longtext.txt
```

_Output:_

```
Lorem Ipsum is simply dummy t$
$
$
It has survived not only five$
$
$
was popularised in the 196$
$
            $
publishing software like Ald$
```

### `-t`

**Description:**
The `-t` option works like the `-v` option, except it will also display _tabulations_ using `^I` caret notation.

**Usage:**

```shell
cat -t longtext.txt
```

```
Lorem Ipsum is simply dummy t
^I   ^I^I

It has survived not only five


was popularised in the 196
^I^I^I

publishing software like Ald
```

## Examples

1. Imagine you're on your computer, and you want to quickly check out what's inside a file, maybe it's a fun story or an important message from a friend. You can use the "cat" command to open the file and see its content.

   ```shell
   cat story.txt
   ```

2. Let's say you're working on a school project and have two different pieces of information in separate files. You can use "cat" to put them together.

   ```shell
   cat firstname.txt lastname.txt
   ```

3. Imagine you're reading a long comic book, and you want to tell your friend about specific pages. You can add page numbers to the comic using this command.

   ```shell
   cat -n comic.txt > numberedcomic.txt
   ```

4. If you're starting to write a cool story or a secret journal, you can create a new empty file with this command. It's like getting a blank page to write your thoughts.

   ```shell
   cat > newfile.txt
   ```

5. If you're copying a file from one friend's computer to yours, you use this command to transfer the file to your computer.

   ```shell
   cat file1.txt > file2.txt
   ```

6. Imagine you're reading a book with a lot of pages. Instead of flipping through every page, you can use this command to read it one section at a time.

   ```shell
   cat chap1.txt chap2.txt chap3.txt | less
   ```

## Additional Information

A comprehensive discussion of the `cat` command always includes a reference to the "Useless Use of `cat`" anti-pattern. In this context, it refers to individuals making tasks unnecessarily complicated when simpler and more efficient methods are available.

_Imagine you have a favorite book, and you want to share a cool part with your friend. You could either read the part out loud to your friend, or you could just give them the book to read themselves. Reading it out loud is like using "cat" in a "useless" way because it's extra work._

Here's an example:

_Useless Use of `cat`:_

```shell
cat favorite_book.txt | less
```

_Simpler and Better Way:_

```shell
less | favorite+book.txt
```

_In the case of the "Useless Use of Cat," you're essentially vocalizing the book using the "cat" command before passing it on. However, a more straightforward approach is to directly hand over the book to your friend for reading. This method is simpler, avoiding unnecessary extra steps._

## Exercises

1. File Concatenation

   - Create three text files, such as `file1.txt`, `file2.txt`, and `file3.txt`, with some sample text in each.
   - Use the cat command to concatenate the contents of `file1.txt`, `file2.txt`, and `file3.txt` into a single file, let's call it all `files.txt`.
   - Verify that all f`iles.txt` contains the combined text from the three original files.

2. Creating and Copying files

   - Create a new text file named `mydocument.txt` using the cat command.
   - Type a short message or any text content into `mydocument.txt`.
   - Create a copy of `mydocument.txt` and name it `mydocument_copy.txt` using the cat command.
   - Verify that both `mydocument.txt` and `mydocument_copy.txt` contain the same text.

3. Numbering Lines

   - Create a text file named `poem.txt` with a few lines of poetry.
   - Use the `cat` command with the `-n` option to display the contents of `poem.txt` with line numbers.
   - Observe the output and note how line numbers are added.

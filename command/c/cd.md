# `cd`

## Description

The `cd` command, also known as `chdir`(**ch**ange **dir**ectory), is a command-line shell command used to change the current working directory in various operating systems. IT can be used in shell scripts and batch files.

The command syntax are:

```shell
cd directory
```

## Use cases

1. Imagine you have a folder(`videogames`) on your computer where you keep all your video games. You use the `cd` command to go there so you can play your favorite games.

   ```shell
   cd videogames
   ```

2. Suppose you have a folder(`music`) where you store your music. You use cd to enter that folder to listen to your favorite songs.

   ```shell
   cd music
   ```

3. Imagine you are working in a project folder named `my_project` that is located within a `projects` directory, which, in turn, is inside your `Documents` directory. To move up to the parent directory (i.e. `Documents`), you can use the `cd ..` command.

   ```shell
   cd ..
   ```

4. Let's say you've been exploring various directories, and you want to quickly return to your home directory. You can simply use `cd` without any arguments:

   ```shell
   cd
   ```

5. You're working in two directories: `source` and `destination`. You want to quickly switch back and forth between them. You can use `cd -` to toggle between these directories.

   ```shell
   cd source
   cd - # Switches to "destination"
   cd - # Switches back to "source"
   ```

6. Suppose you have a directory named `My Documents`` with a space in the name, and you want to navigate to it. To do this, you need to enclose the directory name in quotes.

   ```shell
   cd "My Documents"
   ```

   Note: _You can also use [escape character](https://en.wikipedia.org/wiki/Escape_character) to achieve same result_

   ```shell
   cd My\ Documents
   ```

## Exercises

1. You are in the `documents` directory and want to navigate to the `pictures` directory, which is a sibling of `documents`. How would you use the cd command to achieve this?
   _Directory Tree_

   ```
    .
   ├── documents
   └── pictures
   ```

2. You want to quickly switch between two directories named `work` and `projects` multiple times. How would you use the cd command to achieve this?

# `cd`

## Description

The `cd` command, also known as `chdir`(**ch**ange **dir**ectory), is a command-line shell command used to change the current working directory in various operating systems. It can be used in shell scripts and batch files.

The syntax for the command is:

```shell
cd [directory]
```

## Use cases

1. Imagine you have a folder (`videogames`) on your computer where you keep all your video games. You use the `cd` command to go there so you can play your favorite games.

   ```shell
   cd videogames
   ```

2. Suppose you have a folder (`music`) where you store your music. You use `cd` to enter that folder to listen to your favorite songs.

   ```shell
   cd music
   ```

3. Imagine you are working in a project folder named `my_project` that is located within a `projects` directory, which, in turn, is inside your `Documents` directory. To move up to the parent directory (i.e. `Documents`), you can use the `cd ..` command.

   ```shell
   cd ..
   ```

4. You're working in two directories: `source` and `destination`. You want to quickly switch back and forth between them. You can use `cd -` to toggle between these directories.

   ```shell
   cd source
   cd - # Switches to "destination"
   cd - # Switches back to "source"
   ```

## Additional Section

1. **Navigating to the `root` Directory**

   To navigate to the `root` directory, which is the top-level directory in the file system, we can use `cd / ` command.

   ```shell
   cd /
   ```

2. **Navigating to `home` Directory**

   To navigate to `home` folder, where personal files and settings are stored, we can use the `cd` command with either username or the tilde (`~`) symbol.

   ```shell
   cd susheel
   ```

   _OR_

   ```shell
   cd ~
   ```

   _OR_

   ```shell
   cd
   ```

3. **Navigating Directory with _spaces_ in them**

   Suppose you have a directory named `My Documents`` with a space in the name, and you want to navigate to it. To do this, you need to enclose the directory name in quotes.

   ```shell
   cd "My Documents"
   ```

   Note: _You can also use [escape character](https://en.wikipedia.org/wiki/Escape_character) to achieve same result_

   ```shell
   cd My\ Documents
   ```

4. **Navigating using _absolute paths_ and _relative paths_**

   1. **Absolute Path**

      - An absolute path specifies the complete directory structure from the root directory to the target directory.
      - It always begins with a forward slash (`/`) in the Unix-like systems.

      **Example**

      Suppose you have the following directory structure:

      ```
      /
      ├── home
      │   └── user
      │       ├── documents
      │       └── pictures
      └── var
         └── logs
      ```

      _To navigate to the `pictures` directory using an absolute paths:_

      ```shell
      cd /home/user/pictures
      ```

   2. **Relative Paths**

      - A relative path specifies the location of the target directory relative to your current working directory.
      - It doesn't start with a forward slash.

      **Example**

      If you are currently in the `documents` directory.

      ```
      /
      ├── home
      │   └── user
      │       ├── documents
      │       └── pictures
      └── var
         └── logs
      ```

      _To navigate to the `pictures` directory using a relative path_

      ```shell
      cd ../pictures
      ```

   _Note: You can learn more about absolute and relative path from [here](https://www.geeksforgeeks.org/absolute-relative-pathnames-unix/)._

## Exercises

1. You are in the `videogames` directory and want to navigate to the `movies` directory, which is a sibling of `videogames`. How would you use the cd command to achieve this?

   _Directory Tree_

   ```
    .
   ├── movies
   └── videogames
   ```

2. You want to quickly switch between two directories named `work` and `projects` multiple times. How would you use the cd command to achieve this?

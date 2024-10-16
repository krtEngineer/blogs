Date: 16/10/2024

### Essential Linux Commands: Part 2

This is second part of blog series which contains essential linux commands. Here, we discuss basic usage of commands for **managing files and directories**, with examples.

1. [pwd](https://man7.org/linux/man-pages/man1/pwd.1.html)
   Displays the current directory.
   ```bash
   kushagratiwari$ pwd
   /Users/kushagratiwari/personal_projects/examples
   ```
2. [ls](https://man7.org/linux/man-pages/man1/ls.1.html)
   Displays the content of a directory.

   ```bash
   kushagratiwari$ ls
   file.txt
   kushagratiwari$ ls -l
   total 0
   -rw-r--r--  1 kushagratiwari  staff  0 Oct 16 23:49 file.txt
   kushagratiwari$ ls -a
   .		..		file.txt
   kushagratiwari$ ls -al
   total 0
   drwxr-xr-x   3 kushagratiwari  staff   96 Oct 16 23:49 .
   drwxr-xr-x  17 kushagratiwari  staff  544 Oct 16 23:49 ..
   -rw-r--r--   1 kushagratiwari  staff    0 Oct 16 23:49 file.txt
   ```

   > See "total 0," it means that the directory contains no files that take up disk space. The "total" refers to the total number of blocks allocated to the files in the directory.

   > Also, two special entries you'll always see are . and ..:
   > . (single dot) refers to the current directory. It allows you to perform operations relative to your current location.
   > .. (double dots) refers to the parent directory. It is used to move up one level in the directory hierarchy.
   > These are standard entries in Unix-like file systems and are present in every directory.

3. [cd](https://man7.org/linux/man-pages/man1/cd.1p.html)
   Changes the current directory.
   ```bash
   kushagratiwari$ ls
   file.txt	new_directory
   kushagratiwari$ cd new_directory
   kushagratiwari$ pwd
   /Users/kushagratiwari/personal_projects/examples/new_directory
   ```
   Go to home directory.
   ```bash
   kushagratiwari$ cd ~
   kushagratiwari$ pwd
   /Users/kushagratiwari
   ```
   Move up one directory level.
   ```bash
   kushagratiwari$ pwd
   /Users/kushagratiwari/personal_projects/examples/new_directory
   kushagratiwari$ cd ..
   kushagratiwari$ pwd
   /Users/kushagratiwari/personal_projects/examples
   ```
4. [touch](https://man7.org/linux/man-pages/man1/touch.1.html)
   Creates an empty file or updates the timestamp of an existing file.
   ```bash
   kushagratiwari$ ls
   file.txt	new_directory
   kushagratiwari$ touch file1.txt
   kushagratiwari$ ls
   file.txt	file1.txt	new_directory
   kushagratiwari$ ls -l
   total 8
   -rw-r--r--  1 kushagratiwari  staff  21 Oct 16 23:54 file.txt
   -rw-r--r--  1 kushagratiwari  staff   0 Oct 17 00:03 file1.txt
   drwxr-xr-x  2 kushagratiwari  staff  64 Oct 16 23:58 new_directory
   kushagratiwari$ touch file.txt
   kushagratiwari$ ls -l
   total 8
   -rw-r--r--  1 kushagratiwari  staff  21 Oct 17 00:03 file.txt
   -rw-r--r--  1 kushagratiwari  staff   0 Oct 17 00:03 file1.txt
   drwxr-xr-x  2 kushagratiwari  staff  64 Oct 16 23:58 new_directory
   ```
5. [mkdir](https://man7.org/linux/man-pages/man1/mkdir.1.html)
   Creates a directory.
   ```bash
   kushagratiwari$ ls
   file.txt	file1.txt	new_directory
   kushagratiwari$ mkdir new_directory_1
   kushagratiwari$ ls
   file.txt	file1.txt	new_directory	new_directory_1
   ```
6. [cp](https://man7.org/linux/man-pages/man1/cp.1.html)
   Copies files or directories.
   Copy a file:

   ```bash
   kushagratiwari$ ls
   file.txt	file1.txt	new_directory	new_directory_1
   kushagratiwari$ cat file.txt
   My name is Kushagra.
   kushagratiwari$ cp file.txt file1.txt
   kushagratiwari$ cat file1.txt
   My name is Kushagra.
   ```

   Copy a directory recursively:

   ```bash
   kushagratiwari$ ls
   file_1.txt	new_directory	new_directory_1
   kushagratiwari$ ls new_directory
   file.txt
   kushagratiwari$ ls new_directory_1
   kushagratiwari$ cp -r new_directory/ new_directory_1/
   kushagratiwari$ ls new_directory_1
   file.txt
   ```

7. [mv](https://man7.org/linux/man-pages/man1/.1.html)
   Moves or renames files and directories.
   Move a file:

   ```bash
   kushagratiwari$ ls
   file.txt	new_directory	new_directory_1
   kushagratiwari$ ls new_directory
   kushagratiwari$ mv file.txt new_directory/file.txt
   kushagratiwari$ ls new_directory
   file.txt
   ```

   Rename a file:

   ```bash
   kushagratiwari$ ls
   file.txt	new_directory	new_directory_1
   kushagratiwari$ mv file.txt file_1.txt
   kushagratiwari$ ls
   file_1.txt	new_directory	new_directory_1
   ```

8. [rm](https://man7.org/linux/man-pages/man1/rm.1.html)
   Deletes files or directories.
   Delete a file:

   ```bash
   kushagratiwari$ ls
   file_1.txt	new_directory	new_directory_1
   kushagratiwari$ rm file_1.txt
   kushagratiwari$ ls
   new_directory	new_directory_1
   ```

   Delete a directory and its contents:

   ```bash
   kushagratiwari$ ls
   new_directory	new_directory_1
   kushagratiwari$ rm -r new_directory_1
   kushagratiwari$ ls
   new_directory
   ```

9. [rmdir](https://man7.org/linux/man-pages/man1/rmdir.1.html)

   Deletes an empty directory.

   ```bash
   kushagratiwari$ ls
   new_directory	new_directory_1
   kushagratiwari$ ls new_directory_1
   kushagratiwari$ rmdir new_directory_1
   kushagratiwari$ ls
   new_directory
   ```

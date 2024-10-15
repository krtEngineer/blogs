Date: 15/10/2024

### Common Linux IO redirections

One of the most fundamental features of Linux is I/O redirection, which allows you to control where the input comes from and where the output goes. In this blog post, we'll explore the basics of I/O redirection with practical examples.

### What is I/O Redirection?

I/O redirection in Linux refers to the process of changing the standard input/output streams. By default, the standard input (**stdin**) is the keyboard, and the standard output (**stdout**) and standard error (**stderr**) are the terminal screen. Redirection allows you to reroute these streams to files or other commands.

Let's delve into each redirection with examples.

1. Send **stdout** to a file.
   command syntax: command >file

   ```bash
   kushagratiwari$ echo 'Namaste, Bharat!'>output.txt
   kushagratiwari$ cat output.txt
   Namaste, Bharat!
   ```

2. Send **stderr** to a file.
   command syntax: command 2>file

   ```bash
   kushagratiwari$ cat file_1.txt 2>output_err.txt
   kushagratiwari$ cat output_err.txt
   cat: file_1.txt: No such file or directory
   ```

3. Send **stdout** and **stderr** to a file.
   command syntax: command >file 2>&1
   Here's what each part does:

   1. command: The command you want to run.
   2. '>' output.txt: Redirects stdout to output.txt.
   3. 2>&1: Redirects stderr (file descriptor 2) to the same location as stdout (file descriptor 1).

   ```bash
   kushagratiwari$ ls /nonexistent_directory > output.txt 2>&1
   kushagratiwari$ cat output.txt
   ls: /nonexistent_directory: No such file or directory
   ```

4. Read **stdin** from a file.
   Command syntax: command <file

   ```bash
   kushagratiwari$ cat unsorted_list.txt
   dog
   cat
   apple
   banana
   zebra
   kushagratiwari$ sort<unsorted_list.txt
   apple
   banana
   cat
   dog
   zebra
   ```

5. Read **stdin** from a file and send **stdout** to another file.
   Command syntax: command <file1 >file2
   ```bash
   kushagratiwari$ cat unsorted_list.txt
   dog
   cat
   apple
   banana
   zebra
   kushagratiwari$ sort <unsorted_list.txt >sorted_list.txt
   kushagratiwari$ cat sorted_list.txt
   apple
   banana
   cat
   dog
   zebra
   ```
6. Append **stdout** at the end of a file.
   Command syntax: command >>file
   ```bash
   kushagratiwari$ cat input.txt
   I am a software engineer.
   kushagratiwari$ echo 'I studied from NIT, Bhopal' >>input.txt
   kushagratiwari$ cat input.txt
   I am a software engineer.
   I studied from NIT, Bhopal
   ```
7. Append **stderr** at the end of a file.
   Command syntax: command 2>>file
   ```bash
   kushagratiwari$ cat input.txt
   I am a software engineer.
   I studied from NIT, Bhopal
   kushagratiwari$ ls /nonexistent_directory 2>>input.txt
   kushagratiwari$ cat input.txt
   I am a software engineer.
   I studied from NIT, Bhopal
   ls: /nonexistent_directory: No such file or directory
   ```
8. Append **stdout** && **stderr** at the end of a file
   Command syntax: command >>file 2>&1

   ```bash
   kushagratiwari$ cat output.txt
   I am an output file.
   kushagratiwari$ ls /path/to/directory >> output.txt 2>&1
   kushagratiwari$ cat output.txt
   I am an output file.
   ls: /path/to/directory: No such file or directory
   ```

9. Read **stdin** from the keyboard until the character c.
   Command syntax: command <<c
   ```bash
   kushagratiwari$ cat <<finish
   > a for apple
   > b for ball
   > c for cat
   > finish
   a for apple
   b for ball
   c for cat
   ```
10. Pipe **stdout** to command2
    Command syntax: command | command2

    ```bash
    kushagratiwari$ ls | grep json
    example.json
    example_1.json

    ```

11. Pipe **stdout** and **stderr** to command2
    Command syntax: command 2>&1 | command2
    ```bash
    kushagratiwari$ ls /path/to/directory 2>&1 | grep file
    ls: /path/to/directory: No such file or directory
    ```

I/O redirection is a fundamental concept in Linux that enhances your ability to manage data flow between commands and files. By mastering these redirection techniques, you can efficiently handle output and errors, automate tasks, and streamline your workflows.

Happy scripting!

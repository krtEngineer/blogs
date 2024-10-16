Date: 16/10/2024

### Linux Wildcards: A Beginner's Guide

Linux wildcards, also known as **globbing patterns**, are powerful tools used to match filenames and strings in the shell. They allow you to perform operations on multiple files without specifying each one individually. In this guide, we'll explore the most common wildcards and provide examples to help you grasp their functionality.

### What Are Wildcards?

Wildcards are special characters used in command-line operations to represent one or more characters. They enable users to efficiently manage files and directories by **matching patterns** rather than exact names.

1. **Asterisk (\*)**
   The asterisk matches **zero or more characters**. It’s the most versatile wildcard, allowing you to match a wide range of filenames.
   ```bash
   kushagratiwari$ ls
   file.txt	file1.txt	file2.txt	file3.txt	file4.json
   kushagratiwari$ ls *.txt
   file.txt	file1.txt	file2.txt	file3.txt
   ```
2. **Question Mark (?)**  
   The question mark matches **exactly one** character. It’s useful when you know the length of the filename but not the exact characters.

   ```bash
   kushagratiwari$ ls
   file.json	file.txt	file1.txt	file2.txt	file3.txt	file4.json
   kushagratiwari$ ls file?.json
   file4.json
   ```

3. **Square Brackets ([])**
   Square brackets match **any one** of the enclosed characters. You can also specify a range of characters.

   ```bash
   kushagratiwari$ ls
   file.json	file.txt	file1.txt	file2.txt	file3.txt	file4.json
   kushagratiwari$ ls file[1234].txt
   file1.txt	file2.txt	file3.txt
   kushagratiwari$ ls file[2-4].txt
   file2.txt	file3.txt
   ```

4. **Exclamation Mark or Caret in Square Brackets ([^] or [!])**
   These match any character not enclosed in the brackets. It’s useful for excluding specific characters.
   ```bash
   kushagratiwari$ ls
   file.json	file.txt	file3.txt	file4.json	fileA.txt	fileB.txt
   kushagratiwari$ ls file[!0-9].txt
   fileA.txt	fileB.txt
   kushagratiwari$ ls file[^0-9].txt
   fileA.txt	fileB.txt
   ```

### Some more examples

1. Deleting files
   Suppose you want to delete all .json files in a directory:
   ```bash
   kushagratiwari$ ls
   file.json	file.txt	file3.txt	file4.json	fileA.txt	fileB.txt
   kushagratiwari$ rm *.json
   kushagratiwari$ ls
   file.txt	file3.txt	fileA.txt	fileB.txt
   ```
2. Copying Files
   To copy all text files to another directory:

   ```bash
   kushagratiwari$ ls
   all_text_files	file.txt	file1.json	file2.json	file3.txt	fileA.txt	fileB.txt
   kushagratiwari$ cp *.txt all_text_files
   kushagratiwari$ ls all_text_files
   file.txt	file3.txt	fileA.txt	fileB.txt
   ```

3. Moving Files
   To move all .json files to a backup directory:
   ```bash
   kushagratiwari$ ls
   all_text_files	file.txt	file2.json	fileA.txt
   backup		file1.json	file3.txt	fileB.txt
   kushagratiwari$ mv *.json backup
   kushagratiwari$ ls
   all_text_files	backup		file.txt	file3.txt	fileA.txt	fileB.txt
   kushagratiwari$ ls backup
   file1.json	file2.json
   ```

Wildcards are an essential part of Linux command-line operations, providing flexibility and efficiency in file management. Experiment with these examples to become more comfortable using wildcards in your daily tasks.

Happy globbing!

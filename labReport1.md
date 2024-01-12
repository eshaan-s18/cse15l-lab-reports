# Lab Report 1 - Remote Access and FileSystem (Week 1)

## `cd` Examples
The command `cd <path>` represents "Change Directory" and is used to switch the current working directory to the given path

***no arguments***
```
[user@sahara ~]$ cd
[user@sahara ~]$
```
This command **does not** output an *error*. This example does not switch the current working directory (`/home`) to a given path because it is missing an argument that defines which path the current working directory (`/home`) should switch to, so the current working directory (`/home`) remains the same as before.

***path to a directory***
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
This command **does not** output an *error*. This example switches the current working directory (`/home`) to `/lecture1` because the command includes a directory argument (`lecture1`) that defines which path the current working directory (now `/lecture1`) should switch to. 

***path to a file***
```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
[user@sahara ~/lecture1]$ 
```
This command **does** output an *error*. This example attempts to switch the current working directory (`/lecture1`) to `Hello.java`, but fails because the command includes a file argument instead of a directory argument. The current working directory (`/lecture1`) can only switch to directories, not files, so the command leads to an error and the current working directory (`/lecture1`) remains the same.

---
## `ls` Examples
The command `ls <path>` represents "List" and is used to list the files and folders in a given path

***no arguments***
```
[user@sahara ~]$ ls
lecture1
[user@sahara ~]$
```
This command **does not** output an *error*. It is not essential for the `ls` command to have a path argument because the command in this example will list the files and folders in the current working directory (`/home`). The output of this command is `lecture1`.

***path to a directory***
```
[user@sahara ~]$ ls lecture1
Hello.class  Hello.java  messages  README
[user@sahara ~]$
```
This command **does not** output an *error*. Unlike the previous example, this command does provide a path argument to the `ls` command in the form of `lecture1`. As a result, the command outputs a list of the files and folders in the path argument provided (`/lecture1`). The output of this command is `Hello.class  Hello.java  messages  README`.

***path to a file***
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
[user@sahara ~/lecture1]$
```
This command **does not** output an *error* ONLY because of the `cd lecture1` command, which switches the current working directory from `/home` to `/lecture1` before using the `ls Hello.java` command. This is essential for the output (`Hello.java`) because if I did not use the `cd` command to switch the current working directory to `/lecture1`, I WOULD HAVE received an *error* that says `ls: cannot access 'Hello.java': No such file or directory`. Since I did switch the current working directory, the output the command `ls Hello.java` provides is `Hello.java` because it is the only file to list for the path `/Hello.java`.

---
## 'cat' Examples
The command `cat <path1> <path2> ... ` is used to print the contents of one or more files given by the paths

***no arguments***
```
[user@sahara ~]$ cat

^C
[user@sahara ~]$
```
This command was run in the working directory of `/home` and **does** output an *error*. This error is caused because a path is not provided to the `cat` command, and it is essential to provide one or more paths to the `cat` command. As a result, the command gets stuck in an infinite loop and does not produce an output. I used the `^C` command to forcefully terminate the run process because of this *error* produced by the command.

***path to a directory***
```
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
[user@sahara ~]$
```
This command was run in the working directory of `/home` and **does** output an *error*. This error is caused because the path provided to the `cat` command is a directory, and it is essential to provide one or more paths that are files to the `cat` command. As a result, the command outputs an *error* that says `cat: lecture1: Is a directory` as the `cat` command cannot print the contents of a directory, only a file.

***path to a file***
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
[user@sahara ~/lecture1]$
```
This command **does not** output an *error* ONLY because of the `cd lecture1` command, which switches the current working directory from `/home` to `/lecture1` before using the `cat Hello.java` command. This is essential for the output seen above because if I did not use the `cd` command to switch the current working directory to `/lecture1`, I WOULD HAVE received an *error* that says `cat: Hello.java: No such file or directory`. Since I did switch the current working directory, the output seen above contains the contents and code in the `Hello.java` file.

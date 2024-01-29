# Lab Report 1 - Remote Access and FileSystem (Week 1)

## `cd` Examples
The command `cd <path>` represents "Change Directory" and is used to switch the current working directory to the given path

***no arguments***
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd
[user@sahara ~]$ 
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ pwd
/home/lecture1
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1/messages
[user@sahara ~/lecture1/messages]$ pwd
/home/lecture1/messages
[user@sahara ~/lecture1/messages]$ cd
[user@sahara ~]$ pwd
/home
```
This command **does not** output an *error*. When the command `cd` is used without any arguments, it returns the user back to their `/home` directory regardless of what the current working directory is when `cd` with no arguments is called. In the example above, `cd` with no arguments is called from the `/home` directory, the `/home/lecture1` directory, and the `/home/lecture1/messages`, and the command returns the user back to the `/home` directory in all cases as seen when the `pwd` command is used above, which prints the current working directory.

***path to a directory***
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ pwd
/home/lecture1
```
This command **does not** output an *error*. This example switches the current working directory (`/home`) to `/lecture1` because the command includes a directory argument (`lecture1`) that defines which path the current working directory (now `/lecture1`) should switch to. The current working directory changes from `/home` to `/lecture1` as seen in the example above using the `pwd` command which prints the current working directory.

***path to a file***
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ pwd
/home/lecture1
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
[user@sahara ~/lecture1]$ pwd
/home/lecture1
```
This command **does** output an *error*. This example attempts to switch the current working directory (`/lecture1`) to `Hello.java`, but fails because the command includes a file argument instead of a directory argument. The current working directory (`/lecture1`) can only switch to directories, not files, so the command leads to an *error* and the current working directory (`/lecture1`) remains the same as seen with the example above.

---
## `ls` Examples
The command `ls <path>` represents "List" and is used to list the files and folders in a given path

***no arguments***
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ ls
lecture1
[user@sahara ~]$ pwd
/home
```
This command **does not** output an *error*. It is not essential for the `ls` command to have a path argument because the command in this example will list the files and folders in the current working directory (`/home`). The output of this command is `lecture1`.

***path to a directory***
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ ls lecture1
Hello.class  Hello.java  messages  READM
[user@sahara ~]$ pwd
/home
```
This command **does not** output an *error*. The working directory was `/home` when the command was run. Unlike the previous example, the command above does provide a path argument to the `ls` command in the form of `lecture1`. As a result, the command outputs a list of the files and folders in the path argument provided (`/lecture1`). The output of this command is `Hello.class  Hello.java  messages  README`.

***path to a file***
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ ls lecture1/Hello.java
lecture1/Hello.java
[user@sahara ~]$ ls lecture1/messages/hi.txt
lecture1/messages/hi.txt
[user@sahara ~]$ pwd
/home
```
This command **does not** output an *error*. The working directory was `/home` when the command was run. When the `ls` command is run with a relative path to a file as an argument, the output is the same absolute path that was provided as an argument. When I run the `ls` command with the argument `lecture1/Hello.java` the output is the same as the argument (`lecture1/Hello.java`). Similarly when I use the argument `lecture1/messages/hi.txt`, I get `lecture1/messages/hi.txt` as the output.


---
## `cat` Examples
The command `cat <path1> <path2> ... ` is used to print the contents of one or more files given by the paths

***no arguments***
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cat
test
test
     

test2
test2
test3
test3
^C
[user@sahara ~]$ pwd
/home
```
This command was run in the working directory of `/home` and **does not** output an *error*. The output produces an interesting behavior as the command gets stuck in an infinite loop. While in this infinite loop, if you typing something after running the `cat` command, you will receive an output of the same input you provided. For example, when I provided an input of `test` or `test2` as seen above, I immediately received an output of the same input I provided. At the end of the example above, I used the `^C` command to forcefully terminate the run process.

***path to a directory***
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
[user@sahara ~]$ pwd
/home
```
This command was run in the working directory of `/home` and **does** output an *error*. This error is caused because the path provided to the `cat` command is a directory, and it is essential to provide one or more paths that are files to the `cat` command. As a result, the command outputs an *error* that says `cat: lecture1: Is a directory` as the `cat` command cannot print the contents of a directory, only a file.

***path to a file***
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cat lecture1/Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
}[user@sahara ~]$ pwd
/home
```
This command **does not** output an *error*. The working directory was `/home` when the command was run. When the `cat` command is run with a relative path to a file as an argument, the output is the content of the file. When I run the `cat` command with the argument `lecture1/Hello.java` in the example above, the output I received was the code within the `Hello.java` file.

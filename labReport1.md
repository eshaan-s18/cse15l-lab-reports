# Lab Report 1 - Remote Access and FileSystem (Week 1)

## ```cd``` Examples
The command ```cd <path>``` represents "Change Directory" and is used to switch the current working directory to the given path

***no arguments***
```
[user@sahara ~]$ cd
[user@sahara ~]$
```
This command **does not** output an *error*. This example does not switch the current working directory to a given path because it is missing an argument that defines which path the current working directory should switch to, so the current working directory remains the same as before.

***path to a directory***
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
This command **does not** output an *error*. This example switches the current working directory to *lecture1* because the command includes a directory argument (*lecture1*) that defines which path the current working directory should switch to. 

***path to a file***
```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
[user@sahara ~/lecture1]$ 
```
This command **does** output an *error*. This example attempts to switch the current working directory to *Hello.java*, but fails because the command includes a file argument instead of a directory argument. The current working directory can only switch to directories, not files, so the command leads to an error and the current working directory remains the same.

---
## ```ls``` Examples
the command ```ls <path>``` represents "List" and is used to list the files and folders in a given path

# **Cd**
**No Arguments**
```
[user@sahara ~]$ cd
[user@sahara ~]$
```
The working directory was the /home directory. cd is used to change directories, but if no directory is specified, it goes to /home directory. The output is not an error.

**Path to Directory**
   ```
   [user@sahara ~]$ cd /home/lecture1
   [user@sahara ~/lecture1]$
   ```
   The working directory was /home directory. cd is used to change directories and the path specified was to lecture1, therefore we switched to /lecture1. The output is not an error because this is a valid command.

**Path to File**
   ```
 [user@sahara ~]$ cd lecture1/
 [user@sahara ~/lecture1]$ cd Hello.java 
 bash: cd: Hello.java: Not a directory
   ```
 The working directory was /lecture1. cd only changes directories. It cannot change to files. The output is an error because Hello.java (the file specified) is not a directory.

# **ls**
**No Arguments**
```
[user@sahara ~]$ ls
lecture1  wavelet
```
The working directory was /home. ls lists the files and folders inside a directory. We were in /home directory and the folder inside the /home directory was /lecture1. The output is not an error.
  
**Path to Directory**
```
[user@sahara ~]$ ls lecture1/
Hello.class  Hello.java  messages  my-file1.txt  my-file2.txt  README
```
The working directory was /home. ls listed the files and folders inside the /lecture1 directory when we specified that as the path. The output is not an error because /lecture1 was in the /home directory (pwd).

**Path to File**
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ ls Hello.java 
Hello.java
```
The working directory was /lecture1. ls just simply listed the name of the file because the pathname was a file. Since, files do not hold directories or other files, it simply just listed the name of the file again. This resulted in an error that displayed what we input. 

# **cat**
**No Arguments**
   ```
[user@sahara ~/lecture1]$ cat
```
The working directory was /lecture1 directory. cat reads output from file and gives its content as an output. If no argument is given, it simply reads from the standard input. The output is an error as nothing was displayed. 
     
**Path to Directory**
   ```
[user@sahara ~]$ cat lecture1/
cat: lecture1/: Is a directory
```
The working directory was /home directory. /lecture1 is a directory, not a file, therefore, an error was thrown because cat only reads output from files. The output is an error because cat only reads output from files.
     
**Path to File**
```
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
}[user@sahara ~/lecture1]$
```
The working directory was /lecture1. The path specified was a file, so cat read the contents of the file. The output is not an error.

# **Cd**
1. No Arguments
   * ![Image](Capture.PNG)
   * the working directory was home directory 
   * cd is used to change directory, but if no argument is specified, it goes to home directory
   * The output is not an error 

2. Path to Directory
   * ![Image](Cd_With_Argument.PNG)
   * the working directory was home directory
   * cd is used to change directories and the path specified was to lecture1, therefore we switched to lecture1
   * the output is not an error because this is a valid command

3. Path to File
   * ![Image](https://github.com/AKalakota23/cse15l-lab-reports/blob/7c2a8cf45fdfeaa1e1f3962ac4a5d05e92b50ee3/path%20to%20file.png)
   * the working directory was lecture1
   * cd only changes directories. It cannot change to files
   * the output is an error because Hello.java (the file specified) is not a directory

# **ls**
1. No Arguments
   * ![Image](https://github.com/AKalakota23/cse15l-lab-reports/blob/167d66af9d8d72045412ab379b4b54af68296360/ls_no_arguments.png)
   * the working directory was home
   * ls lists the files and folders inside a directory. We were in home directory and the folder inside the home directory was lecture 1
   * the output is not an error
  
2. Path to Directory
   * ![Image](https://github.com/AKalakota23/cse15l-lab-reports/blob/f28d3b6199e82cee273e1d25f63c0966ec5bfc99/ls_path%2Bto_dir.png)
   * the working directory was home
   * ls listed the files and folders inside the lecture1 directory when we specified that as the path
   * the output is not an error because lecture1 was in the home directory (pwd) 

3. Path to File
   * ![Image](https://github.com/AKalakota23/cse15l-lab-reports/blob/be6674a17dce0824cd0ec6b0924c59532cff8bee/ls_path_to_file.png)
   * the working directory was lecture1
   * ls just simply listed the name of the file because the pathname was a file. If we wanted to know more about the file, we would have to use other commands
   * the output is not an error

# **cat**
1. No Arguments
   * ![Image](https://github.com/AKalakota23/cse15l-lab-reports/blob/2280b7c1cacc6189c9e12bedfc0bd3a870bda78b/cat_no_argu.png)
   * the working directory was home directory
   * cat reads output from file and gives its content as an output. If no argument is given, it simply reads from the standard input
   * the output is not an error
     
2. Path to Directory
   * ![Image](https://github.com/AKalakota23/cse15l-lab-reports/blob/c1974d2f66df6c04fc3f42bb889082783b554dcd/cat_path_to_dir.png)
   * the working directory was home directory
   * the directory lecture1 is a directory, not a file. Therefore, an error was thrown because cat only reads output from files
   * the output is an error because cat only reads output from files
     
3. Path to File
   * ![Image](https://github.com/AKalakota23/cse15l-lab-reports/blob/edc431a643ad3783ae43bd7e31cfd350339f5614/cat_path_to_file.png)
   * the working directory was lecture1
   * the path specified was a file, so cat read the contents of the file
   * the output is not an error

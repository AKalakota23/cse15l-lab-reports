# Lab 4

## Steps

![Image](https://github.com/AKalakota23/cse15l-lab-reports/blob/fcd3b54559326360773b19319bd2186fdb56a36e/Screenshot%202023-12-02%20at%206.03.58%20PM.png)

##Log into <ieng6>:

Keys Pressed: `<up>` `<enter>`  
`<up` and `<enter>` was a faster and more convenient way to log into ieng6 as that command was previously used.


##Clone your fork of the repository from your Github account (using the SSH URL):

![Image](https://github.com/AKalakota23/cse15l-lab-reports/blob/c2ee7542c3f31e8562ee126560a33b0cb9155f06/Screenshot%202023-12-02%20at%206.31.05%20PM.png)

Keys Pressed: `<ctrl> r g <enter> `

`<ctrl r` is a fast way to search through the command line recursively in the command history. 

##Run the tests, demonstrating that they fail

![Image](https://github.com/AKalakota23/cse15l-lab-reports/blob/dc3a82799032bd74bb4f022e42286b9c1367c672/Screenshot%202023-12-02%20at%206.55.55%20PM.png)

Keys Pressed: `<up> <up> <up> <enter>` The `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command was 3 up in the search history, so I used the up arrow to access it.
Keys Pressed: `<up> <up> <up> <up> <enter>` Then the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ...` command was 4 up in search history, so I accessed it the same way



Edit the code file to fix the failing test

![Image](https://github.com/AKalakota23/cse15l-lab-reports/blob/128a0604b80433f530f84a66dd307f4533f80f38/Screenshot%202023-12-02%20at%207.03.18%20PM.png)
![Image](https://github.com/AKalakota23/cse15l-lab-reports/blob/fdc5f132cd3f4d2914218ab2863163c747e0d2f2/Screenshot%202023-12-02%20at%207.07.14%20PM.png)

Keys Pressed: `vim <shift> L <tab> . <tab> 43 j e r 2 <shift> : w q <enter>`

We need to use `vim` on the specific file we want to edit and the one we are going to edit is ListExamples.java.  We can type `vim` followed by L and then a `<tab>` to finish the rest of the file name and a . and then another `<tab>` to finish the .java part.


Run the tests, demonstrating that they now succeed

Keys Pressed: `bash t <tab> <enter>`


Commit and push the resulting change to your Github account (you can pick any commit message!)

Keys Presesd: `<ctrl> r g i t c o <enter> g i t p  <enter>`


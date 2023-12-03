# Lab 4

## Steps

<img width="466" alt="Screenshot 2023-12-02 at 6 03 58 PM" src="https://github.com/AKalakota23/cse15l-lab-reports/assets/122422354/37945d8c-5350-4d3f-b339-2eb839b7015e">

##Log into <ieng6>:

Keys Pressed: `<up>` `<enter>`  
`<up` and `<enter>` was a faster and more convenient way to log into ieng6 as that command was previously used.


##Clone your fork of the repository from your Github account (using the SSH URL):

<img width="564" alt="Screenshot 2023-12-02 at 6 31 05 PM" src="https://github.com/AKalakota23/cse15l-lab-reports/assets/122422354/4233952f-2f25-4c55-8121-01904bef304a">

Keys Pressed: `<ctrl> r g <enter> `

`<ctrl r` is a fast way to search through the command line recursively in the command history. 

##Run the tests, demonstrating that they fail

<img width="564" alt="Screenshot 2023-12-02 at 6 55 55 PM" src="https://github.com/AKalakota23/cse15l-lab-reports/assets/122422354/3944ca18-28d0-426a-ba24-59a3ddf9bdd5">

Keys Pressed: `<up> <up> <up> <enter>` The `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command was 3 up in the search history, so I used the up arrow to access it.
Keys Pressed: `<up> <up> <up> <up> <enter>` Then the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ...` command was 4 up in search history, so I accessed it the same way



##Edit the code file to fix the failing test

<img width="404" alt="Screenshot 2023-12-02 at 7 03 18 PM" src="https://github.com/AKalakota23/cse15l-lab-reports/assets/122422354/f89bea0d-e115-4224-84a4-7d418ca9dc86">
<img width="345" alt="Screenshot 2023-12-02 at 7 07 14 PM" src="https://github.com/AKalakota23/cse15l-lab-reports/assets/122422354/77afde5b-6bb5-4c9a-a36e-8a88365711a7">

Keys Pressed: `vim <shift> L <tab> . <tab> 43 j e r 2 <shift> : w q <enter>`

We need to use `vim` on the specific file we want to edit and the one we are going to edit is ListExamples.java.  We can type `vim` followed by L and then a `<tab>` to finish the rest of the file name and a . and then another `<tab>` to finish the .java part.


##Run the tests, demonstrating that they now succeed

<img width="357" alt="Screenshot 2023-12-02 at 7 11 32 PM" src="https://github.com/AKalakota23/cse15l-lab-reports/assets/122422354/a1073c80-8997-4c69-b8f8-7c8a9c18969d">

Keys Pressed: `bash t <tab> <enter>`

I entered bash and then t followed by a `<tab>` to quickly fill in the rest of the file name and then `<enter>`.

##Commit and push the resulting change to your Github account (you can pick any commit message!)

<img width="564" alt="Screenshot 2023-12-02 at 7 17 16 PM" src="https://github.com/AKalakota23/cse15l-lab-reports/assets/122422354/ee2f1249-f746-45ad-807c-b95081012bbf">

Keys Presesd: `<ctrl> r g i t c o <enter> g i t p  <enter>`

I used `<ctrl> r` to recursively search through the command history to find `git commit` and `git push`. I didn't have to type out the whole thing as the rest of the command would appear. I then pressed `<enter>` following the git commands. 

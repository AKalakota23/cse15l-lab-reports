#Lab Report 5

#1. The original post from a student with a screenshot showing a symptom and a description of a guess at the bug/some sense of what the failure-inducing input is. (Don’t actually make the post! Just write the content that would go in such a post)

Student (Afraz): Hi Akhil! I am having trouble with my code and would like you to take a look at it. Sincerely, Afraz.

```
    int index1 = 0, index2 = 0;
    while(index1 < list1.length() && index2 < list2.length()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.length()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.length()) {
      result.add(list2.get(index2));
      // change index1 below to index2 to fix test
      index2+= 1;
    }
    return result;
  }


}
                                                                                           39,18         Bot
```
<img width="564" alt="Screenshot 2023-12-03 at 6 48 00 PM" src="https://github.com/AKalakota23/cse15l-lab-reports/assets/122422354/2e90f3c3-59df-4dd1-8f68-5614916d067e">

Student (Afraz): What I am thinking is that the issue has to be do with list1 and list2 has the output in the terminal is showing that they cannot find the correct symbol.

#2. A response from a TA asking a leading question or suggesting a command to try (To be clear, you are mimicking a TA here.)

Akhil TA: Hi Afraz, what data structure do you think list1 and list2 are? Try taking a look to see how they are instantiated to determine what data structure they are and what the correct corresponding method is.

Student (Afraz): Oh okay! It appears that list1 and list2 are arraylists of type String. I looked it up and the correct method to use on arraylist is .size() in order to get the length of the arraylist. I will try that out and let you know what I got.

Student: It ended up working!

#3. Another screenshot/terminal output showing what information the student got from trying that, and a clear description of what the bug is.

<img width="232" alt="Screenshot 2023-12-03 at 7 00 45 PM" src="https://github.com/AKalakota23/cse15l-lab-reports/assets/122422354/bd99acdb-0a40-4cb8-a726-2afaeb2f0f1a">

The bug in this case was that the student assumed that list1 and list2 were arrays and therefore used .length() method to receive the size of the array. However, list1 and list2 were arraylists and therefore would require to use of .size() method in order to grab the size.

#4. At the end, all the information needed about the setup including:
The file & directory structure needed
The contents of each file before fixing the bug
The full command line (or lines) you ran to trigger the bug
A description of what to edit to fix the bug

File and directroy structure needed: ListExamples.java and test.sh have to be in the same directory with the ListExamplesTests.java. 

The contents of each file before fixing the bug:

In `test.sh`

`javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`

In `ListExamples.java`
```
import java.util.ArrayList;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(s);
      }
    }
    return result;
  }


  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        index1 += 1;
        result.add(list1.get(index1));
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index2 += 1;
    }
    return result;
  }


}
```
To fix the bug, you need to change the list1.length() and list2.length() to list1.size() and list2.size() because they are arraylists and .size() are the appropriate methods to use. 

#Part 2 Reflection


During the second half of the quarter, I delved into the intricacies of Vim, command line operations, and bash scripting in the lab. I discovered efficient text editing techniques in Vim, mastered command line navigation and file manipulation, and gained proficiency in creating automated scripts using bash, significantly enhancing my overall command-line skills and productivity. Vim's xtensive features provide a fast and effective way to manipulate text, making it a valuable skill for programming and editing configuration files. Command line proficiency is essential for navigating and manipulating files and directories swiftly. Bash scripting, in particular, allows for the creation of custom automation scripts, which helps enhance productivity.



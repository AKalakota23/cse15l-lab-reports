# Part 1 - Bugs
ArrayExamples.java `reverseInPlace` method

Failure Inducing Input:
```
@Test 
  public void test2ReverseInPlace(){
    int[] input2 = {2,4};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{4,2}, input2);
  }
```
Non-Failure Inducing Input:
```
@Test 
  public void test2ReverseInPlace(){
    int[] input2 = {4};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{4}, input2);
  }
```
Symptoms:

Failure Inducing Input:
![Image](https://github.com/AKalakota23/cse15l-lab-reports/blob/6556ea41eacdc21c2e03b23e85cf34e172a74e03/Screenshot%202023-11-04%20at%203.35.26%20PM.png)

Non-Failure Inducing Input:
![Image](https://github.com/AKalakota23/cse15l-lab-reports/blob/546163f79d7fc05d81e6b11e52c7546d170323a0/Screenshot%202023-11-04%20at%203.38.24%20PM.png)

Bugged Code:
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

Fixed Code:
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1]; 
      arr[arr.length-i-1] = temp;
    }
    
  }
```
This fix addresses the issue because it ensures each element is swapped without being overwritten through the use of a temp integer. The first element is swapped with the last element. The second element is swapped with the last minus 1 and so on. We do this until we reach the midpoint.  

# Part 2 - Researching Commands
Chosen Command: `Less`

## Searching with Less Command:

Input:
```
/research
```
Output: 
```
technical/biomed/gb-2000-1-1-research002.txt
technical/biomed/gb-2000-1-2-research0003.txt
technical/biomed/gb-2001-2-10-research0041.txt
technical/biomed/gb-2001-2-10-research0042.txt
technical/biomed/gb-2001-2-11-research0045.txt
technical/biomed/gb-2001-2-11-research0046.txt
technical/biomed/gb-2001-2-12-research0051.txt
technical/biomed/gb-2001-2-12-research0053.txt
technical/biomed/gb-2001-2-12-research0054.txt
technical/biomed/gb-2001-2-12-research0055.txt
technical/biomed/gb-2001-2-2-research0004.txt
technical/biomed/gb-2001-2-3-research0007.txt
```
This specific input is indexing all the places where "research" is included. This is pretty useful when wanting to search for a specific pattern in a directory.

Input:
```
?pmed
```

Output:
```
technical/plos/pmed.0020237.txt
technical/plos/pmed.0020238.txt
technical/plos/pmed.0020239.txt
technical/plos/pmed.0020242.txt
technical/plos/pmed.0020246.txt
technical/plos/pmed.0020247.txt
technical/plos/pmed.0020249.txt
technical/plos/pmed.0020257.txt
technical/plos/pmed.0020258.txt
technical/plos/pmed.0020268.txt
technical/plos/pmed.0020272.txt
technical/plos/pmed.0020273.txt
technical/plos/pmed.0020274.txt
technical/plos/pmed.0020275.txt
technical/plos/pmed.0020278.txt
technical/plos/pmed.0020281.txt
~
~
~
~
~
~
~
~
```
This is useful if you want to quickly find a pattern within a directory as it will execute a forward search from your current location to the first found match. The matches are also highlighed which makes it easy to spot. If you wanted to execute a backwards search, you can use `?` instead of a `/`. 

Source: https://linuxhandbook.com/less-command/

## Setting Marks with Less:

Input:
```
ma (press 'm' followed by a letter to set a mark)

'a (press ' followed by the marked letter to go to marked section)
```

Output:
```
VISION FOR SUCCESS
After prioritizing their primary issues, conferees then listed
indicators by which success in achieving diverse communities of
justice could be defined. Indicators are grouped by topic and
summarized by theme.
Leadership
Indicators of success -- Our senior management includes more
women, gays, lesbians, people of color, older people and people
with disabilities. Leaders are held accountable for progress in
meeting goals that ensure our programs and state justice
communities are diverse throughout, maintaining a "glittering
mosaic." From novel power-sharing arrangements, new leaders and
leadership models emerge. Local and national initiatives are
established to nurture and promote them.
Program Boards
Indicators of success --Boards contain representatives from a
greater variety of groups. National, state and local program boards
reflect the diversity of the communities they serve.
State Justice Communities
Indicators of success --We endorse a common vision of diversity
and goal for achievement on the national, state and local levels,
```
This input works by adding marks to any line and when you press ' followed by the marked letter, you are sent back to the marked line. In this case, we are using "a" as the marked letter and using it to go back to the position we marked.

Input:
```
mb

'b
```

Output:
```
Indicators of success --Boards contain representatives from a
greater variety of groups. National, state and local program boards
reflect the diversity of the communities they serve.
State Justice Communities
Indicators of success --We endorse a common vision of diversity
and goal for achievement on the national, state and local levels,
```

This is pretty useful if you come across something interesting when you are reading a file and want to remember where it was. It works by adding marks to any line and when you press ' followed by the marked letter, you are sent back to the marked line. 

Source: https://linuxhandbook.com/less-command/

## Viewing Multiple Files with Less:

Input:
```
less diversity_priorities.txt comission_report.txt
```

Output:
```

OVERVIEW
On May 31 and June 1, 2001, approximately fifty equal justice
advocates gathered in Washington, DC for LSC's and NLADA's first
national conference on diversity in the legal services community.
Focusing on broad aspects of diversity - including, among others,
age, gender, disability, sexual orientation, race, ethnicity and
national origin - participants examined diversity-related strengths
and challenges facing clients, staff and program leaders (both
local and national), and brainstormed about potential strategies
for addressing the challenges. To ensure that the dialogue would
include the variety of issues and individuals in the legal services
community, NLADA and LSC selected participants to reflect both the
leadership and emerging leadership of the field. To the maximum
extent possible, participants broadly mirrored the full population
of the national community. Attendance at the meeting was limited to
about 50 people to foster candid conversation. Two members of the
Karp Consulting Group (Deborah Howard and Yvonne Shinhoster Lamb)
facilitated the two-day session.
All participants understood that, while the assembled group
reflected the demographics of the community, they did not speak for
every member of the broad-based legal services community. It should
be noted also that no clients were involved in this event. Thus the
vision and strategies suggested here must be seen and considered in
the context of a series of dialogues on diversity that NLADA and
LSC are holding throughout the year and in the context of the
diversity_priorities.txt (file 1 of 2)
```
This allows us to view both files in one terminal. The chosen parameters are the files you want to see and it works by typing out "less" followed by the files you want to view. This is useful if you want to look at more than one file in a terminal from a directory.

Input:
```
less CONFIG_STANDARDS.txt Progress_report.txt
```

Output:
```
STATE PLANNING CONFIGURATION STANDARDS Final Task Force Report
- Board Approved
November 2001
LEGAL SERVICES CORPORATION


STATE PLANNING CONFIGURATION STANDARDS
Final Task Force Report - Board Approved

I. PREFACE
This document-- Legal Services Corporation State Planning
Configuration Standards -- presents in one place a comprehensive
compilation of the standards LSC recipients and Designated State
Planning Bodies (DSPB's)1 should consider and that the Legal
Services Corporation will use in considering the configuration of a
state's legal services delivery system.2
Determination of the most appropriate configuration of programs
in a given state is a part of the broader state planning process
and cannot be divorced from consideration of the overall goals of
the state delivery system, the state's past performance, current
status, and progress towards and plans for achieving those goals.
The Legal Services Corporation expects its grantees in each state
and territory to work with one another and with a broad spectrum of
other equal justice stakeholders3 to develop comprehensive,
integrated statewide civil legal services delivery systems which
are responsive to the most compelling needs of eligible clients and
client communities, ensure the highest and most strategic use of
all available resources, maximize the opportunity for clients
throughout the state to receive timely, effective and appropriate
legal services in the present and in the future, and operate
efficiently and effectively.4
1 A "Designated State Planning Body" is an entity that has been
established and charged with responsibility for coordinating state
legal services delivery planning. Such planning entities are
CONFIG_STANDARDS.txt (file 1 of 2)
```

If you input the file names one by one, it lists the file name along with its position in the list of files. This is pretty useful if you want to open and view multiple files with less.

Source: https://linuxhandbook.com/less-command/

## Displaying Line Numbers with Less

Input:
```
less CONFIG_STANDARDS.txt
-N
```

Output:
```
      1 
      2 
      3 
      4 
      5 STATE PLANNING CONFIGURATION STANDARDS Final Task Force Report
      6 - Board Approved
      7 November 2001
      8 LEGAL SERVICES CORPORATION
      9 
     10 
     11 STATE PLANNING CONFIGURATION STANDARDS
     12 Final Task Force Report - Board Approved
     13 
     14 I. PREFACE
     15 This document-- Legal Services Corporation State Planning
     16 Configuration Standards -- presents in one place a comprehensive
     17 compilation of the standards LSC recipients and Designated State
     18 Planning Bodies (DSPB's)1 should consider and that the Legal
     19 Services Corporation will use in considering the configuration of a
     20 state's legal services delivery system.2
     21 Determination of the most appropriate configuration of programs
     22 in a given state is a part of the broader state planning process
     23 and cannot be divorced from consideration of the overall goals of
     24 the state delivery system, the state's past performance, current
```
The -N command is printing the number of lines in CONFIG_STANDARDS.txt. This is pretty useful if you want to guage the length of the contents of a file through the usage of the number of lines.

Input:
```
less Progress_report.txt
-N
```

Output:
```
      1 
      2 
      3 
      4 
      5 MEMORANDUM
      6 TO: LSC Board of Directors FROM: Randi Youells, Vice President
      7 for Programs DATE: January 8, 2002 SUBJECT: Strategic Directions
      8 2000-2005
      9 I am pleased to submit to you our report concerning the progress
     10 of the programs' units and offices-primarily OPP and the State
     11 Planning Team with some statistical and reporting assistance from
     12 OIM-in terms of meeting the goals and objectives of your strategic
     13 planning document, Strategic Directions 2000-2005.
     14 I would like to put this report in its proper perspective. We
     15 are all acutely aware that our civil legal services delivery system
     16 is strained to the breaking point. Legal services programs
     17 nationally have been battered by economic pressures and escalating
```

The -N command with less essentially prints the number of lines in the reader. This is pretty useful if you want to know the number of lines there are when perusing through the file with less command. 

Source: https://www.computerhope.com/unix/uless.htm?ref=linuxhandbook.com

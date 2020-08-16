# Lab10 Guide
## Getting Started

Please watch the Lab10 Walkthough Video.

## Lab Warmup - Parsing strings
### Problem Description
<br />
1. Prompt the user for a string that contains two strings separated by a comma. 

- Examples of strings that can be accepted:
   - Jill, Allen
   - Jill , Allen
   - Jill,Allen
<br />

Ex:
```
Enter input string:
Jill, Allen
```
<br />
2. Report an error if the input string does not contain a comma. Continue to prompt until a valid string is entered. 

*Note: If the input contains a comma, then assume that the input also contains two strings.* 
<br /><br />
Ex:
```
Enter input string:
Jill Allen
Error: No comma in string.

Enter input string:
Jill, Allen
```
<br />
3. Extract the two words from the input string and remove any spaces. Store the strings in two separate variables and output the strings. 
<br /><br />

Ex:
```
Enter input string:
Jill, Allen
First word: Jill
Second word: Allen
```
<br />
4. Using a loop, extend the program to handle multiple lines of input. Continue until the user enters q to quit.  
<br /><br />

Ex:
```
Enter input string:
Jill, Allen
First word: Jill
Second word: Allen

Enter input string:
Golden , Monkey
First word: Golden
Second word: Monkey

Enter input string:
Washington,DC
First word: Washington
Second word: DC

Enter input string:
q
```


### Implementation Guide
1. Expand the folder named LabWarmup and open the file named main.c
2. Enter the program code to create an application as described in the Problem Description.
3. Test the program using to ensure it functions as expected.
4. Commit the changes to your local repository with a message stating that LabWarmup is completed.
5. Push the changes from your local repository to the github classroom repository.
6. Update the Coding Journal with an entry describing your experience using the steps outlined below.


## Lab Activity
### Problem Description
<br />
1. Prompt the user for a title for data. Output the title. 
<br /><br />

Ex:
```
Enter a title for the data:
Number of Novels Authored
You entered: Number of Novels Authored
```
<br />
2. Prompt the user for the headers of two columns of a table. Output the column headers. 
<br /><br />

Ex:
```
Enter the column 1 header:
Author name
You entered: Author name

Enter the column 2 header:
Number of novels
You entered: Number of novels
```
<br />
3. Prompt the user for data points. Data points must be in this format: *string, int*. Store the information before the comma into a string variable and the information after the comma into an integer. The user will enter `-1` when they have finished entering data points. Output the data points. Store the string components of the data points in an array of strings. Store the integer components of the data points in an array of integers. 
<br /><br />

Ex:
```
Enter a data point (-1 to stop input):
Jane Austen, 6
Data string: Jane Austen
Data integer: 6
```
<br />
4. Perform error checking for the data point entries. If any of the following errors occurs, output the appropriate error message and prompt again for a valid data point.

- If entry has no comma
   - Output: `Error: No comma in string.` 
- If entry has more than one comma
   - Output: `Error: Too many commas in input.`
- If entry after the comma is not an integer
   - Output: `Error: Comma not followed by an integer.` 

<br />

Ex:
```
Enter a data point (-1 to stop input):
Ernest Hemingway 9
Error: No comma in string.

Enter a data point (-1 to stop input):
Ernest, Hemingway, 9
Error: Too many commas in input.

Enter a data point (-1 to stop input):
Ernest Hemingway, nine
Error: Comma not followed by an integer.

Enter a data point (-1 to stop input):
Ernest Hemingway, 9
Data string: Ernest Hemingway
Data integer: 9
```
<br />
5. Output the information in a formatted table. The title is right justified with a width of 33. Column 1 has a width of 20. Column 2 has a width of 23. 
<br /><br />

Ex:
```
        Number of Novels Authored
Author name         |       Number of novels
--------------------------------------------
Jane Austen         |                      6
Charles Dickens     |                     20
Ernest Hemingway    |                      9
Jack Kerouac        |                     22
F. Scott Fitzgerald |                      8
Mary Shelley        |                      7
Charlotte Bronte    |                      5
Mark Twain          |                     11
Agatha Christie     |                     73
Ian Flemming        |                     14
J.K. Rowling        |                     14
Stephen King        |                     54
Oscar Wilde         |                      1
```
<br />
6. Output the information as a formatted histogram. Each name is right justified with a width of 20. 
<br /><br />

Ex:
```
         Jane Austen ******
     Charles Dickens ********************
    Ernest Hemingway *********
        Jack Kerouac **********************
 F. Scott Fitzgerald ********
        Mary Shelley *******
    Charlotte Bronte *****
          Mark Twain ***********
     Agatha Christie *************************************************************************
        Ian Flemming **************
        J.K. Rowling **************
        Stephen King ******************************************************
         Oscar Wilde *
```

### Implementation Guide
1. Expand the folder named LabActivity and open the file named main.c
2. Enter the program code to create an application as described in the Problem Description.
3. Test the program using to ensure it functions as expected.
4. Commit the changes to your local repository with a message stating that LabActivity is completed.
5. Push the changes from your local repository to the github classroom repository.
6. Update the Coding Journal with an entry describing your experience using the steps outlined below.

## Coding Journal
Keep a journal of your activities as you work on this lab. Many of the best engineers that I have worked with professionally have kept some sort of engineering journal. I personally packed notebooks around with me for nearly 8 years before I began keeping my notes electronically.   

Your journal can track ideas, bugs, cool links, code snippets, shell commands, rants, or simply a reflection on what worked well or not-so-well with this lab activity. I will not be grading the content of your journal, but I will expect at least two date-stamped journal entries of at least a paragraph each added to the provided Journal.md file.

### Implementation Details
1. Add an entry to the provided Journal.md located in the CodingJournal folder, formatted using markdown notation. You can find a reference at the bottom of this guide.

2. Commit the changes to your local repository with a message stating an entry has been added to the journal.
3. Push the changes from your local repository to the github classroom repository.
4. Repeat for reach additional journal entry
## Markdown Resources
Markdown is a notation that is used to format text documents.  It is widely used in Software Development shops around the world, which is why we're asking you to use it in your lab documentation.  

Github provides a guide for getting started:  [Mastering Markdown](https://guides.github.com/features/mastering-markdown/)
# Lab10 Guide
## Getting Started

Please watch the [Lab10 Walkthough Video](https://www.youtube.com/playlist?list=PLvnIObHoMl8cLxjfgsSf5C8T4gcaArdBL).

### Code Style Requirements
Please review the [CS253 Style Guide](https://docs.google.com/document/d/1zKIpNfkiPpDHEvbx8XSkZbUEUlpt8rnZjkhCSvM-_3A/edit?usp=sharing) and apply it in all lab warmups, lab activities and projects this semester. Coding Style will assessed as part of your lab and project grades.

### Code Quality Requirements
- Code must compile without warnings using the provided Makefile
- Programs must handle unexpected user input and either reprompt (loops) or gracefully exit with a non-zero exit status.
- Programs must handle error conditions gracefully, without crashing, ideally by checking function returns codes (if available) and returning a non-zero exit status.
- Programs should be free of memory related errors, buffer overflows, stack smashing, leaks, etc... Whether the program crashes or not. This will be validated using valgrind.

## Lab Warmup - Playlist Builder
### Problem Description
Playlist Builder is an application that allows the user to specify a CSV file containing song data and a number of songs on the commandline.  The application will open the CSV, load the specified number of songs from the CSV file into a dynamically allocated array of the specified size, sort the songs in the array based upon their duration, then display the list of songs in the console.

<br />
1. Carefully study the Song header file (Song.h)
<br /><br />
The Song struct as well as function declarations for the related functions described below have been provided in Song.h. Please do not modify the provided Song.h file. Details regarding each function as well as expected return values are included in the comments associated with each function declaration in Song.h. The following is a summary of this content:

- Data members
  - char artist[40];
  - char album[40];
  - char title[40];
  - int duration;
- Related functions
  - Song * CreateSong(const char artist[], const char album[], const char title[], int duration)  
  - int CompareSong(Song * thisSong, Song * thatSong)  
  - void PrintSong(Song * thisSong)
  - void DestroySong(Song * thisSong)
  
<br />
2. Process the command-line arguments passed into main(), validate the correct number of values are passed in, dynamically create a songlist array of the specified size and finally, open the specified file.  Handle any errors that occur by displaying a helpful error message and then exit with a non-zero exit status. 

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
3. Iterate through each line in the specified input CSV file, extracting song fields from each line as shown in the CSVParser example, adding each song to the songlist. If the songlist fills up before reaching the of the CSV file, stop processing the CSV file and display a message specifying that the requested number of songs have been successfully loaded.  If the end of the CSV file is reached before loading the requested number of songs, display a message specifying that only n songs were loaded.
<br /><br />

Ex:
```
Enter input string:
Jill, Allen
First word: Jill
Second word: Allen
```
<br />
4. Use qsort() and the CompareSong() function to sort the songlist array.
<br /><br />


<br />
5. Iterate through the sorted songlist and display each song in the console using the PrintSong() function. Verify that the songs are displayed in ascending order
<br /><br />


<br />
6. Release allocated memory. Iterate through the songlist, freeing each Song by calling the DestroySong() function. Then free the songlist.  Also make certain to close any files that were opened.
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
1. Expand the folder named LabWarmup and open the files named Song.h, Song.c and main.c
2. Enter the program code to create an application as described in the Problem Description.
3. Test the program to ensure it functions as expected.
4. Run the program with valgrind to catch any memory leaks or errors
5. Commit the changes to your local repository with a message stating that LabWarmup is completed.
6. Push the changes from your local repository to the github classroom repository.
7. Update the Coding Journal with an entry describing your experience using the steps outlined below.


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

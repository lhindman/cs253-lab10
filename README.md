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

```
<br />
3. Iterate through each line in the specified input CSV file, extracting song fields from each line as shown in the CSVParser example, adding each song to the songlist. If the songlist fills up before reaching the of the CSV file, stop processing the CSV file and display a message specifying that the requested number of songs have been successfully loaded.  If the end of the CSV file is reached before loading the requested number of songs, display a message specifying that only n songs were loaded.
<br /><br />

Ex:
```

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

```


### Implementation Guide
1. Expand the folder named LabWarmup and open the files named Song.h, Song.c and main.c
2. Enter the program code to create an application as described in the Problem Description.
3. Test the program to ensure it functions as expected.
4. Run the program with valgrind to catch any memory leaks or errors
5. Commit the changes to your local repository with a message stating that LabWarmup is completed.
6. Push the changes from your local repository to the github classroom repository.
7. Update the Coding Journal with an entry describing your experience using the steps outlined below.


## Lab Activity - Gradebook
### Problem Description
Gradebook is an adaptation of a CS121 project used to demonstrate processing CSV files as well as working with ArrayLists and is revisited when we discuss Arrays.  This version of the Gradebook application allows the user to specify a CSV file containing student grade data command-line.  The application will open the CSV, load the grades from the CSV file into a dynamically allocated array. The array will initially be allocated to hold a max of 8 student grades, but will grow as needed by doubling its size each time. Once the grade data has been loaded from the CSV file, the grades array will be sorted based upon score, then displayed in the console. 
<br />
1. Carefully study the StudentGrader header file (StudentGrade.h)
<br /><br />
The StudentGrade struct as well as function declarations for the related functions described below have been provided in StudentGrade.h. Please do not modify the provided StudentGrade.h file. Details regarding each function as well as expected return values are included in the comments associated with each function declaration in StudentGrade.h. The following is a summary of this content:

- Data members
  - char lastname[20];
  - char firstname[20];
  - int id;
  - int score;
- Related functions
  - StudentGrade * CreateStudentGrade(const char lastname[], const char firstname[], int id, int score)  
  - int CompareStudentGrade(StudentGrade * thisSG, StudentGrade * thatSG)  
  - void PrintStudentGrade(StudentGrade * thisSG)
  - void DestroyStudentGrade(StudentGrade * thisSG)

Ex:
```

```
<br />
2. Process the command-line arguments passed into main(), validate the correct number of values are passed in, dynamically create a gradebook array to hold 8 StudentGrade pointers and finally, open the specified file.  Handle any errors that occur by displaying a helpful error message and then exit with a non-zero exit status. 
<br /><br />

Ex:
```

```
<br />
3. Iterate through each line in the specified input CSV file, extracting song fields from each line as shown in the CSVParser example, adding each StudentGrade to the gradebook. If the gradebook fills up before reaching the of the CSV file, grow the gradebook by doubling its size as shown in the SampleDataProcessing example. When the end of the CSV file is reached display a message specifying the number of StudentGrades that were successfully loaded.
<br /><br />

Ex:
```

```
<br />
4. Use qsort() and the CompareSong() function to sort the gradebook array.
<br /><br />

Ex:
```

```
<br />
5. Iterate through the sorted gradebook and display each StudentGrade in the console using the PrintStudentGrade() function. Verify that the StudentGrades are displayed in ascending order
<br /><br />

<br />
6. Release allocated memory. Iterate through the songlist, freeing each Song by calling the DestroySong() function. Then free the songlist.  Also make certain to close any files that were opened.
<br /><br />


Ex:
```

```

### Implementation Guide
1. Expand the folder named LabWarmup and open the files named StudentGrade.h, StudentGrade.c and main.c
2. Enter the program code to create an application as described in the Problem Description.
3. Test the program to ensure it functions as expected.
4. Run the program with valgrind to catch any memory leaks or errors
5. Commit the changes to your local repository with a message stating that LabWarmup is completed.
6. Push the changes from your local repository to the github classroom repository.
7. Update the Coding Journal with an entry describing your experience using the steps outlined below.

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

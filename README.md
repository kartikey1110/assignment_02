# CITS\_4407 Assignment 02

## Description

This project contains 2 scripts called clean and analyse.
Both the scripts are bash scripts and include gawk scripts inside.

### clean

This script reads a csv file, filters out rows with incomplete data and outputs it to a csv file. Following are details of the script:

* The input csv file is passed as an argument to the script.
* It performs following safety checks on the file:
1. Input file provided as argument.
2. Provided file exists in same directory as script.
3. Provided file is in csv format.
4. Provided file is not empty.
5. CSV file has 7 columns in header.

* The script expects csv file to follow specific column order mentioned below:
1. video\_id
2. publish\_date
3. views
4. likes
5. dislikes
6. comments\_disabled
7. ratings\_disabled

* It performs following data transformation steps:

1. Removes column ratings\_disabled.
2. Converts publish\_date data from timestamp to date.
3. Deletes rows which do not have same number of columns as header.
4. Deletes rows without video\_id.
5. Deletes duplicate rows
6. Deletes rows with 0 number of likes or dislikes.

* The script outputs the remaining rows to a file called trending\_videos\_clean.csv.

### analyse

This script reads data from the output file of script "clean"(see above) and performs few analysis tasks on the data. Following are the details of the script:

* The input csv file is passed as an argument to the script.
* It performs following safety checks on the file:

1. Input file provided as argument.
2. Provided file exists in same directory as script.
3. Provided file is in csv format.
4. Provided file is not empty.

* The script expects csv file to follow specific column order mentioned below:

1. video\_id
2. publish\_date
3. views
4. likes
5. dislikes
6. comments\_disabled

* It performs following analysis on the data:

1. Print the video\_id of the video that has the most number of occurrences in the data.
2. Print the mean number of views.
3. Print the video\_id of the video with the maximum number of dislikes.
4. Print the video\_id and the publish\_date of the video that contains the highest engagement rate, which is an indicator of how actively the viewers react. The engagement rate is calculated as: (likes + dislikes)/views.
5. Print the video\_id and the publish\_date of the video that contains the least net sentiment rate, which determines if the overall reception is positive or negative. The net sentiment rate is calculated as: (likes - dislikes)/views.



## Usage

* Firstly place the file "trending\_videos\_unclean.csv" in the same directory.
* Run the script clean using command - ./clean trending\_videos\_unclean.csv
* Run the script analyse using command - ./analyse trending\_videos\_clean.csv


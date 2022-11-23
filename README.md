# Election_analysis

## Overview of Election Audit
## Purpose
Tom, our client for this project, is an employee of the Colorado Board of Elections. He has requested assistance to write an algorithm that will automatically analyze local election results. The goal of this project is to 1.) confirm the voting results of the election and 2.) create a script that can be scaled beyond this single election to other congressional and senate district election results. In order to successfully certify the election results, the script was written to produce the following the following necessary information: 

1. Calculate the total number of votes cast.
2. Get a complete list of candidates who received votes.
3. Calculate the total number of votes each candidate received.
4. Calculate the percentage of votes each candidate won.
5. Determine the winner of the election based on popular vote.
6. Calculate the voter turnout for each county
7. Generate the percentage of votes each county contributes to the total number of votes in the precinct
8. Determine the county with the highest voter turnout.

^ Goals generated using information provided from module activity 3.6.5

## Resources
- Data Source: election_results.csv
- Software: Python 3.9.13, Visual Studio Code

## Election Audit Results
The analysis of the election show that:
- **There were 369,711 total votes cast in the local election**.

The total vote count was calculated by looping through the rows and continuing to add the number of votes in each row to the total value. First, I created a "total_votes" variable and initialized it to start at zero.

<img width="317" alt="image" src="https://user-images.githubusercontent.com/114873837/203384879-453d64cb-c174-4826-a48b-cf076fc362be.png">

After setting up a for loop, I included a section of code that would read and add the value of the votes from the list of dictionaries representing each row until the end of the list was reached.
<img width="427" alt="image" src="https://user-images.githubusercontent.com/114873837/203385287-a8b84b11-1bac-4d9a-ba14-46b7ae98a4a1.png">

To place the number of total votes in an output table that could be printed to the terminal and written to the text file, I included the "total_votes" value (that had been calculated in the for loop) in a series of f strings that produced the table format and contents.  

<img width="464" alt="image" src="https://user-images.githubusercontent.com/114873837/203386057-7e724a5e-36b7-485c-bdcd-cd827f886cc5.png">


- **The following table breaks down the total number of votes cast in each county, as well as their percentage of the total votes in the election**.

<img width="215" alt="image" src="https://user-images.githubusercontent.com/114873837/203383342-1f0315cd-b369-48c6-83ad-e4ece43329ce.png">

This table was produced by first generating a list of counties that should be included in the analysis. I wrote a conditional statement to search for the county name in each row (in the index 1 placement) and if the county name did not already exist in the list of counties, it was then added to the list with an initial vote count of zero until the list was complete for all rows in the csv file. 

<img width="503" alt="image" src="https://user-images.githubusercontent.com/114873837/203613818-b3a31079-a0aa-4758-9608-9612150e48fe.png">

Then the following statement was added to the existing for loop reading all rows. It looks to add the vote count to the existing county's dictionary of vote values.

<img width="421" alt="image" src="https://user-images.githubusercontent.com/114873837/203615049-a2ef99bd-05e3-4c59-a0a4-4e4c83f172f7.png">

Then I assigned a variable to tally the total vote count for each county.

<img width="443" alt="image" src="https://user-images.githubusercontent.com/114873837/203617445-15718458-34b6-42ce-b994-047b48be8bbd.png">

After all of the counties are listed and the vote counts tabulated, the last piece of information for the output table is the percentage of the total votes represented by each county's turnout. I created a new variable to capture the calculation of county votes divided by total votes multiplied by 100, which generates the percentage of the total.

<img width="464" alt="image" src="https://user-images.githubusercontent.com/114873837/203615840-75ed5015-4896-4354-b62e-0fab5da7bc06.png">


To place the county results in an output table that could be printed to the terminal and written to the text file, I structured a series of f strings to fill in the values of the county name, county percentage, and county vote totals. Because this code is within the for loop, the output of results is repeated for each county, resulting in three lines for the output table. 

<img width="600" alt="image" src="https://user-images.githubusercontent.com/114873837/203388252-9b74af2e-f2d2-4de8-b310-09a76236bfb1.png">


- **From the above output, we can see that the county with the largest number of votes was Denver**, with a total vote count of 306,055, which was 82.8% of the total ballots cast across the precinct.

To confirm this result, I included a piece of code that would automatically produce the county with the largest county turnout. First, prior to the for loop, I initialized variables to represent the largest county (largest_county), a string, and the largest number of votes (most_county_votes), an integer set to zero. 

<img width="513" alt="image" src="https://user-images.githubusercontent.com/114873837/203618417-a6929b88-882c-4ec8-8906-b0a413ea0b0f.png">

Next, I created a for loop "for county_name in county_votes" to loop through the county votes dictionary to retrieve the vote count for each county. Within the for loop, I wrote a conditional if statement - If the vote count for the county was greater than the current value of "most_county_votes", then the current county becomes the largest county with the most county votes.

<img width="642" alt="image" src="https://user-images.githubusercontent.com/114873837/203618861-48819ca8-25ad-4e21-91dc-64cb06e7594b.png">

To place the largest county results in an output table that could be printed to the terminal and written to the text file, I structured a series of f strings to fill in the values of the largest county name.

<img width="561" alt="image" src="https://user-images.githubusercontent.com/114873837/203620871-ed73352c-94c6-49ed-885d-08fdcbedf07a.png">

- **The candidates included: Charles Casper Stockham, Diana DeGette, and Raymon Anthony Doane**
  
Much like the process of generating the list of all counties, this list was generated by looping through each candidate name in the dictionary of rows and adding any candidate name that was new to the list. 

<img width="519" alt="image" src="https://user-images.githubusercontent.com/114873837/203621424-52e6141a-9802-4a85-8f5d-a12abed78e03.png">

 - **The following table breaks down the total vote count and percentage of votes for each candidate:**
 
 <img width="320" alt="image" src="https://user-images.githubusercontent.com/114873837/203604377-706130f2-6b2a-4e3a-96cd-12445e874643.png">

This table was produced by first compiling the list of candidate names as described above. Then the following statement was added to the existing for loop reading all rows. It looks to add the vote count to the existing candidate's dictionary of vote values.

<img width="451" alt="image" src="https://user-images.githubusercontent.com/114873837/203624473-4cdc00c1-b3e8-47ff-a4eb-3ce13854fa2e.png">

Following the process described above for each county, I created a new variable to capture the calculation of candidate votes divided by total votes multiplied by 100, which generates the percentage of the total.

<img width="474" alt="image" src="https://user-images.githubusercontent.com/114873837/203624217-bd575b14-d53b-40c1-9039-fda9c76d5c4c.png">

To place the candidate results in an output table that could be printed to the terminal and written to the text file, I structured a series of f strings to fill in the values of the candidate's name, percentage, and candidate vote totals. Because this code is within the for loop, the output of results is repeated for each candidate, resulting in three lines for the output table. 

<img width="541" alt="image" src="https://user-images.githubusercontent.com/114873837/203624106-8641764c-723e-4d6b-b8e0-620f6e1901e0.png">

Next, I created a for loop "for candidate_name in candidate_votes" to loop through the candidate votes dictionary to retrieve the vote count for each candidate. Within the for loop, I wrote a conditional if statement - If the vote count for the candidate was greater than the current value of "winning_count" and the vote percentage for the candidate was greater than the current value of "winning_percentage", then the current candidate name becomes the winning candidate.

<img width="585" alt="image" src="https://user-images.githubusercontent.com/114873837/203631801-34030f10-661a-4464-a943-c0abba1fd4dd.png">

 - **From the above analysis, we can see that the candidate with the largest number of votes was Diana DeGette, who secured a sizeable 73.8% of the votes with 272,892 votes.**
 
 <img width="465" alt="image" src="https://user-images.githubusercontent.com/114873837/203630319-ce6ad517-2325-44ba-b4bc-5e879001b02c.png">


## Election Audit Summary

The python script as described above can be considered scalable for other elections. The text file that displays the results will automatically update to display the candidate names, county names, and votes, even if they are different values or larger numbers of values than the ones used in our sample csv. 

If the election isn't looking at specific candidates, but rather ballot initiatives or referendums (such as "vote yes/no on this measure"), the variables for "candidate names" can easily be updated to reflect the yes or no options. 

Since many voting districts are drawn to cross county lines and cover geographic portions of multiple counties, the board of elections can also change references to the "county" variables to "voting district" or "precinct", or even "state" if the election is large enough. 


# Election_analysis

## Overview of Election Audit
## Purpose
A Colorado Board of Elections employee has given you the following tasks to complete the election audit of a recent local congressional election.

1. Calculate the total number of votes cast.
2. Get a complete list of candidates who received votes.
3. Calculate the total number of votes each candidate received.
3. Calculate the percentage of votes each candidate won.
5. Determine the winner of the election based on popular vote.

## Resources
- Data Source: election_results.csv
- Software: Python 3.9.13

## Election Audit Results
The analysis of the election show that:
- **There were 369,711 total votes cast in the local election**.
The total vote count was calculated by looping through the rows and continuing to add the number of votes in each row to the total value. First, I created a "total_votes" variable and initialized it to start at zero.

<img width="317" alt="image" src="https://user-images.githubusercontent.com/114873837/203384879-453d64cb-c174-4826-a48b-cf076fc362be.png">

After setting up a for loop, I included a section of code that would read the value of the votes from the dictionary representing the row.
<img width="427" alt="image" src="https://user-images.githubusercontent.com/114873837/203385287-a8b84b11-1bac-4d9a-ba14-46b7ae98a4a1.png">

To produce the number of total votes in an output table, I included the "total_votes" value (that had been calculated in the for loop) in a series of f strings that produced the table format and contents.  

<img width="464" alt="image" src="https://user-images.githubusercontent.com/114873837/203386057-7e724a5e-36b7-485c-bdcd-cd827f886cc5.png">


- The following table breaks down the total number of votes cast in each county, as well as their percentage of the total votes in the election.
[CODE DESCRIPTION]
<img width="215" alt="image" src="https://user-images.githubusercontent.com/114873837/203383342-1f0315cd-b369-48c6-83ad-e4ece43329ce.png">

- From the above analysis, we can see that the county with the largest number of votes was Denver, with a total vote count of 306,055, which was 82.8% of the total ballots cast across the precinct. To confirm this result, I included a piece of code that would automatically produce the county with the largest county turnout.
[CODE DESCRIPTION]

- The candidates were:
  -Candidate 1
  -Candidate 2
  -Candidate 3
 -The candidate results were:
  - Candidate 1 received "x% of the vote and "y" number of votes
  - Candidate 2 received "x%" of the vote and "y" number of votes
  - Candidate 3 received "x% of the vote and "y" number of votes
 -The winner of the election was:
  - Candidate (1, 2, or 3), who received "x%" of the vote and "y" number of votes

## Election Audit Summary

There is a statement to the election commission that explores how this script can be used for any election, with two examples for modifying the script. (4 pt)

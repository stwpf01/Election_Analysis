# Election_Analysis

## Overview of Project

The purpose of this project was to determine the results of an election by using Python and then writing said results to a text file. The results gathered for this project were the winner, number of votes and percentage of votes of the winner, votes casted per county, and largest turnout for a county. The inital information was provided for in the [election_results.csv](https://github.com/stwpf01/Election_Analysis/blob/main/Resources/election_results.csv)file. A script of code was then written in Python, found in the [PyPoll_Challenge.py](https://github.com/stwpf01/Election_Analysis/blob/main/PyPoll_Challenge.py) file, to parse through the information and then the results were put into [election_analysis.txt](https://github.com/stwpf01/Election_Analysis/blob/main/analysis/election_analysis.txt) to see them outside a running code terminal. The results of the election will be detailed below in the "Election-Audit Results" section.     

## Election-Audit Results

Here are the results of the election in their entirety. Note: These are the same results found in the [election_analysis.txt](https://github.com/stwpf01/Election_Analysis/blob/main/analysis/election_analysis.txt)file:  

![Election_Results](https://github.com/stwpf01/Election_Analysis/blob/main/analysis/Election_Results.png)

This tells us the following information:

- There were 369,711 votes in total cast.
- Three counties voted in this election (listed alphabetically),
  * Arapahoe, where 24,801 votes were cast making up 6.7& of the total vote.
  * Denver, where 308,055 votes were cast making up 82.8% of the total vote.
  * Jefferson, where 38,855 votes were cast making up 10.5% of the total vote.

- The county with the highest turnout was Denver.
 

- There were three candidates running in this election (listed alphabeticallyby first name),
  * Charles Caspar Stockham, receiving 85,213 votes making up 23.0% of the total vote.
  * Diana DeGette, receiving 272,892 votes making up 73.8% of the total vote.
  * Raymon Anthony Doane, receiving 11,606 votes making up 3.1% of the total vote.

- The winner of this election was Diana Degette with 272,892 votes making up 73.8% of the total votes.

An example of how this information was found using Python is as follows:

1. Created variables for lists and dictionaries for the county (`county_list = []`) and their votes (`county_votes = {}`), respectively.
2. Nested in a `for` statement for a variable to read the .csv file, determine where in the row counties would be located.
(`county_name = row[1]`).
3. Create an `if` statement using an inverted Boolean value.
(`if county_name not in county_list:`) 
4. Nested inside the `if` statement, add the county name to the county list 
    (`county_list.append(county_name)`)
5. Underneath but still nested inside the `if` statement, strart tracking the votes for a county as an integer.          
    (`county_votes[county_name] = 0`)
6. Beneath the `if` statement but not indented inside it, start adding all of the votes for a county together. (`county_votes[county_name] += 1`) 
7. Nested in a `for` loop outside the previous `if` statement, make a variable to collect the county names for the county votes dictionary.
(`for county_name in county_votes:`)
    (`vote = county_votes.get(county_name`)
8. Still nested in the `for` loop, create a variable to represent the outcome of a percentage equation using the float method to convert the numbers to have a decimal place.
(`county_percentage = float(vote) / float(total_votes) *100`)
9. Create an `f-string` syntax format for a new variable to clearly state the outcomes on individual lines.
(`county_results = (f"{county_name}: {county_percentage:.1f}% ({vote:,})\n")`)
10. Use the `print` function to see the outcomes in the terminal.

What this should show is the a list of the counties with their percentage of the vote and the total amount of votes they received. 


## Election-Audit Summary

As long as the right information is provided to parse through, this script used to determine the outcome of this election can be used for any election. Modifications would need to be made if the information is not provided in the exact order, such as Counties being listed in the third row[2] and not the second row[1] or the need to see two decimal points beyond the ones integer (`:.2f` instead of `:.1f` in the `f-string` format) , but it should give the same results. 
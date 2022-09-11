# **Analysis of the Election Audit**
##### Miguel Fidelino
##### September 10 2022

## Purpose 

The purpose of the election audit was to parse the voter's ballot to find the winner of the election. 

The election commission requested us to provide the following information:

    1. The voter turnout for each county
    2. The percentage of votes from each county out of the total count
    3. The county with the highest turnout

## Results


*  How many votes were cast in this congressional election?

    A total of 369,711 votes were cast.


* Provide a breakdown of the number of votes and the percentage of total votes for each county in the precinct.

    Jefferson county had 10.5% of the votes, with 38855 voters.
    Denver county had 82.8% of the votes, with 306055 voters.
    Arapahoe county had 6.7% of the votes, with 24801 voters.


* Which county had the largest number of votes?

    Denver county had the highest amount of voters, with 82.8% of the entire votes.

* Provide a breakdown of the number of votes and the percentage of the total votes each candidate received.

    Charles Casper Stockham won 23.0% of the votes, with a total of 85,213 voters from the three counties.

    Diana DeGette won a majority with 73.8% of the votes, with a total of 272,892 from the three counties.

    Raymon Anthony Doane won the least amount of votes, with a total of 3.1% of the total voters. A total of 11,606 votes were received from the three counties.

* Which candidate won the election, what was their vote count, and what was their percentage of the total votes?

    Diana DeGette won with a majority win of 73.8%. DeGette received a total of 272,892 votes from the three counties.

## Election-Audit Summary

The script used to count the total elections parsed 369,711 total csv codes in a time of .2879 seconds. In less than a third of a second, we were able to obtain information on the participating candidates and counties: the total votes per entity, the winner of the election, and county participation data.

With the implementation of the following code we are able to scale the entries for any amount of candidates:

```

        if candidate_name not in candidate_options:

            candidate_options.append(candidate_name)
            candidate_votes[candidate_name] = 0

        candidate_votes[candidate_name] += 1
```

The same can be done with counties:

```
        if county_name not in county_list:
            county_list.append(county_name)
            county_votes_dict[county_name] = 0

        if county_name in county_votes_dict:
            county_votes_dict[county_name] += 1
```

The script we have provided has the ability to fit any size of candidates or counties, and can be used for future elections as the code above can identify new entries. In terms of performance, the script we have provided can parse about 1,000,000 CSV entries in 4/5 of a second.

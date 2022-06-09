# Election__Analysis

In this analysis, we looked for general voting statistics of every county and candidate as well as the winning candidate and highest turnover county. Here are some important points to note about the election data:
* There were a total of 369,711 votes casted
* For Jefferson county, there was a total of 38,855 votes casted, with a percentage of 10.5%. For Denver county, there was a total of 306,055 votes, with a percentage of 82.8%. And for Arapahoe, there was a total of 24,801 votes, with a percentage of 6.7%.
* By the data presented for each county, Denver had the largest number of votes, much bigger than any of the two other counties.
* As for the candidates: Charles Casper Stockham had 85,213 votes with 23.0% of the total votes casted. Diana DeGette had 272,892 votes with 73.8%. And Raymon Anthony Doane had 11,606 votes with 3.1%. 
* Diana DeGette won the election by a grand total of 272,892 votes, which accounted for 73.8% of the total votes. 

The script used for this election process can be used for any election process as it provides the total number for any variable you'd like to use and provides a percentage which can then very easily be transformed into a pie graph for representational visualization. In the case of counties, you could replace that by states if it were to be a presidential election for example. The point of this script, is to withdraw the data provided by a large data structure that would otherwise take a long time to analyze. The script seemlessly grabs on to the data you're interested in, does the calculations for you, and removes the risk of human error. Some core parts of the code that made this possible included: 
* Provides the data for the winning county:

        if (county_votes_result > winning_count) and (county_vote_percentage > winning_percentage):
            winning_count = county_votes_result
            largest_county = county_name
            winning_percentage = county_vote_percentage
            county_voter_turnout = largest_county
            
* Provides data for winning candidate:


        for candidate_name in candidate_votes:
                votes = candidate_votes.get(candidate_name)
                vote_percentage = float(votes) / float(total_votes) * 100
                candidate_results = (
                        f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")
                if (votes > winning_count) and (vote_percentage > winning_percentage):
                        winning_count = votes
                        winning_candidate = candidate_name
                        winning_percentage = vote_percentage
                
* A completely editable print statement that can be openly modified to whatever values or strings you'd like in accordance to the code and purpose of the code


        winning_candidate_summary = (
                f"-------------------------\n"
                f"Winner: {winning_candidate}\n"
                f"Winning Vote Count: {winning_count:,}\n"
                f"Winning Percentage: {winning_percentage:.1f}%\n"
                f"-------------------------\n")
        print(winning_candidate_summary)
    
These logic statements provide some of these results, as well as perform all the logic and methematical functions for you. In just a simple code run, you can receive your wanted results without any unwanted errors or flaws in the integrity of the data. 

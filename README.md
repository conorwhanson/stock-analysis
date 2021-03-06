# Stock Analysis based on Year

## Overview
This project is meant to analyze and display the total daily volume and overall return for 12 stocks for the years of 2017 or 2018. The project allows the user to input on which year they want to see the analysis run.
## Results
After running the analysis on both years for all 12 stocks we can draw a few of conclusions regarding the stock performance. First, 2017 was a strong return year for a majority of the stocks analyzed, with four stocks exceeding 100% return (see table below).

![Ticker_performance_2017](https://github.com/conorwhanson/stock-analysis/blob/main/resources/ticker_performance_2017.png)

Second, in 2018 there was a substantial downturn in stock returns across the board, with all but 2 taking a loss of returns. This perhaps suggests some kind of event which caused such a downturn (see table below).

![Ticker_performance_2018](https://github.com/conorwhanson/stock-analysis/blob/main/resources/ticker_performance_2018.png) 

Third, only 2 stocks maintained returns for both years (ENPH and RUN), with RUN increasing its return in 2018 beyond its 2017 return. Further, both stocks increased their daily volume by double. Whatever caused the other 10 stock returns to drop seems to have left these 2 unaffected, and suggests these two are perhaps more immune to market volatility than the others. 

I would suggest more data be gathered on the performance of these 12 stocks for a greater range of years. This would give a clearer picture of long-term performance to ensure greater likelihood of returns over time, as well as help us understand what caused the downturn in the market. Furthermore, I would suggest more data for RUN and ENPH specifically to understand what causal factors contributed both to their stability relative to the other stocks, as well as their increased volume (RUN doubled and ENPH nearly tripled). An initial glance at this data shows these two stocks could perhaps be good candidates for investment. 

Regarding the script utilized to run this analysis, using a refactored script drastically cut the runtimes for the stock analysis. While the original script completed the analysis in .28125 seconds, the refactored script did the same analysis 3 times faster (.08203 seconds, see images below).

![VBA_Challenge_2017](https://github.com/conorwhanson/stock-analysis/blob/main/resources/VBA_Challenge_2017.png)![VBA_Challenge_2018](https://github.com/conorwhanson/stock-analysis/blob/main/resources/VBA_Challenge_2018.png)

The main difference between the scripts is twofold. First, the refactored script used a single index to reference the tickers (tickerIndex). This allowed the code to only need to use this single reference when running through each array to gather the ticker name, daily volume, and return (see image below).

![tickerIndex](https://github.com/conorwhanson/stock-analysis/blob/main/resources/Script_comparison_1.png) 

Second, the refactored code nested a ticker increase inside the loop through the tickers, increasing the tickerIndex with each pass and saved the value to each variable, outputting the totals a single time after the loop was done. This is much faster than having to go back to the beginning of the loop to look for the next ticker and outputting the values each pass through the loop (see image below).

![Nested_ticker_increase_v_output_in_loop](https://github.com/conorwhanson/stock-analysis/blob/main/resources/Script-comparison_2.png)

While both scripts completed the task required, if we were to expand our analysis to more stocks and increase the range of years, the refactored script would save much time. This would be crucial to ensure the stocks are purchased at an opportune time to provide the maximum return.

## Summary
The advantages of refactoring a code can be significant, with equally significant pitfalls. The code can certainly save time as opposed to having to write something from scratch. As long as the basic logical structure and goal match your current project minimal changes would be needed. However, determining that the goal of your project and the goal for which the refactored script was initially written may not be straightforward. If the refactored code had a different goal, then significant changes may be needed along with extra time for debugging.

This refactored code was easy in one sense because it had the same goal as our original code. It worked in that the main structure was what we were also seeking to build and execute. However, certain elements of the code required research to see how it could be utilized for our goal, as well as how the added index and variables would fit within the existing code. Overall, once ironed out the code works well and has the potential to analyze larger datasets with haste.

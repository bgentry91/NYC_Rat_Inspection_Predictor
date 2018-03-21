# NYC Rat Inspection Predictor

Project repo for model to predict future rat inspections in NYC by Tax Block. A powerpoint presentation outlining the project can be found [here](https://github.com/bgentry91/NYC_Rat_Inspection_Predictor/blob/master/NYC_Rat_Inspection_Presentation.pdf). Visualization of historic rat inspections can be found on the project's [bl.ocks.org](https://bl.ocks.org/bgentry91/783ac5c3cc4fae6c952806d2465a8989) page.

[Direct Link](https://bl.ocks.org/bgentry91/raw/783ac5c3cc4fae6c952806d2465a8989/)

![Map Image](https://github.com/bgentry91/NYC_Rat_Inspection_Predictor/blob/master/Rat_Inspections_Q42017.png?style=centerme)

The model was built using a random forest classifier in Python using Pandas and Scikit-learn. Because the rat inspection data is relatively sparse, the data was grouped by quarter of the year and tax block. This follows the assumption that if one building on a block had active rat signs, others were likely to as well. The downside to this approach is that the model only predicts results at this level, but for it’s potential uses by the health department I feel that is acceptable. 

I found that the key to this project was engineering time series features for a given block as well as its five nearest neighbors. Through this approach, the model is better able to understand how the rats move through the city. For instance, as extermination efforts push rats out of one block, they are often likely to move to other nearby blocks. If your neighbors had rats last quarter, you might want to look out – there’s a good chance they’ll move towards your building! These time series features were engineered for the results of previous inspections as well as for follow-up and baiting actions performed by the health department.

Finally, I built a visualization using D3.js that allows a user to view the results of rat inspections over time in each Manhattan census block. This mapping helps visualize both the results of inspections in a given quarter as well as the city’s inspection efforts. Often, a larger number of census blocks are never inspected in a 3-month period.

Rat inspection data from [NYC Open Data](https://data.cityofnewyork.us/Health/Rodent-Inspection/p937-wjvj) and tax lot information from the NYC Planning Department [PLUTO database](http://www1.nyc.gov/site/planning/data-maps/open-data.page#pluto).

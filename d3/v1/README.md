README
====================================================
This repository consists of the following files/folders: 

1. [data](https://github.com/LiChangNY/Udacity_d3/tree/master/data)
  * [2008](http://stat-computing.org/dataexpo/2009/the-data.html) flights information data. The original data is about 650 MB so I used Python for processing the data.
  * [airport](http://stat-computing.org/dataexpo/2009/supplemental-data.html) information including city, state, latitude and longitude. 
  * [script.ipynb](https://github.com/LiChangNY/Udacity_d3/blob/master/data/script.ipynb): For this project, I only used the contiguous U.S. states (thus excluding Alaska and Hawaii). 
2. [js](https://github.com/LiChangNY/Udacity_d3/tree/master/js): .js files
3. index.html: all versions

##Summary
Catching flights or picking someone up at the airport can be excruciating if the flight gets delayed or even cancelled. Allowing users to fully explore the flight route of interest, this visualization aims to inform the performance of U.S. flights in 2008. Readers can find information such as number of flights, cancellation rate, and delay rate, etc, and use this information to plan for their journey, for example, avoiding booking flights with high cancellation rate, and adjust their expectations in advance. 

##Design
The first part of the visualization is a geo-map of U.S. airports. Circles represent the location of all U.S. airports. The circle size indicates number of flights taking off from a given airport. Once clicked on each circle, the web page will plot all the flight routes from the selected airport to the destination airports. This design is very much inspired by [Mike Bostock’s airport visualization](http://mbostock.github.io/d3/talk/20111116/airports.html). Based off his beautiful visualization, I added more information in the second interactive panel (beneath the map) to show the flight information by routes and help readers assess flight performance. Readers will be able to find number of flights between two airports, the percentage of cancellation, delay (both departure and arrival) and diversion rate. 

#Feedback
Work-in-progress:
- What do you notice in the visualization? 
- What questions do you have about the data?
- Is there something you don't understand in the visualization?
- What do you think you will use this visualization?
- Do you find any relationships interesting or counter-intuitive?
- What do you like about the visualization?
- What do you think I can improve on  the visualization?


##Resource
1. javascript - How to invoke "click" event programmatically in d3? - Stack Overflow
http://stackoverflow.com/questions/9063383/how-to-invoke-click-event-programmatically-in-d3
2. D3.js - Bar Chart & Sorting - JSFiddle http://jsfiddle.net/enigmarm/3HL4a/13/
3. TopoJSON Points http://bl.ocks.org/mbostock/4408297
4. Plotting points on a map in D3 http://bl.ocks.org/phil-pedruco/7745589
5. Making a Simple Interactive Map Prototype with D3…For Total Beginners Who are Totally Impatient | suffen.us
https://suffenus.wordpress.com/2014/01/07/making-interactive-maps-with-d3-for-total-beginners/
6. Map example: dot and path http://mbostock.github.io/d3/talk/20111116/airports.html

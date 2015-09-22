README
====================================================
This repository consists of the following files/folders: 

1. [data](https://github.com/LiChangNY/LiChangNY.github.io/tree/master/d3/v2/data)
  * [2008](http://stat-computing.org/dataexpo/2009/the-data.html) flights information data. The original data is about 650 MB so I used Python for processing the data.
  * [airport](http://stat-computing.org/dataexpo/2009/supplemental-data.html) information including city, state, latitude and longitude. 
  * [script.ipynb](https://github.com/LiChangNY/LiChangNY.github.io/tree/master/d3/v2/data/script.ipynb): For this project, I only used the contiguous U.S. states (thus excluding Alaska and Hawaii). 
2. [js](https://github.com/LiChangNY/LiChangNY.github.io/tree/master/d3/v2/js): .js files
3. index.html: all versions

##Summary
This project visualizes the worst 25 airports (with >1000 flights in 2008) for cancellation and the laregest cancellation reason for each airport. Of these 25 airports, nearly 3 out of 4 are in the Midwest. About half (12 out of 25) airports reported extreme weather as the largest reason for cancellation, closely followed by National Air System (11 out of 25). Although intuitively you would correlate the Midwest's high cancellation rates with the severe weather conditions in the area, the analysis shows "National Air System", which includes non-extreme weather conditions and heavy air traffic, as the main reason for cancelled flights. 

##Design
The visualization is first based off of a geo-map of the reported 25 airports. I used airports with more than 1000 flights in 2008. Circles represent the location of these airports. The circle size indicates cancellation rate. Each circle is colored by the top cancellation reason. Hovering each circle, readers will see a summary of the flight information of a given airport.   

#Feedback
- What do you notice in the visualization? 
- What questions do you have about the data?
- Is there something you don't understand in the visualization?
- Do you find any relationships interesting or counter-intuitive?
- What do you like about the visualization?
- What do you think I can improve on  the visualization?

@Charlie Udacity coach:
In the text you say "Of these 25 airports, nearly 3 out of 4 are located near the coast". Firstly, it's confusing because you say "Of these 25" then immediately "out of 4" - can you give this out of 25 for clarity? Secondly, I'm not sure this is true. It doesn't look to me as though 3/4 of the airports are near the coast. How do you define 'near the coast'?

Somewhat similarly, 'More than three-thirds (16 out of 25)' doesn't seem correct. 16/25 is less than two thirds, certainly not more than three thirds.

What does CXL mean? It seems unnecessary to obscure meaning here.
LC: I changed CXL to Cancellation. :) 

Whilst it's nice that you added a link to more explanation of the various causes of cancellation, I think you could include a explanation of this within the visualisation to save the viewer having to go elsewhere.

In the legend there is a red circle for 'security' but I don't see any red circles on the map. Why is this included?

I think the plot still suffers from overplotting - perhaps the use of transparency and edging is adding to this problem? I think that it might be better to change the transparency on mouseover so that the highlighted circle is bright, rather than changing its colour (where there is overplotting, it makes it even more difficult to see).

Li: I changed to a lighter edge. As for transparency, I wasn’t very in favor of solid colors in the beginning because a few circles overlap with each other. But now when I use non-transparent color instead of changing to yellow on mouseover, it does look much nicer. The mouse-over circle stands out even more. 

The transparency on the tooltip text also makes this a little hard to see. Could you change the placement of this text, or make its background more opaque?

##Resource
1. javascript - How to invoke "click" event programmatically in d3? - Stack Overflow
http://stackoverflow.com/questions/9063383/how-to-invoke-click-event-programmatically-in-d3
2. D3.js - Bar Chart & Sorting - JSFiddle http://jsfiddle.net/enigmarm/3HL4a/13/
3. TopoJSON Points http://bl.ocks.org/mbostock/4408297
4. Plotting points on a map in D3 http://bl.ocks.org/phil-pedruco/7745589
5. Making a Simple Interactive Map Prototype with D3…For Total Beginners Who are Totally Impatient | suffen.us
https://suffenus.wordpress.com/2014/01/07/making-interactive-maps-with-d3-for-total-beginners/
6. Map example: dot and path http://mbostock.github.io/d3/talk/20111116/airports.html
7. Let's Make a Map: http://bost.ocks.org/mike/bubble-map/

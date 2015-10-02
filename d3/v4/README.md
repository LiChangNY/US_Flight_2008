README
====================================================
This repository consists of the following files/folders: 

1. [data](https://github.com/LiChangNY/LiChangNY.github.io/tree/master/d3/v4/data)
  * [2008](http://stat-computing.org/dataexpo/2009/the-data.html) flights information data. The original data is about 650 MB so I used Python for processing the data.
  * [airport](http://stat-computing.org/dataexpo/2009/supplemental-data.html) information including city, state, latitude and longitude. 
  * [script.ipynb](https://github.com/LiChangNY/LiChangNY.github.io/tree/master/d3/v4/data/script.ipynb): For this project, I only used the contiguous U.S. states (thus excluding Alaska and Hawaii). 
2. [js](https://github.com/LiChangNY/LiChangNY.github.io/tree/master/d3/v4/js): .js files
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

No.1
@bhavin_329167828 Udacity peer:
Hi Li,

Your visualization is definitely explanatory in nature, and the visual encodings are clear. I think as-is you may probably meet all expectations.

I do have a suggestion, if I may:

I noticed that except LaGuardia, all the other airports in your viz are small and regional. Since US air travel has a hub-and-spoke system, I feel you could broaden the appeal of your viz by limiting it to just the 25 busiest airports in America, which would all be hubs. It would be a great tool for most air travellers in the US in deciding what hub to connect through.

You would also be comparing airports that have similar passenger traffic, so that it is a fair comparison.

Regards,
Bhavin

Response:

Hi, Bhavin.
Thank you so much for your comment. I think your suggestion on visualizing 25 busiest airports sounds great. However, after I made changes by limiting to just the 25 busiest airports, I realize that it poses a challenge in the visual encodings. Here is the link: http://lichangny.github.io/d3/v3/2
Some circles, as decided by the cancellation rate, either overlap with each other significantly when I use a big magnifier or appears super small with a small magnifier , which reduces the readability of the viz....I'm all ears if you have any recommendations on how to improve on the v3 codes.

Thanks again!
Best,
Li


Hi Li,

Mike Bostock suggests that you can overcome the problem of overlapping by always putting smaller bubbles over larger bubbles. Please see the data viz #6 at this link, where he discusses the problem of occlusion.

http://bost.ocks.org/mike/bubble-map/6

The lie-factor on the bubbles seems to be greater than 1. If you notice, the area for the 3% bubble is more than 3x larger than the area of the 1% bubble. You can easily fix that by using the square root of the cancellation rate.

Best Regards,
Bhavin

Response:

Hi, Bhavin.

Thank you so much for the lead. I sorted the data to address the occlusion problem and used Math.sqrt for radius. Here is the updated viz.
http://lichangny.github.io/d3/v3/index.html6

Let me know if you have any further suggestions. Thanks again!

Best,
Li

Hi Li,

The data viz looks great. The highlighting of the selected airport is a nice touch.

Good luck!

Best Regards,
Bhavin


No.2 
@Charlie Udacity coach:

I think you've got a couple of interesting points in there, which your text did a good job of highlighting:
- The spread of the busiest airports in the US
- Weather seems to cause cancellations mostly on the south and central parts of the US
Overall, I enjoyed looking at your visualisation - well done! I like the use of text and map together.

However there were a few things that confused me that you could improve

- In the text you say "Of these 25 airports, nearly 3 out of 4 are located near the coast". Firstly, it's confusing because you say "Of these 25" then immediately "out of 4" - can you give this out of 25 for clarity? Secondly, I'm not sure this is true. It doesn't look to me as though 3/4 of the airports are near the coast. How do you define 'near the coast'?
LC: Sorry for the confusion. I mistakenly counted McCarran (NV) and Phoenix Sky Harbor (AZ) as in coastal states but Nevada and Arizona are not, based on the wiki page. I've corrected them.

- Somewhat similarly, 'More than three-thirds (16 out of 25)' doesn't seem correct. 16/25 is less than two thirds, certainly not more than three thirds.
LC: Corrected as "About two-thirds". Sorry for the typo. 

- What does CXL mean? It seems unnecessary to obscure meaning here.
LC: It's supposed to short for cancellation. Since it caused confusion, I changed CXL to Cancellation. :) 

- Whilst it's nice that you added a link to more explanation of the various causes of cancellation, I think you could include a explanation of this within the visualisation to save the viewer having to go elsewhere.
LC: Added some examples. 

- In the legend there is a red circle for 'security' but I don't see any red circles on the map. Why is this included?
LC: Security was one of the four cancellation codes in the original dataset. But none of 25 busiest airports reported security as the biggest reason for cancellation (which is good :)). I've removed it from the graph.

- I think the plot still suffers from overplotting - perhaps the use of transparency and edging is adding to this problem? I think that it might be better to change the transparency on mouseover so that the highlighted circle is bright, rather than changing its colour (where there is overplotting, it makes it even more difficult to see).
LC: I changed to a lighter edge. As for transparency, in the beginning I wasn’t very in favor of solid colors because a few circles overlap with each other. But now when I use non-transparent color instead of changing to yellow on mouseover, it does look much nicer. The mouse-over circle stands out even more. 

- The transparency on the tooltip text also makes this a little hard to see. Could you change the placement of this text, or make its background more opaque?
LC: I've increased the font size as well as the placement. Is it more clear now?

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

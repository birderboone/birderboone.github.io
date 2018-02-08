---
layout: page
title: eBird Projects
permalink: /ebird/
---

As a regional editor for central Texas and a data junky I have worked significantly with eBird data in my free time. 

# Texas Filters Widget 
Texas contains 254 counties that host over 500 bird species annually spanning desert, alpine, shrubland, coastal, and riparian wetland habitats. Dozens of volunteers in the state of Texas tirelessly maintain the filters for each county in order to maintain data integrity. The task of creating accurate filters for each of the 254 counties in Texas is extremely difficult for a handful of volunteers and resources are often scattered.

With the help of head Texas eBird editor, Eric Carpenter, I created a tool that uses the current filters and presence absence data from eBird to visualize and monitor these filters for the Texas eBird portal. This includes what other filters are present, county level timings of birds, and datatables to find rare birds that are not on filters.  
<div style="text-align:center" markdown="1">

  ![ebird shinny ap](https://i.imgur.com/Zo1vWtL.png)
  
</div>
This tool currently runs in a SHINY R app that can be run locally on a computer. Just download the entire folder below. Install the necessary packages (noted at the top of the code), enter your working directory, and hit run. 

The link can be found below:
[Texas eBird Shiny app](https://github.com/birderboone/ebird)

# Life List Widget
With the addition of the eBird profile, eBird has vastly improved the visual output for users on about their life lists. I wanted to improve on this concept and push the statistics and summaries farther. I built a shiny widget that show you more data on your birding habits. Simply request a download of your data, and unzip the resulting file.

![How To download yourd data](https://i.imgur.com/osTddYN.png)

This code will be up by the end of Jan 2018

![ebird preview all locations](https://i.imgur.com/dLiUvJS.png)

![ebird preview life birds](https://i.imgur.com/hUZaiC6.png)


# Listing and Needs Widget for eBird
eBird central contains many great features for birding listers, inlcuding needs alerts and target species. However, it lacks a couple of features that might be useful for birders or data junkies.

I wanted to create an app that allowed people to use their downloaded birding data (see above), to forecast where the best places to bird are to gain more life or year birds. This tool is meant to be fun and largely for curiosity sake. So I hope you'll have fun with it!

![ebird listing preview](https://i.imgur.com/Y3rztEi.png)

I expect to post the finished code up by the end of January 2018.

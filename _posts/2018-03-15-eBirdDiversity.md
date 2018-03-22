---
layout: post
title: How many birds can you see in each U.S. county?
---
Recently I asked the question: [what counties in the US were the most underbirded](https://birderboone.github.io/eBirdEffort/). I found that the Central and Southern United States were severely underbirded, and was surprised at the large discrepancy in effort across the United States. For example the #1 county by submissions, Los Angelos county, has an impressive 181,000 checklists submitted all time. This would rank #7 worldwide, just behind the United Kingdom if L.A. was considered it's own country (luckily its not). Now compare this to Martin, Kentucky with only 12 checklists submitted **EVER**. Clearly data from these two counties are not similar.

The reason this might matter is Los Angeles county ranks 2nd in total species seen with 534 while Martin county ranks 2nd TO LAST with 71. While Southern California certainly is more birdier than the Kentucky, it's not that much birdier. We know that an increase in search effort increases bird diversity. More birders in an area inevitably find more birds, especially skilled birders, which certainly exist in LA but possibly not Martin county. Additionally, birding brings tourism and a groundswell of conservation for a region. Here in Texas countless tracks of important and birded lands are owned by private groups (Houston Audubon, The Nature Conservancy, Texas Ornithological Society), the state of Texas, and federal agencies (USFWS and FS). These sites remain regionally important and well managed partly because of the large interest by birders. These contrasting levels of effort can hamper research using eBird, particularly when researchers want to calculate species diversity of timings using presence data. 

![total species diversity on ebird](https://i.imgur.com/ogHJ3Tr.png) *Total birds seen on eBird by county.*

-------------------------------------------------
Granted it can be difficult to bring birders to a county. South Texas and South Jersey aside, most highly birded counties are in areas of high populations. Most under-birded areas are sparsely populated or not known for high bird diversity, lowering the willingness of birders to travel to these counties. 

Texas is a good case study in trying to increase birding in underbirded areas and highlight discovering new things across the state. Texas contains a large number of highly skilled, obsessive, or just energetic birders, and 254 counties some of which contain more cattle than people. While the greater Houston, Austin, and San Antonio area are well birded, more than half the state rarely gets visited by birders. To increase data in these counties the Texas Ornithological Society began the [Texas Century Club](http://texascenturyclub.org/index.php?title=Main_Page). Birders attempt to log 100 species in 100 counties (200 in 200 for the intrepid birder). Anybody who accomplishes this feat is recognized at the next Texas Ornithological Society meeting and a plaque. To date, every county in Texas has logged atleast 129 species and 117 checklists. A single person, Anthony Heweston, has even logged 100 birds in all 254 counties of Texas. 

## So how many birds are there?
This certainly proves one thing, there's always more birds. But it also brings up another question. How many birds are there supposed to be in every county? While counties containing large cities are likely reasonably accurate in their species richness, we may never know how many birds actually exist in underbirded areas. I wanted to figure out if I could use these highly bird areas as test data to model what factors might affect birding diversity. Specifically, I wanted to model how many birds including vagrants you might find, not just expected winter/summer bird diversity (which has been calculate before). I modeled eBird diversity in highly birded counties against climatic, physically, and biological variables that might affect bird diversity. Once this model was created I interpolated it across the United States. I outlinded the methods at the end of the page if you want to take a look. Otherwise I'll skip to the results.

![](https://i.imgur.com/i2mmR3b.png)
*Modeled bird diversity across the United States*

-------------------------------------------------
My resulting model shows many patterns we already knew. Coastal and southern sites have the highest expected diversity, and these results are similar to our actual ebird diversity. Perhaps more surprising is that western diversity as a whole is expected to be much higher than interior eastern diversity, particularly in the Appalachian region. In total our lowest diversity was in Patrick county, Virginia (240 birds), our highest total was from Los Angelos county (487), and our average diversity was 299 birds for each county. 

You can find the resulting table and browse though it [here](https://github.com/birderboone/birderboone.github.io/blob/master/ebirdSpeciesModeled.csv)

![](https://i.imgur.com/V7TEDjj.png)
*Increase in bird diversity compared to current eBird reports*

-------------------------------------------------
When we take the difference between reported diversity on eBird and modeled diversity we get a map thats very similar to our map of [total submitted checklists](https://birderboone.github.io/eBirdEffort/). The northern plains and Mississippi remain underbirded and contain the highest descrepancy between actual birds seen and likely birds in the area. When we look at locations in Texas, the South, and the Atlantic coast, many of the counties are within a days drive of a major metropolis. Southern Mississippi counties, for example, can easily be accessed on a day or weekend from Biloxi, New Orleans, and Mobile. Texas maybe surprising after my spiel on the Texas Century Club, but it highlights how hard is to increases birding in regions that are quite remote and contain few oppurtunities to actually bird. Many century club members resort to side of the road point counts to boost their numbers. Publicly accessed land just doesnt exist in some regions.

The take home message is there's always new places and reasons to bird. The excitement of birding new areas can come from finding new county records, exploring new areas, or adding novel data to citizen science efforts. There's never truly destitute birding areas, that's what makes birding so great. You can find new things everywhere you go. You just have to get out there and spend time in the field

-Matt


### Methods
For the test data set I used countries with atleast 5000 checklists. My previous work with eBird data showed that 5000 checklists in a region tends to create adequate sampling in area for timing charts and relatively accurate presence calculations. In the USA, 662/3100 counties reach this milestone. Regions with high numbers of checklists tend to find more rare birds than similar regions even past our 5000 cut off. To help alleviate the bias from these regions, I filtered out extremely rare birds by subsetting the data to species seen at a presence of 0.001 (0.1%). 

I wanted to model species diversity on eBird, which represents more than just expected diversity of native birds but also vagrancies. The [Biodiversity Mapping Project](http://biodiversitymapping.org/wordpress/index.php/usa-birds/), calculated bird diversity in the United States for conservation efforts and allowed access to the outputs. I used this variable as a good metric of baseline diversity in the region. 

To help explain factors that might lead to increased vagrancies in a region I included varibles like county area, mean precipitation, elevational range, distance to the coast, and temperature range. I calculated each of these metrics for every county in the United States in R (praise be to it). Finally, I modeled the total number of birds seen on eBird against our biodiversity metric, area, and the mentioned climate metrics using Boosted Regresssion Trees and interpolated the model across the United States


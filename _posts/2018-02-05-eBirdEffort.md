---
layout: post
title: Where should you bird today?
---
I've recently moved to San Bernard NWR for the winter to catch rails. Located on the Upper Texas Coast, San Bernard boasts some of the highest bird species totals in the United States (a respectable 311). This is partly due to it's location right in the epicenter of spring gulf migration and its proximaty to Houston (1.5 hours). The entire area of the gulf coast contains impressive  winter birding oppurtunties including being only 40 minutes from the [famous Mad Island WMA](https://www.nature.org/ourinitiatives/regions/northamerica/unitedstates/texas/explore/mad-island-bird-count.xml?redirect=https-301), whose CBC totals rank number one 20 of the past 25 years. Part of this CBC's success comes from lots of scouting and a large group of participants (~100). Infact this entire regions good birding can partitally be attributed to the amount of birders birding the area. 

This effect has been coined the [Patagonia picnic table effect](https://en.wikipedia.org/wiki/Patagonia_picnic_table_effect). Wherein, more birders searching in an area leads to more rare birds found. The story goes that a Thick-billed Kingbird was found (correct me if I'm wrong) at the Patagonia Rest stop. This bird brought in birders from all around to find the bird, and this influx of birders found more rarities like a Yellow Grosbeak. Anyone who has been to this site can tell you that there's nothing particularly novel about this rest stop. It's in Southeast Arizona near a desert wash, there's plenty of sites like this around the area. However, this spot became famous because of the amount of birders who found all the new rare birds. Any surrounding vegetated washes could have also had these birds, but there weren't birders to find them. This phenemenon got me thinking about how novel is it to find a rare bird in an area, and are there areas where novel birds be more likely to be found by a single individual.

My first stop in this line of thinking was to figure out where are the underbirded areas in the United States. Logic should dictate if there are non-birded areas near ones with high amounts of species then that area likely also has good birds in it. So my question was "Where might an increase in birding lead to the largest increase in novel data?" 

To explore this idea I started an eBird data mining exercise. I will detail later my tactic for data mining eBird, but for now I'll be brief. Using R I acquired all presence absence data from eBird for all counties in the United States. I used the map functions in ggplot to then map this data. My first stop was to map checklists totals by state to see what states might be the least birded and see if there is obvious descrepancies in effort
![state map](https://i.imgur.com/HoCx4zI.png)

My first look at checklists totals across the United States showed an obvious bias in checklists with population megacenters dominating other regions by factors of ten. So to explore the more under birded areas where effort might be an issue I mapped all eBird checklists by county and filtered out counties that had totals of atleast 1,000 total checklists.  

![ddd](https://i.imgur.com/AnCyPLo.png)

This inital mapping revealed nothing particularl novel: populous areas around cities and the Northeast contain high numbers of submitted checklist, where as areas with low populations contain relatively few checklists. Disproportionately Mississippii, Kentucky, and West Virgina seem to be under birded even compared to the Great Plains (one of the better known eBird effort holes). How does this total effort affect species seen?



To figure out how effort might affect species diversity on eBird I mapped the total number of species seen all time per state. When looking at this map the obvious birding hotspots (Texas, Arizona, and California) stand out. These states are all big, south, and contain very diverse habitat including Sky Islands, Deserts, Forests, and unique wetlands. Noticeably lacking is the entirety of the Mississippi River drainage and Central Plains. In particular there are obvious biases in ND, SD, IA, MS, KY, and WV. So how many species are we supposed to see in these areas and how underbirded are they?

Luckily, USGS, as part of their [Gap Analysis project](https:Fre//gapanalysis.usgs.gov/species/), calculated likely species richiness across the United States. While their calculated species richness is not the exact same number as number of birds seen in an area (which included vagrancies), we can use it as a comparative guide to compare regions. From this data we notice that species richness increases the farther south and proximate to coastlines. Mountain ranges notoriously lead to less species richiness on a small scale but increase it when paired with novel habitat types (like deserts in the west).

![usgs gap anaylsis](https://gapanalysis.usgs.gov/species/files/2012/03/Birds_Richness.png)

This data shows states bordering each other, particularly those that contain similar water features should be approximately similar in species diversity. Meaning states like West Virginia (328 birds) and Kentucky (348 birds) likely contain somewhere between Ohio (404) and Tennessee (394). That's an increase of ~70 and 50 birds! 

MS (379) sits somewhere between Louisiana (450) and Alabama (432), an increase of ~60 birds!

The entirety of the Great Plains is much more difficult to estimate. For starters the Central United States is under birded and features like the Great Lakes and the Rocky Mountains can increase species richiness. Colorado has both a good birder population and a healthy contrast between the Rockies and Great Plains making it difficult to compare to mountainless North Dakota. However, Wyoming's edition of the Tetons and South Dakotas Black Hills suggest numbers for these states might approach Colorado in birding potential. A liberal estimate for  North Dakota (366), South Dakota (370), and Wyoming (389) probably sit somewhere between Colorado (494) and Montana (408).

An important note is none of these really get at birding vagrancies, something I hope to address soon. 

--------------------------------------------------------------

Highly birded sites noted for birding (AZ, CA, FL, and TX) and states with high populations (NY, OH, PA) boast high amount of species rarities. So if you choose to bird an area how likely are you to find something new? The states with the lowest checklists total would be a good place to start. Interestingly, 7 states in the bottom 10 of total checklists are also in the bottom 10 of total species. 
![dd](https://i.imgur.com/QO2ro6D.png)

However, one issue is population varies in each of these states which affects the amount of total checklists that could be submitted. Certain states naturally contain more birders than others and thus any single contribution is masked by other birders in the area. So to account for this I calculated the ratio of total checklists to population (2010 Census). Which leads us to our rather surprising and comical final map. with the understanding that one hyper eBirder can bias areas if they submit multiple checklists every day (as does happen in certain areas).

![fff](https://i.imgur.com/H1ngAGu.png)

I expect only Vermont birders were aware of this impressive stat, for every 3 people living in Vermont 1 eBird checklist has been submitted (Since Jan 2018). Besides that we see that Mississippi and Kentucky are criminally underbirded. These states are both underbirded and likely chocked full of new birds for you to find! Even our estimates of Mississippi's potential come from two states that have their own effort problems (refer back to the original map). 

My suggestion for all budding birders itching for a challenge is to visit any of our underbirded counties, particularly if you live in any of the bottom 10 birded states (the Great Plains States, Mississippi, Kentucky, and West Virginia). Not only will you be adding novel data to eBird but your chances of finding unique or new birds is quite high. The lowest birded states have opportunities for even relatively new birders to find state firsts that states like Texas, California, Arizona, and New Jersey can't offer.

So get out there and bird your heart out!.

-Matt

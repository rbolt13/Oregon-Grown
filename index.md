## Cannabis Dispensary Diversity

### Introduction

A state known for growing all varieties of trees and greenery, it’s no wonder that Oregon was one of the first states to legalize recreational cannabis in 2014. Measure 91 changed the lives of both those affiliated with cannabis and those who benefit from the tax revenue it brings in. While many businesses and industries struggled in 2020 due to COVID-19 the cannabis industry kept growing. According to the Oregon Liquor Control Commission (OLCC) between January and September of 2020 the state and local taxes for cannabis sales tax in Oregon was more than $134 million. That is already slightly more than the cannabis sales tax for the entire year of 2019.  With that much money, and more to come this project aims to investigate the diversity of dispensaries look like in Oregon November 2020, 8 years after recreational legalization. 

```
<stoney picture>
The above image is of COVID-19 essential employees of Stoney Only Clackamas wearing 'gas masks' on 4/20/2020. 
Credit: https://www.instagram.com/stoney_only/
```
### Background

Two years ago, in May 2018 Willamette Weekly wrote an article about the Oregon cannabis industry that said, “... more than 1 in 5 of Oregon’s 544 dispensaries now belong to a chain.”. In that same article the author wrote about the owner of Chalice who helped write House Bill 4014 in 2016 which revoked the residency requirement from House Bill 3400 in 2015.  This meant there was no longer a 51% requirement for any cannabis owned business to be owned by an Oregonian of at least two years. To raise the stakes even higher, a year after this article was written in 2019 Kate Brown passed Bill 582 which would make it legal to transport cannabis over state lines when it becomes federally legal. Meaning that cannabis companies that already have business in recreationally legal neighboring states such as Washington, California, and Nevada will already have a leg up doing business with Oregon if they already established cannabis businesses in Oregon. Particularly dispensaries, since that is the avenue in which any cannabis product can be legally sold. Something else to mention about Oregon cannabis dispensary licenses is that unlike other states who have legalized cannabis after Oregon, such as Chicago, there was no lottery or easy way for illegal drug dealers or healers to transition their businesses legally. Seeming to disconnect the legal cannabis industry even further from the people of color who have been historically associated (and criminalized) with illegal cannabis.

### Data Collection

To get a better understanding of the diversity of dispensaries in Oregon as current as November 2020 the first step of this project was to get that data set of Active Marijuanan Retail Licenses from the OLCC’s website. This data set included useful information to this project such as the Trade Name, County, Street Address, Postal City and Zip codes for all active licenses. I then saved and sorted the data alphabetically by Trade Name, and sadded two more columns to my data to investigate. The first column, Business, was looking at how many dispensaries had multiple locations (with the same name or owner) compared to those that had only a single location. The second column added, Big Four, was left for all dispensaries unless they were owned by Groundworks (Electric Lettuce, Serra, Pharma), Mr.Nice Guy, Nectar, and La Mota. With the modified data,  I was able to copy the spreadsheet into a google sheet and use Geocode by Awesome Table to add the latitude and longitude coordinates for each dispensary. 

There are two important things to note here about the two data columns that were added. The first is that while Groundworks brand is Electric Lettuce, Serra, and Pharma, they own many dispensaries in Oregon, but keep the existing branding in place. For transparency I knew to look for this because I worked for Groundworks for a short time, and was able to verify the other locations they owned via their website blog. Those dispensaries are Canna Daddies, Cola Cove, Five Zero Trees, Foster Buds, Alberta Green House, Rose City Wellness, and Herbary Dispensary. Meaning the data shows all these locations as Groundworks, having multiple Business locations. No further research was found that indicated other dispensary brands had multiple locations with differing names, however that does not mean there couldn’t be more chain dispensaries than what is indicated on the maps below. The second thing to note about this data is that some chain dispensaries had both Limited Liability Companies (LLC’s), which changes the structure of ownership, and non LLC’s. The most notable for this data set is La Mota which has 9 LLC’s, 2 of which are in Medford. 

### Mapping Processes

Before collecting spatial references I made sure my map had the standard Lambert conic conformal projection, then from the Oregon Spatial Library I used a polygon shape file of the Oregon border and the city limits from 2019. With my main spatial references in place I used XY Table to Point in Arc Pro to convert my dispensaries data table into points on a map. With that alone two obvious and instant trends showed a large cluster of dispensaries within Portland’s urban growth boundary (ugb) which matches population trends in Oregon. From ARLIS I added the highway lines as visual markers to the readers, and the polygon of Portland’s ugb to use for one of my study areas.  The last shape file I added was the Major Rivers from Lab 1. I thought the Willamette river specifically running down the center of the ugb was a good reference for identifying the East and West sides of Portland. However, I did not include it in the cities maps because aesthetically speaking none of the other maps had large bodies of water in them. Admittedly I played around with a bunch of different files from ARLIS, but none showed more interesting or obvious to eyeball trends to me than the ugb, and major cities. 

Additionally I wanted to further investigate the diversity of those areas most dense in dispensaries. To do so I used select by attribute to export out the single dispensaries, multiple dispensaries, and each of the Big Four classified earlier as Groundworks, Mr. Nice Guys, Nectar, and La Mota as individual feature classes. Then I used a spatial join of the city limits and each of the feature classes that were just exported to obtain an attribute table similar to **Table 1** below, which shows the data for the ugb and Oregon's 10 cities densist in dispensaries. 


| City Name     | Dispensary    | Groundworks  | Mr.Nice Guy | Nectar  | La Mota  |
| :-----------: |:-------------:| :-----------:| :---------: | :----:  | :------: |
| ugb     | 262 | 25 | 4 | 14 | 11 |
| Portland  | 196 | 10 | 3 | 8 | 8 |
| Salem | 50 | 0 | 4 | 2 | 0 |
| Eugene | 49 | 1 | 1 | 2 | 1 |
| Medford | 26 | 0 | 1 | 0 | 6 |
| Bend | 24 | 0 | 1 | 0 | 0 |
| Corvallis | 15 | 0 | 2 | 0 | 0 |
| Springfield |12 | 0 | 1 | 1 | 0 |
| Roseburg | 11 | 0 | 0 | 0 | 2 |
| Beaverton | 10 | 1 | 0 | 2 | 0 |
| Astoria | 8 | 0 | 2 | 0 | 0 |

```
**Table 1**: Oregon's 10 Dispensary Dense Cities, and Portland UGB
```

With the data leading the way in cartographic decision making, the last tool I used was cut. Since Portland’s ugb was it’s own shapefile, the first cut to make was all the cities that weren’t Portland, Salem, Eugene, or Medford. I next clipped the highways (for reference), and each of the big four dispensaries for both Portland’s ugb and the 4 cities previously stated. Lastly for Portland’s ugb maps I cut the rivers, as well as the single and multiple dispensaries to fit within those boundaries. The last small note to add is that in the last map the cities are colored differently because it has Graduated Colors for it’s primary symbology on the dispensary join. In the final map design it made more sense to me to put the number of dispensaries per city in each map under the city name, rather than to add another legend with ranged values that wouldn’t necessarily make sense at first glance.

```
<Map 1>
**Dispensary Diversity**: above shows dispensary diversity in Oregon as of November 2020. The image of Oregon on the left shows all 695 dispensaries, whereas the map on the right only shows the locations of the largest four dispensaries in Oregon: La Mota, Groundworks, Mr.Nice Guy, and Nectar. 
```
### Dispensary Diversity

Highlighted above in map 1, **Dispensary Diversity** the data shows us that more than half of dispensaries in Oregon are owned by a chain, and that one in ten of all dispensaries in Oregon are owned by either La Mota, Groundworks, Mr.Nice Guy, or Nectar. 


To speculation on certain trends, La Mota and Mr.Nice Guy’s presence along I-5 could be in preparation of federal legalization, and ready accessiblity to Californa's market. It could also be related to proximity of cannabis farms. Nectar locations have reputations of being large “Warehouse” size dispensaries, that probably deal with a lot of bulk purchases, which this project takes no account of. Groundworks on the other hand has its own indoor farm called Pruf Cultivar located North of Portland by the airport. Since their dispensaries mostly sell their flower, it makes sense to keep most if not all of Groundworks locations in the Portland area (near their farm). Especially considering Groundworks has footing in California with more than 11 California dispesaries and growing. 

```
<Map 2>
**MJ in Portland's UGB*: In the image on the left are  261 of Oregon’s 695 dispensaries ( that’s almost 40%) with yellow plus signs indicating 140 multiple dispensaries and the green plus signs indicated the 121 single business dispensaries. To the right of that image is also Portland’s ugb, but only showing the largest four dispensaries in Oregon. Note MJ is a common short hand for Mary Jane a _slang_ term for Marijuanna. 
```
### MJ in Portland's UGB

The first point noted on this map is that the percentages for the urban growth boundary matches that of Oregon. Meaning about 53% of dispensaries in Portland’s urban growth boundary are chains. Another point to add is that one in ten of overall dispensaries in this area is owned by Groundworks, and according to their website their are plans to buy even more dispensaries in this area in 2021. Additionally about 20% of dispeensaries in Portland urban growth boundry are owned by one of the big four chains: Groundworks, La Mota, Nectar, or Mr. Nice Guy. To add a cartographic note about this map, the cross signs were initally used on the maps to match the common green outlines white plus sign symbology that is assosicated with dispensaries. Changing the cross signs to other symbology even dot’s did not change the clutter-ness of the left side map in Map 2. To counteract the heiracrhy that would to show a more accurate 50/50 split I increased the transparency of both the inside of the yellow cross and it’s orange border. Additionally, in regards to the symbology for Nectar. I played around with darker / more vibrant colors, as well as giving it a higher ranking order, but felt it detracted from the trends I was trying to visually highlight.

```
<Map 3>
**Densest Cities Dealing Dope**: shows the top four most dispensary dense cities and where the four biggest chain dispensaries are approximately located in each.
```
### Densest Cities Dealing Dope

Highlighted on this map are that 8% of dispensaries in Portland (not the ubg) are owned by Groundworks, 8% of dispensaries in Salem are owned by Mr.Nice Guy, and almost ¼ th (23%) of the dispensaries in Medford are owned by La Mota. Not mentioned on this map, but commented about in this paper was about LLC’s, and how La Mota has two in Medford. The main reason this stuck out to me was because there are six La Mota’s in Medford, but it only looks like five on the map because two of those La Motas are around the corner from each other. Doing further research, it only appears that there are 5 La Mota’s in Medford even though there are six licenses. If time wasn’t a limiting factor on this project it would have been beneficial to do more research on the business of cannabis dispensaries to better speculate on some of these outliers and trends in big canna-buisness. 

### Conclusion 

When I first started this project, I was coming from a two year history of privlidge selling cannabis legally as a white woman, in an industry that to me felt like it seperated itself from issues surrounding social justice in a similar way that big fast food chains would seperate themselves from issues surrounding obesity. Unlike obsity, however the cannabis market was legalized intererly by social activism, and when I first proposed this project wanted to look specifically at the sex and race or the owner. However unlike large chains smalled dispensaries owners were not unfamiliar with cannabis prohibition, and still go by their former alliaces which made finding the demographics for those dispensaries difficult. 

If I were to add to this project there are three different avenues I'd potentially take. 
1. Expand area from Oregon to include West Coast states Washington and California.
2. Expand focus from cannabis dispensaries to include cannabis manufacuters and farms.
3. Indoor Farms vs. Outdoor Farms 

### Special Thanks

Special thanks to my Professor Alicia Milligan for teaching me about GIS and being a huge support duing this entire project, and Amy Valley at Stoney Only for not only being a friend and a mentor, but for allowing me the tools, access, and support to learn and grow in any way I chose at my time at Stoney Only. 


```
### Sources
OLCC Data Set: https://www.oregon.gov/olcc/marijuana/Pages/Recreational-Marijuana-Licensing.aspx
Oregon Spatial Library: https://spatialdata.oregonexplorer.info/geoportal/
Groundworks Website: https://www.gw-ind.com/
Mr.Nice Guys Website: https://www.mrniceguyretail.com/home
Nectar Website: https://nectar.store/
La Mota Website: https://www.lamota.com/
Willamette Article[2018]:https://www.wweek.com/news/2018/05/16/deep-pocketed-investors-are-storming-oregons-cannabis-market-theyre-shifting-the-business-model-from-mom-and-pop-shops-to-starbucks/ 
```

### Contact

```
Email: rbolt@pdx.edu
LinkedIn: https://www.linkedin.com/in/randi-bolt-ab20771b0/
```

<!--
```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```
-->

---
layout: archive
title: "How Do Summer Storms Effect Melting Sea Ice?"
author_profile: false
---
**Hannah Chapman-Dutton**

![enter image description here](Chapman_1.jpg)
> "Arctic sea ice extent continues to decline in all months of the year; the strongest reductions in September are unprecedented in at least 1000 years."[^1] 

Sea ice covers the Arctic Ocean from roughly November to June each year. In some areas, sea ice can even survive the summer to become what is called multiyear ice. This ice cover provides habitat for many animals and microorganisms, as well as an important means of transportation and has cultural significance for Arctic indigenous communities. Sea ice is also extremely important from a climate perspective: it keeps the polar oceans from warming!

Sea ice is usually white and very reflective. Most of the sunlight that hits the ice, or snow on top of ice, is reflected back out to space instead of being absorbed by the dark ocean underneath. For most of the year, this highly reflective surface helps to keep the polar regions cool. This feature is particularly important in the late spring and summer when darker, melting ice and open water on the surface can absorb incoming radiation from the sun rather than reflecting it. The more reflective the ice is, the colder it stays and, therefore, the longer it can survive into the summer months.

>**Albedo:** the proportion of light or radiation that is reflected by a surface. Albedo is often measured as a unitless number between 0 and 1, with 0 absorbing all radiation and 1 reflecting all radiation.

Fresh, dry snow is one of the most reflective surfaces in nature with an albedo of up to 0.9, while wet snow is closer to 0.5. Ocean water comes in at 0.08, with sea ice falling anywhere between the ocean and snow depending on how old or dirty it is, or how much melt water is present within the ice.

In the Arctic Ocean, between 50% and 80% of the snow on sea ice is deposited by cyclones[^2] (hurricanes that occur outside of tropical regions). With so much of the highly reflective snow cover coming from cyclones, it is very important to fully understand what kind of impact a summer cyclone can have on melting ice. Analyzing satellite imagery provides a great way to quantify the changes in surface reflectance across a region of sea ice after a cyclone passes over.

## Testing A Cyclone's Impact on Sea Ice
The first step in this process is to identify a cyclone that contributed to the snow depth in a sea ice environment. This is done using the records from Ice Mass Balance Buoys[^3] which are frozen into the sea ice and left to drift and record changes in snow depth, air temperature, ice thickness, and air pressure.  

A buoy deployed in 2008 recorded an increase in snow depth of about 7 centimeters in mid July. At the same time as this snowfall, a cyclone passed over the buoy, meaning that the snow can be attributed to that cyclone rather than a regular storm. This event was recorded by the MODIS[^4] Terra satellite which records surface reflectance data across many wavelengths, including the visual spectrum which is particularly useful for recording differences in snow, ice, and water. 

![MODIS images from July 1, 2008 and July 15, 2008 above the classified maps for each image](Chapman_2.jpg)
*Top: Combined images from MODIS bands 1-3. Bottom: Classification maps*

In order to quantify the differences in reflectance between these two images, I identified four classes within each image using small areas of white snow/ice, dark/melting ice, ponds/breaking ice, and open water. These manually selected areas were used as training data for an algorithm which then classified each pixel in the given image as one of those four classes. I also included one or two cloud classes since both images have a fair amount of cloud cover obscuring the ice below. 

### The Trouble with Clouds
Clouds often pose a problem when using satellite data in the range of visible light. Any instrument operating on the same wavelengths as our eyes will "see" the same things that we see. As such, it can be very difficult to get useful data on a surface like sea ice which is frequently obscured by clouds. The image below is an example of the study area from July 13, 2008 which is almost completely obscured by clouds and post-processing artifacts. This proves to be a nearly unavoidable problem when studying the impacts of cyclones since they generally make for very dense cloud cover.

![MODIS image obscured by clouds](Chapman_3.jpg)
*July 13, 2008 MODIS image featuring heavy cloud cover*

## Results
Once each image is classified, it is easy to quantify the results by looking at what percentage of the image is attributed to each class. Below are percentage plots of each image with and without clouds included. Note that, while July 15 was far more cloudy, when the cloudy pixels are removed we can see a 40% increase in highly reflective white snow and ice, as well as a slight decrease in melting ice and a large 30% decrease in open water and melt ponds on the surface. This decrease in open water is likely due to the high winds associated with a cyclone which can compress the ice, draining ponds and temporarily closing cracks.

![enter image description here](Chapman_4.jpg)

## Conclusions
The results of this comparison uphold the hypothesis that a summer cyclone can have a positive impact on the overall reflectance of a sea ice environment. Even well into the summer when the sea ice is actively melting and breaking apart, the snowfall from a cyclone can decrease the amount of visible dark or melting ice on the surface. Since water and dark ice absorb more light than fresh snow, their exposure on the surface causes the ice to warm and melt faster than it might otherwise. 

In a large-scale, comprehensive study of sea ice types, this method would be applied to many tens or hundreds of images. The parameters for each class and each image would be fed into a machine learning program which could then learn to classify such images independently. By doing this, we could learn about the impacts of many cyclones across  time and space and determine if they always have the same effect or if the impact of a cyclone on ice has changed over time. 

![Graph of sea ice extent decline since 1980, NSIDC](Chapman_5.jpg)
*Global sea ice extent from 1980-present. Source: NSIDC[^5]*

According to the 2019 IPCC special report on the cryosphere, "it is very likely that projected Arctic warming will result in continued loss of sea ice"[^1].  Under these conditions, it is becoming more and more important to understand how different climatic factors cause ice to melt faster and which help preserve it later into the melt season. In the case of cyclones, changes to the temperature or humidity of the atmosphere that are expected in climate change scenarios could also change the frequency and intensity of large storms. While more cyclones in the summer might help to prevent sea ice from melting as quickly and therefore keep the oceans slightly cooler, there is also a possibility that warmer cyclones would result in rain rather than snow precipitation which would likely make the ice melt even faster. As such, understanding specifically how cyclones under different conditions impact the reflectance of the sea ice surface is imperative for improving predictions of climate change. 

[^1]: IPCC, 2019: Technical Summary [H.-O. Pörtner, D.C. Roberts, V. Masson-Delmotte, P. Zhai, E. Poloczanska, K. Mintenbeck, M. Tignor, A. Alegría, M. Nicolai, A. Okem, J. Petzold, B. Rama, N.M. Weyer (eds.)]. In: _IPCC Special Report on the Ocean and Cryosphere in a Changing Climate_ [H.- O. Pörtner, D.C. Roberts, V. Masson-Delmotte, P. Zhai, M. Tignor, E. Poloczanska, K. Mintenbeck, A. Alegría, M. Nicolai, A. Okem, J. Petzold, B. Rama, N.M. Weyer (eds.)]. In press. https://www.ipcc.ch/srocc/chapter/technical-summary/
[^2]:Webster, M., Parker, C., Boisvert, L., & R. Kwok (2019), The role of cyclones in snow accumulation on Arctic sea ice, Nat. Comms. 10, 5285, doi:10.1038/s41467-019-13299-8.
[^3]: Perovich, D., J. Richter-Menge, and C. Polashenski, Observing and understanding climate change: Monitoring the mass balance, motion, and thickness of Arctic sea ice, http://imb-crrel-dartmouth.org , current year.
[^4]: Vermote, E., Wolfe, R. (2021). _MODIS/Terra Surface Reflectance Daily L2G Global 1km and 500m SIN Grid V061_. NASA EOSDIS Land Processes DAAC. Accessed 2022-04-21 from [https://doi.org/10.5067/MODIS/MOD09GA.061](https://doi.org/10.5067/MODIS/MOD09GA.061). Accessed April 21, 2022.
[^5]:Campbell, G. G., S. Pfirman, B. Tremblay, R. Newton, P. DeRepentigny, W. Meier, and C. Fowler. The Ice Tracker. [http://icemotion.labs.nsidc.org/SITU](http://icemotion.labs.nsidc.org/SITU)

# Arizona Water Availability Analysis

Water is the most important resource for sustaining life on the planet. Fresh water is scarce in the desert, not a surprise. 
How does Arizona, with one of the driest climates in the US sustain the fifth largest city and a population of 7-million? 
This project identifies the major sources and uses of water, and investigates the sustainability of the two largest sources, 
the Colorado River, and the aquifer. Both of these sources are under pressure and not easily renewable.

I was motivated to investigate the water issue after I coached my daughter's middle-school robotics team; part of the First Lego League Challenge 
is to solve a real-world problem, and that year, we looked at water, which intersected nicely with living in the desert. We toured the Central Arizona
Project headquarters, and visited their NASAesque command room where they monitor every inch of the aquaduct that brings Colorado River water into Arizona. 
They recently announced a curtailment of the AZ allocation of the river, and I wondered, how worried should Arizonans be about the future of water in this state?

### Questions Asked in this Analysis

- Is Arizona Growing - what does that growth trend look like?
- Is Arizona getting warmer? 
- Is Precipitation declining? Is the change in precipitation statistically significant?
- Are Water levels in Lake Mead declining?
- Are Aquifer levels in Arizona declining? Is the change in aquifer levels statistically significant?
- Is Arizona capable of meeting its 100-year water commitments

#### Datasets:

[Weather (Precipitation, Relative Humidity, Temperature, Evaporation Rates)](data/AZPrecipitation.csv)<br/>
[Population (Year, Population)](data/AZpopulationgrowth.csv)<br/>
[Lake Mead: End-of-water-year (Sept. 30) storage in Lake Mead and Lake Powell, in thousands of acre feet, Source: USBR](data/Lake Meade.csv)<br/>
[Aquifer 1998-2018 Comparison](data/AZGroundWater_20year.csv)<br/>
[Aquifer 2008-2018 Comparison](data/Groundwater2008_2018.csv)<br/>
[Aquifer 2017-2018 Comparison](data/Groundwater2017_2018.csv)<br/>

Datasets were obtained through public sources:
Arizona Department of Water Resources (new.azwater.gov/aaws)
National Oceanic and Atmospheric Administration (climate.gov)
United States Bureau of Reclamation (usbr.gov)
US Geological Survery USGS (waterdata.usgs.gov/az/nwis/gw)

#### Technology

Language(s): Python / Jupyter Notebook<br/>
Libraries: Scipy / Numpy / Pandas / Matplotlib / pylab

### Methodology

##### Climate

I analyzed temperature and precipition from forty years of climate data (monthly averages) taken from multiple weather stations in the state of Arizona. There was a wide range of data from the mountains to desert. I separated the data into four decades and compared the rainfall in those datasets so see if rainfall was declining. I used a confidence interval of 95% and a two-tailed test to dispute the null hypothesis that there was no statistically significant variation in precipitation and temperature. I concluded that Arizona is getting hotter and drier over time.

I used line plots to visualize the variety of weather patterns in the state, and added a best-fit line using least squares method to show the downward trend for precipitation.
I used a normal histogram from the mean and standard deviation of each precipitation sample to map out the differences in the decades. For temperature, I used a bar plot and best fit line to model the temperature rise.

#### Population

I analyzed population growth by taking census data over 100 years and plotting histograms to visibly see Arizona's exponential growth.

#### Lake Mead Water levels

I used a simple line chart and bar chart model with a best fit line to show the precipitous decline in the water levels. 

#### Aquifer Water levels

This was the most difficult dataset to analyze. There are thousands of wells tapping into the aquifer in 46 basins in the state of Arizona. Many of them are metered and regulated, but hundreds are not. Each well tells its own story and can be vastly different from another well in another basin, which made visualizing the data extremely difficult. Wells are not measured in volume available, they are measured in feet to extractable water. Some wells drill down 1000' or more; some wells are 10' deep. Each well in three time periods was compared for depth level, if the well was at 10 feet in 1998 and at 20 feet in 2008, that's a loss of 10 feet of water. By summing the changes in the water levels, I could see if Arizona had a net gain to the aquifers, or a net loss. Using scipy, i was able to use a ttest to see if those levels were different to a statistically significant degree, and in which direction (decline/growth). 

For one of my comparisons, I had 58% of my wells reporting a depth loss, but I had statistically significant growth over all, meaning there was a net gain of water. In my research, I looked at the positive outliers where I could see the results of years of recharging efforts in the Phoenix AMA. To confirm my analysis, I removed the Phoenix AMA and ran the same analysis on all other wells, and found a critical decline in well level OUTSIDE of the Phoenix AMA. Just looking at the overal outcome, one might think that Arizona aquifers are in great shape.

### Have I piqued your interest? Learn more...

https://www.droughtfacts.com/ (the company line)
https://www.nytimes.com/2018/07/19/magazine/the-water-wars-of-arizona.html
https://www.nytimes.com/1886/07/08/archives/the-water-problem-in-arizona.html <-- From 1886!!!
https://www.nytimes.com/2021/01/05/business/theyre-making-water-a-commodity-investors-see-opportunity-in-the-colorado-river.html
https://www.azcentral.com/story/news/local/arizona-environment/2021/04/30/arizona-preparing-cutbacks-colorado-river-water-amid-drought/7401706002/
https://www.azcentral.com/story/news/local/arizona-environment/2021/06/10/lake-mead-declines-new-low-colorado-river-crisis-deepens-arizona-drought/7621138002/



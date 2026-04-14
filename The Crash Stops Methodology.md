#How I Found the WMATA Bus Stop with the Most Nearby Crashes#

## Cleaning the Data ##

My reporting on the bus stops which have the most crashes near to them is centered on and possible because of three datasets: “[Metro Bus Stops](https://opendata.dc.gov/datasets/DCGIS::metro-bus-stops/about),” as provided by the Washington Metropolitan Area Transit Authority, and “[Crashes in DC](https://opendata.dc.gov/datasets/DCGIS::crashes-in-dc/about)” and “[Crash Details Table](https://opendata.dc.gov/datasets/DCGIS::crash-details-table/about),” as maintained by Washington’s District Department of Transportation. 

“Crashes in DC” had location and time data for each crash, but not vehicle information. “Crash Details Table” had vehicle information for each crash, as well as other useful information like several datapoints for each person involved in the crash. So, I joined “Crashes in DC” with “Crash Details Table.” This ended up giving me information about who was involved in the crashes, which helped provide flavor and humanity to the story.

I also removed entries in the “Metro Bus Stops” dataset that were outside Washington, as the article was focused only on Washington bus stops and crashes.

## Mapping the Data ##

To start to understand the relationship between bus stops and crashes, I had to visually map the locations of the bus stops and crashes. I installed [QGIS](https://qgis.org/), an open source geospatial visualizing and mapping tool, to do this.

In the QGIS application, I can upload CSV files and tell the application which columns to consider as geographic data. It then maps that data on X, Y coordinates.

As a base, I uploaded a dataset of Washington’s roads called “[Roads](https://opendata.dc.gov/datasets/DCGIS::roads/about),” created by Washington’s Office of the Chief Technology Officer. This way, any crash or bus stop data I added would have a context of where the location actually is in Washington.

I then added “Metro Bus Stop” data as a layer and “Crashes in DC” as a layer.

I chose two nearby stops arbitrarily to determine the range I wanted to consider a crash to be “near a bus stop.” I chose the Georgia Avenue NW-Tuckerman Street NW bus stop and Georgia Avenue NW-Piney Branch Road NW bus stop, noted their latitude and longitude coordinates and found the latitudinal and longitudinal middle between the two stops. Calculated the middle to be 68 meters from the bus stop and used that as the radius for future calculations and analyses.

I then followed and learned from a [tutorial](https://docs.qgis.org/3.44/en/docs/gentle_gis_introduction/vector_spatial_analysis_buffers.html) of how to establish a radius around points and a [tutorial](https://gis.stackexchange.com/questions/217444/understanding-join-attributes-by-location-in-qgis) of how to join attributes by location. This allowed me to use QGIS to get a new dataset of crashes within a 68 meter radius of bus stops. I then analyzed this dataset.

I did all of this in an attempt to answer a question: “Which WMATA bus stop is the most dangerous?” That question has not yet been answered, but I’m continuing to try to answer it.

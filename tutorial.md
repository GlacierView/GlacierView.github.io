---

layout: splash
title: Tutorial
classes:
    - landing
    - dark-theme
excerpt: "A Google Earth Engine web application to monitor mountain valley glaciers"
header:
    overlay_image: /assets/images/glacier_header.png
    overlay_filter: 0.1


---

## Getting Started
***
App opening screen. Our app opens on a zoomed map of the Trient glacier in Switzerland. This is the first of our three seminal examples.

<img width="1413" alt="Screen Shot 2021-06-08 at 2 10 45 PM" src="https://user-images.githubusercontent.com/13628543/121258114-5e0a8f80-c863-11eb-82e1-f690c99b1842.png">

>Note: To view another glacier ...

The map can be navigated like the Google Maps application. You may search for countries of interest of regions of interest. In rare cases, you may search for the names of glaciers in the top search bar. Or the map can be navigated by clicking and dragging to a desired location. The zoom level will determine the viewability of the glacier polygons. 

## Functionality
### Data Access 

#### Image data
Once you click within the polygon of a glacier the GLIMS ID and coordinates will appear above the map. Additionally, the side panel will display a button allowing a user to navigate to the google drive to download the image data for that glacier. You may clear the pins by clicking the clear points button on the map. This will allow you to click upon another desired glacier.

#### Time Series data: Analysis Results
Additionally, time series data corresponding to the data displayed on the side panel is also available through a time series data link. The data displayed on the side panel is smoothed used a 5 year moving average to display the signal of glacier retreat within the noise but the time series data available through a link is not smooth and thus one can apply whatever smoothing is most useful for any particular project.

### Seminal Examples 
Our app contains three seminal examples of analysis results for glacier retreat over time. 

We include these examples of glaciers from different parts of the world for those unfamiliar with the project and glaciers in general. These examples provide a smooth time series for the decline in glacier area or arc length in the flowline over the last 37 years. Additionally, we can toggle a linear trend for each time series to determine average decline over time. An example of these time series is shown below:

<img width="696" alt="Screen Shot 2021-06-08 at 2 20 02 PM" src="https://user-images.githubusercontent.com/13628543/121259245-b9894d00-c864-11eb-8612-f23ef9c46b50.png">

These time series are smoothed using a five year moving average with a normal kernel as mentioned above. This will lead to a smoothed estimate of glacier retreat/shrinkage over time. 

One can navigate the time series and click on a particular date like seen in the above image to have the Landsat image RGB from that date displayed over the bounding box of the glacier. This allows us to see Landsat defects and image quality visually. Like the below Landsat image for Kahoto Glacier on April 23, 2015.

<img width="716" alt="Screen Shot 2021-06-08 at 2 32 30 PM" src="https://user-images.githubusercontent.com/13628543/121260709-8942ae00-c866-11eb-9f93-440b28fdaa1b.png">

### Other glaciers 

In addition to the three main examples, one may navigate to any glacier of interest and click with the boundaries of said glacier to bring all information about the glacier into the side panel. Currently all of the glaciers in orange have time series data available and will display the smoothed time series in the side panel. All glaciers that are highlighted on the map have image data available for download.

### Map Layers and Navigation

The map can be navigated as any other application using google maps. Search bar can used to navigate to particular regions of the world as desired and any click with a glacier polygon bring information on the side bar for data download. 

We have four primary fixed geo-spatial data layers displayed on the world map in our Google Earth Engine Application. 

Layer 1: Polygon for every spatially joined WGMS valley glacier, this consists of 474 glaciers. 

Layer 2: Polygon for every spatially joined WGMS valley glacier that has a matching GLIMS ID with the GLIMS database, this consists of 75 glaciers.

Layer 3: Glacier flowlines estimated using gd-flow (Hansen et al 2021).

Layer 4: Bounding Box around the glacier polygons.

These layers are automatically loaded on the map within the application but each can be hidden for easier viewing. 



***

### How to read GLIMS IDs

GLIMS IDs are the systematic id numbers for the glaciers in our data set. Not all glaciers within the dataset have names in their local languages. Thus, we maintain the GLIMS IDs to index our data and images. The GLIMS IDs are representative of the Latitude and Longitude of the location of any particular glacier. For example, the Trient glacier has GLIMS ID, G007026E45991N. This represents that Trient is located at approximately 45.991° North in Latitude and 7.026° East in Longitude. 

For glaciers in the Western Hemisphere this works a bit differently. The Longitude value in the first part of the ID is never given in degrees west, thus for a place like Alaska and the Kashoto Glacier, G222987E58962N, the first part is not representative of the traditional LatLong identification we would be familiar with. Longitude values only go to 180° but here is listed as 222.987° E which corresponds to 360 - 222.987 or about 137° W, which falls in Alaska.

The Latitude portion of the Glims ID is given in both North and South.

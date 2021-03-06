# Leaflet Homework - Visualizing Data with Leaflet

## Background

![1-Logo](Images/1-Logo.png)

### Your Mission
After reviewing part one and part two of the assignment below are the topics I am going to address:
1.	Briefly explain the logic for generating the base map.
After updating the leaflet script dependencies, the base map is imported through leaflet mapbox using my API key as a variable the map is created. You can change the zoom and map size in this section as well. The we sent the 'mapid' to the html so that it populates on the web.

2.	Describe how the JSON was loaded and how was the data traversed. Explain how was the information from the JSON used to render data on the map.
After updating the D3 script dependencies, the USGS earthquake geojson is imported through D3.json. The geoJson function moves through the data, "Features" is the dictionary and the lat & long is the key to unlocking where the earthquakes are. The URL of this JSON pulls in the data for our visualization.

3.	Explain the logic for generating the circles and amending the size of them. What does this communicate?
The styleInfo function moves through the feature dictionary again and pulls out the properties.mag to find the magnitude of the earthquake and the GetColor matches the magnitude size to a specific color including a default color using a switch function. 

4.	Describe how the layer for the Tectonic plates was generated. 
 First we set up the map layers, the basic gray map then the satellite and outdoor throught leaflet mapbox. Then we created a var for a new layer group - tectonic plates. Then used d3 to call in the tetonic plates data from the GeoJson page https://raw.githubusercontent.com/fraxen/tectonicplates/master/GeoJSON/PB2002_boundaries.json and created a 'platedata' function to add the orange lines.

5.	What are the components in the layer control? How were they generated? 
The components of the layer control are the base map, the different color map layers and the earthquake & tectonic overlays. They are generated through a series of functions, first defining them as new layers groups, then the object that defines all the different layer components. .control has the layers, baseMaps, overlays which is then pushed(addto.map) to the map.

6.	Explain the difference between the base map (tile layer) and the data layer(s).
The base maps are just leaflet maps. The data layers are using D3 Json to pull in the data, a JS function to loop through the dictionary and pull out the data, for our visualization from the USGS website and the geojson from the github repository. 

7.	Walk through the logic of how the legend was generated and rendered on the page.
We created a div or place for the ledgend in the logic and called it "info ledgend" then a control function that's called in the css to loop through our intervals and generate a label with a colored square for each interval. Then created the grades and color vars. From there we loop through our intervals and generate a label with a colored square for each interval by pulling in the grades and color vars. Then ledgend. is addTo the map. 

### General Description

Welcome to the United States Geological Survey, or USGS for short! The USGS is responsible for providing scientific data about natural hazards, the health of our ecosystems and environment; and the impacts of climate and land-use change. Their scientists develop new methods and tools to supply timely, relevant, and useful information about the Earth and its processes. As a new hire, you will be helping them out with an exciting new project!

The USGS is interested in building a new set of tools that will allow them visualize their earthquake data. They collect a massive amount of data from all over the world each day, but they lack a meaningful way of displaying it. Their hope is that being able to visualize their data will allow them to better educate the public and other government organizations (and hopefully secure more funding..) on issues facing our planet.

### Before You Begin

1. Add a folder to your homework repository called `leaflet-challenge`.

2. Inside your local git repository, create a directory for the Leaflet challenge. Use the folder names to correspond to the challenges: **Leaflet-Step-1** and **Leaflet-Step-2**.

3. This homeworks utilizes both **html** and **Javascript** so be sure to add all the necessary files. These will be the main files to run for analysis.

4. Push the above changes to GitHub or GitLab.

## Your Task

### Level 1: Basic Visualization

![2-BasicMap](Images/2-BasicMap.png)

Your first task is to visualize an earthquake data set.

1. **Get your data set**

   ![3-Data](Images/3-Data.png)

   The USGS provides earthquake data in a number of different formats, updated every 5 minutes. Visit the [USGS GeoJSON Feed](http://earthquake.usgs.gov/earthquakes/feed/v1.0/geojson.php) page and pick a data set to visualize. When you click on a data set, for example 'All Earthquakes from the Past 7 Days', you will be given a JSON representation of that data. You will be using the URL of this JSON to pull in the data for our visualization.

   ![4-JSON](Images/4-JSON.png)

2. **Import & Visualize the Data**

   Create a map using Leaflet that plots all of the earthquakes from your data set based on their longitude and latitude.

   * Your data markers should reflect the magnitude of the earthquake in their size and color. Earthquakes with higher magnitudes should appear larger and darker in color.

   * Include popups that provide additional information about the earthquake when a marker is clicked.

   * Create a legend that will provide context for your map data.

   * Your visualization should look something like the map above.

- - -

### Level 2: More Data 

![5-Advanced](Images/5-Advanced.png)

The USGS wants you to plot a second data set on your map to illustrate the relationship between tectonic plates and seismic activity. You will need to pull in a second data set and visualize it along side your original set of data. Data on tectonic plates can be found at <https://github.com/fraxen/tectonicplates>.

In this step we are going to..

* Plot a second data set on our map.

* Add a number of base maps to choose from as well as separate out our two different data sets into overlays that can be turned on and off independently.

* Add layer controls to our map.

- - -

### Assessment

Your final product will be assessed on the following metrics:

* The overall thoughtfulness, clarity, and completeness of your writeup

**Good luck!**

### Copyright

Trilogy Education Services © 2019. All Rights Reserved.

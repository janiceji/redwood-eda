# Redwood Tree Macroscope Exploratory Data Analysis

## Introduction

The purpose of this study is to analyze the microclimate surrounding a 70-meter tall redwood tree by using wireless sensors to record the variations in spatial (space) and temporal (time) dynamics, considering characteristics such temperature, humidity, as well as both direct and reflective solar radiation (light). These photosynthetically active radiations, PARs for short, are ultimately able to help scientists understand important biological and environmental impacts, like the amount of energy available for photosynthetic activities and carbon balance in the forest. Things like temperature and humidity grants scientists a deeper understanding on concepts such as the flow of sap or water through the tree. In this case study, environmental changes and patterns around the redwood tree were recorded from April 27, 2004 to June 10, 2004, a total of 44 days. The early summer period was chosen for this study to maximize the variations observed. 
The data collection process for these variables is operated by a network of sensors called macroscopes, a technology that must be protected from the weather while at the same time, exposed to track the microclimatic changes.  First, these sensor nodes are thoroughly calibrated and then scattered around the tree vertically and horizontally. Vertically, they are placed both near the base and tip, from 15 to 70 meters above the ground with a 2-meter spacing. Horizontally, they are placed 0.1 to 1.0 meters across the trunk's radius. Nodes can also be described by their direction, whether they face the east or the west. The substantial variations one observes create gradients that are observable through plotting and performing explanatory analysis. In addition, readings from the sensors are taken once every five minutes, equivalent to one epoch, and the data proceeds to be transmitted to a database. The data in sonoma-data-log.csv contains data taken from the logging itself and the separate network file is there to compensate for the loss data in the loggings in the case of unexpected failures in battery and such. Conversely, the logging file can do the same for the network. Through inspection, one notices that the data collection process differs between the two files, and these differences should be taken into consideration.

## Data
> Gathering data on the environmental dynamics around 70-meter tall redwood tree for 44 days requires robust system design and a careful > deployment methodology.

The dataset we are exploring in this project is the sonoma-data.csv. It is further split into two separate datasets by their retrieval method. sonoma-data-log.csv contains the data yield offered by the nodes, while sonoma-data-net.csv contains the data yield received from the network. In its original form, these datasets contains numerous outliers, inconsistencies, and missing values, which first need to be wrangled before we can extract any useful insights.

The main variables of interest in this study are temperature, humidity, the amount of incident or direct radiation, and reflective or indirect radiation. 

* ``result_time``: captures the timestamp the result was taken from the sensor
* ``epoch``: arbitrary integer that tells time
* ``nodeid``: id of the node sensor
* ``parent``: Amount of PM2.5 emitted, in tons
* ``voltage``: 
* ``depth``: 
* ``humidity``: 
* ``humid_temp``:
* ``humid_adj``:
* ``hamatop``:
* ``hamabot``:

Here are the first few rows from the entire dataset.
```
result_time, epoch, nodeid, parent, voltage, depth, humidity, humid_temp, humid_adj, hamatop, hamabot
2004-05-07 18:24:58.666424,2812,119,5,220,2,95.3567,12.6678,92.1444,4218.18,0
2004-05-07 18:24:58.805974,2812,105,129,223,3,96.9957,12.6482,93.7072,9363.23,0
2004-05-07 18:24:59.075427,2812,113,118,222,4,94.5031,12.4522,91.2718,9405.41,0
2004-05-07 18:24:59.355354,2812,138,5,223,2,96.8828,12.658,93.6018,9363.23,0
2004-05-07 18:24:59.675467,2812,127,42,222,3,97.8044,12.3836,94.409,4702.7,0
```

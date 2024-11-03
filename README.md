# Find_Redundant_Bus_Services

### Introduction
This project deals with geospatial bus and MRT data taken from LTA Datamall. 

In 2023, bus service 167 was deemed to be running parallel to the TEL MRT line, a sign of inefficiency and subsequently the frequency of 167 was reduced. See: https://www.straitstimes.com/singapore/transport/lta-u-turns-on-decision-to-stop-bus-service-167-route-to-be-retained-with-30-minute-intervals. 

What other bus services have a similar issue? That is our task to **identify redundant bus routes and recommend removal or rerouting of bus routes**. A summary of the project scope is given to us by our lecturer, and can be found in the repository.

### Guide to the GitHub Repository
To ensure our codes work, please either clone the repository or download this repository as a zip file. Datasets are not uploaded. It will have to be downloaded from the various data sources, which we will indicate clearly or have to be extracted using an API call, in which an API key will need to be provided.

We have 3 python scripts in our GitHub repository that we will use to identify redundant bus routes.

1) [Data Preprocessing.ipynb](https://github.com/brandono7/DSA4264_Geospatial/blob/main/Data%20Prepocessing.ipynb): 

In this python script, we made API calls to [LTA DataMall](https://datamall.lta.gov.sg/content/datamall/en/dynamic-data.html) to extract geospatial data on buses as well as passenger volume data for bus stops and for MRT/LRT stations. Note: For the API call to work, an account will need to be created and an API Key will be sent to your registered email.

To extract geospatial data on MRT/LRT stations, we gathered MRT/LRT station codes from [data.gov.sg](https://data.gov.sg/datasets/d_d312a5b127e1ae74299b8ae664cedd4e/view). This was then used as an input into the [OneMap API](https://www.onemap.gov.sg/apidocs/) to extract geospatial data on MRT/LRT stations.

2) [get_nearest_mrt_to_bus_stops.ipynb](https://github.com/brandono7/DSA4264_Geospatial/blob/main/get_nearest_mrt_to_bus_stops.ipynb)

In this python script, after obtaining the latitude and longitude of each bus stop and each MRT/LRT station, we computed the Euclidean distance to the nearest MRT/LRT station as well as the distance to the nearest MRT/LRT on every MRT/LRT line (i.e. NS line, EW line, etc.). This is then saved as **processed_data/bus_stops_with_nearest_mrt_data.csv**.

3) [Bus Algorithm.ipynb](https://github.com/brandono7/DSA4264_Geospatial/blob/main/Bus%20Algorithm.ipynb) 

In this python script, we implement a distance algorithm. We read in the bus routes data from **data/bus_routes.csv** and the **bus_stops_with_nearest_mrt_data.csv**. It obtains the nearest median distance to each MRT/LRT line from every bus stop within a bus route service. This bus algorithm serves as our first round of screening for bus routes to be removed. More nuanced considerations will be detailed in our [Report.md](https://github.com/brandono7/DSA4264_Geospatial/blob/main/Report.md).

[Report.md](https://github.com/brandono7/DSA4264_Geospatial/blob/main/Report.md) is the technical report for our project.

This project is an assignment from a NUS course - DSA4264: Sense-making Case Analysis: Public Policy and Society, taught by lecturer Mr. Shaun Khoo.

Authors: Brandon, Joshua, Wan Ting, Li Xuan, Beichen <br>
Special Thanks to Prof Shaun Khoo for his guidance. <br>
Last Updated: 6 Nov 2024

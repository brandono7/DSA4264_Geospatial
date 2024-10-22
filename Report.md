# Technical Report

## 1. Context: Why are we doing this?


In recent years, the Land Transport Authority (LTA) has introduced several new MRT lines, such as the Downtown Line and Thomson-East Coast Line, to improve public transportation efficiency. Historically, commuters relied heavily on bus services, which were slower and less predictable. Since the launch of the new MRT lines, ridership on these bus services has declined, as observed through small-scale surveys and anecdotal evidence. To optimize public transport options and encourage the use of MRT lines, we need to assess which bus routes overlap significantly with MRT services and may be suitable for rerouting or reduction.

---

## 2. Scope: What are we focusing on?


The focus of this report is to identify bus routes that run parallel to existing MRT lines and assess which routes should be reviewed for potential service changes. The goal is to optimize route planning by reducing redundancy and improving cost-efficiency, while also responding to public demand for new bus services. Specifically, we utilize openly available data from the LTA website to perform analysis and calculations that identify the bus line with the greatest overlap with existing MRT lines. Visualizations will be used to further justify and illustrate our findings.


---

## 3. Methodology: How are we doing this?

### 3.1 Collecting Data
*Author: Brandon*

The data collection will involve using publicly available datasets to analyze the bus routes that overlap with MRT lines. We will extract information on route paths, timing, and ridership estimates from these open datasets, along with additional information on MRT coverage and the population density of affected areas.

### 3.2 Explaining the Weighted Sum of Total Distance Metric (Theory)

The methodology for determining which bus routes to prioritize for removal or rerouting involves calculating a Weighted Sum of Total Distance for each bus line. The steps of the algorithm are as follows:

1. **For each bus line**, identify every bus stop along its route.
2. **For each bus stop**, find the nearest MRT station and calculate the distance between the bus stop and the MRT station.
3. **Assign a weight to each bus stop** based on the number of passengers tapping in and out (tap-in/tap-out data), which serves as a proxy for the importance of that bus stop.
4. **Calculate the weighted sum of the total distance** for the entire bus line by multiplying the distance between each bus stop and its nearest MRT station by the respective weight (tap-in/tap-out).
5. **Identify the bus line with the longest weighted total distance**, which suggests that the bus line is less redundant with the MRT system and may be a candidate for service removal or rerouting.

This approach ensures that bus stops with higher passenger traffic (as indicated by tap-in/tap-out data) are given more importance in the analysis. The bus line with the highest overall weighted distance will be prioritized for modification, as it offers the most overlap with MRT services but still serves critical stops for commuters.


---

## 4. Findings: What did you find?



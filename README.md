![Chicago St](https://s3-prod.chicagobusiness.com/north-mich-ave.jpg)

# Chicago Traffic Safety Initiative

**Author**: [Brenda De Leon](mailto:brendardeleon@gmail.com)

## Overview

Traffic deaths are preventable. The City of Chicago has had at least 800,000 yearly reported crash incidents since 2017 and at least 100 yearly reported crash incidents with at least one fatality since 2018. The City of Chicago believes everyone has the right to access to safe streets. However, Chicago has seen a general increase in incidents with at least one fatality over the years even though there has been a general decrease in number of crash incidents. We, the Vision Zero initiative, are committed to working with the City of Chicago to eliminate fatalities and serious injuries from traffic crashes. 

<img src="https://design.chicago.gov/assets/img/logo/LOGO-CHICAGO-horizontal.png" alt="Chicago logo" title="Chicago Logo" align="left" width="150" /> 
<img src="https://www.chicago.gov/content/dam/city/depts/cdot/CDOT%20Projects/VisionZero/VisionZeroLogo_Road_Horizontal_Long-01.png" alt="Vision Zero Chicago logo" title="Vision Zero Chicago Logo" align="center" width="275" />

## Business Problem

Chicago has seen an increase in crash fatalities over the years even though there has been a general decrease in number of crash incidents. The City of Chicago needs to decrease fatal car incidents. Unfortunately, the city resources available to address traffic safety are limited. 

## Data

The City of Chicago provides the public data on the reported traffic crash incidents. 
The following three datasets are provided to be used in conjunction with each other and are regularly updated and available online:

  - [Crashes](https://data.cityofchicago.org/Transportation/Traffic-Crashes-Crashes/85ca-t3if): Information about each traffic crash on city streets within the City of Chicago limits and under the jurisdiction of Chicago Police Department (CPD) (e.g. roadway surface condition, street name). 
  - [Vehicles](https://data.cityofchicago.org/Transportation/Traffic-Crashes-Vehicles/68nd-jvt3): Information about units involved in a traffic crash (e.g. make, vehicle year). 
  - [People](https://data.cityofchicago.org/Transportation/Traffic-Crashes-People/u6pd-qa9d): Information about people involved in a crash and if any injuries were sustained (e.g. driver's license class, sex).

## Methods

We will use this data to create a machine learning model which will help predict what causes injuries in crash incidents. Our binary classification model will help identify what features are most relevant in crash incident injuries.

## Results

We built a classifier that predicts whether an injury occurs, or not, at a crash incident. We can predict whether a crash incident would involve injury based on engineered features at an accuracy of 93% and have determined which of features are most important in predicting injury:

`FIRST_CRASH_TYPE0.389 +/- 0.004` <br> 
`LOCATION0.267 +/- 0.001` <br>
`TRAFFICWAY_TYPE0.183 +/- 0.002` <br>
`CRASH_MONTH0.107 +/- 0.002` <br>
`CRASH_HOUR0.103 +/- 0.002` <br>
`CRASH_DAY_OF_WEEK0.097 +/- 0.002` <br>
`TRAFFIC_CONTROL_DEVICE0.086 +/- 0.002` <br>
`DEVICE_CONDITION0.080 +/- 0.002` <br>
`LIGHTING_CONDITION0.073 +/- 0.002` <br>
`SPEED_LIMIT0.048 +/- 0.001` <br>
`ROADWAY_SURFACE_COND0.043 +/- 0.001` <br>
`WEATHER_CONDITION0.025 +/- 0.001` <br>
`VEHICLE_TYPE0.015 +/- 0.001`

![final model](/models.png)


## Conclusions

Our recommendations for the City of Chicago are backed by data and focus on those features most likely to result in an injury given the city's limited resources. Vision Zero recommends the following:

- **Public Health/Safety Campaigns that caution of the high injury rate in incidents where a cyclist or pedestrian is involved.** Provide free helmets and bike lights, with information on importance of proper usage. Encourage bright clothing to cyclists and pedestrians particularly in lower visible settings. Give warning that vehicle traffic fees involving cyclists or pedestrians will increase if numbers do not decrease.

- **Provide upgrades to problematic location points.** Upgrade the traffic control devices and or include more warnings or traffic control officers along the top location points where the most incidents occur, particularly those of fourway trafficway type. Upgrade lanes and traffic signage around the top location points to be more cyclist and pedestrian friendly, including accessability considerations.

- **Resource availability during targetted time frames.** Resource availability should increase in those top locations, particularly during the months of: July, September, and October and particularly during the hours of: 5pm to 9pm. Consider lowering public transportation fees during those months and/or hours and increasing number of trains/buses in rotation. This will encourage less vehicles on the roads which could decrease opportunities for crash incidents.

By focusing resources on features most important in predicting injury, the City of Chicago can reduce the likelihood of injury from traffic crashes and improve the safety of streets for everyone.

### Next Steps

Further analyses could yield additional insights to further improve the city's traffic safety:

- Better data collection could significantly improve our prediction ability. Unfortunately, features worthy of attention were dropped due to excessive nulls or unknowns. Age and sex are some features that were dropped due to having almost 90% null values. Weather and safety equipment are other possibly important features that were dropped to due to excessive nulls or unknowns.
- Widen the crash date range to include crashes from more years.
- Use location points to create crash incident maps to identify if there are any top locations that cluster near each other for priority identification.
- Conduct a more extensive grid search on random forest focusing on those parameters that can address our data imbalance like class weight.

## For More Information

See the full analysis in the [Jupyter Notebook](/Chicago Traffic Crashes _ Modeling.ipynb) or review this [presentation](/Chicago Crashes Presentation.pdf).

For additional info, contact Brenda De Leon at [brendardeleon@gmail.com](mailto:brendardeleon@gmail.com)

<img src="https://activetrans.org/busreports/wp-content/uploads/2015/04/vision_zero_logo.jpg" alt="visionlogo" style="width: 200px;"/>

## Repository Structure

```
├── data
│   ├── Traffic_Crashes_-_People.csv
│   ├── Traffic_Crashes_-_Vehicles.csv
│   ├── Traffic_Crashes_-_Crashes.csv
│   ├── merged_chicago.csv
│   └── clean_chicago.csv
├── Chicago Traffic Crashes _ Merging Datasets.ipynb
├── Chicago Traffic Crashes _ EDA.ipynb
├── Chicago Traffic Crashes _ Modeling.ipynb
├── Chicago Crashes Presentation.pdf
└── README.md
```

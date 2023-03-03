![Chicago St](https://s3-prod.chicagobusiness.com/north-mich-ave.jpg)

# Enhancing Traffic Safety with Data-Driven Solutions

## Using Machine Learning to Make Chicago's Streets Safer
**Author**: [Brenda De Leon](mailto:brendardeleon@gmail.com)

## Overview

Traffic deaths are preventable. The City of Chicago has had at least 800,000 yearly reported crash incidents since 2017 and at least 100 yearly reported crash incidents with at least one fatality since 2018. The City of Chicago believes everyone has the right to access to safe streets. However, Chicago has seen a general increase in incidents with at least one fatality over the years even though there has been a general decrease in number of crash incidents. We, the Vision Zero initiative, are committed to working with the City of Chicago to eliminate fatalities and serious injuries from traffic crashes. 

<img src="https://www.chicago.gov/content/dam/city/depts/cdot/CDOT%20Projects/VisionZero/VisionZeroLogo_Road_Horizontal_Long-01.png" alt="Vision Zero Chicago logo" title="Vision Zero Chicago Logo" align="center" width="300" />
<img src="https://design.chicago.gov/assets/img/logo/LOGO-CHICAGO-horizontal.png" alt="Chicago logo" title="Chicago Logo" align="center" width="150" /> 

## Business Problem

Chicago has seen an [increase in crash fatalities](https://www.illinoispolicy.org/1m-chicago-speed-camera-tickets-fail-to-stop-record-traffic-deaths/) over the years even though there has been a general decrease in number of crash incidents. The City of Chicago needs to decrease fatal car incidents. Unfortunately, the city resources available to address traffic safety are limited. 

## Data

The City of Chicago provides the public data on the reported traffic crash incidents. 
The following three datasets are provided to be used in conjunction with each other and are regularly updated and available online:

  - [Crashes](https://data.cityofchicago.org/Transportation/Traffic-Crashes-Crashes/85ca-t3if): Information about each traffic crash on city streets within the City of Chicago limits and under the jurisdiction of Chicago Police Department (CPD) (e.g. roadway surface condition, street name). 
  - [Vehicles](https://data.cityofchicago.org/Transportation/Traffic-Crashes-Vehicles/68nd-jvt3): Information about units involved in a traffic crash (e.g. make, vehicle year). 
  - [People](https://data.cityofchicago.org/Transportation/Traffic-Crashes-People/u6pd-qa9d): Information about people involved in a crash and if any injuries were sustained (e.g. driver's license class, sex).

## Methods

We will develop a machine learning model using the available data to predict the factors that contribute to injuries in crash incidents. The development of the model will involve several steps, including data preprocessing, feature selection, model training, and evaluation. Using the model, we can identify the features that have the strongest influence on injury outcomes in crash incidents. Ultimately, our goal is to provide insights into the most significant factors that contribute to injuries in crash incidents, which can inform more effective safety measures and policies.


## Results

We built a <b>Weighted Decision Tree</b> Classification model with engineered features that predicts whether a crash incident involves injury at an accuracy of 95% and determines which features are most important in predicting injury.:

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

![final model](/finalmodel.png)


## Conclusions

Our recommendations for the City of Chicago are based on data analysis, highlighting the features most likely to reduce injury rates while taking into account the city's limited resources. Vision Zero recommends the following:

- **Launch Public Health and Safety Campaigns to raise awareness of the high risk of injury in incidents involving cyclists and pedestrians** Distribute free helmets and bike lights, along with information on the importance of wearing them properly to reduce the risk of injury. Encourage cyclists and pedestrians to wear bright clothing, especially in low-visibility settings, to increase their visibility to motorists. Consider implementing higher vehicle traffic fees involving cyclists or pedestrians to incentivize safer driving practices and reduce the number of incidents.

- **Prioritize problematic location points where the most incidents involving cyclists and pedestrians occur** Implement upgrades to the traffic control devices at these locations, such as adding more visible warnings or installing more efficient traffic control officers. Upgrade the lanes and traffic signage around these locations to make them more cyclist and pedestrian friendly, while also considering accessibility needs. Focus particularly on problematic four-way trafficway locations, where the risk of incidents is highest.

- **Improved Resource Availability for High-Risk Timeframes** Increase the availability of resources, such as traffic control officers and emergency services, in the top locations where incidents involving cyclists and pedestrians are most frequent. Prioritize the months of July, September, and October, when traffic tends to be higher, as well as the hours of 5pm to 9pm, when visibility is lower and more incidents tend to occur. Consider implementing lower public transportation fees during these months and hours, as well as increasing the frequency of trains and buses in rotation, to encourage fewer vehicles on the roads and reduce the risk of incidents involving cyclists and pedestrians. 

By utilizing the insights gained from our machine learning model, the City of Chicago can take targeted action to address the most critical safety concerns and enhance the safety of streets for everyone.

### Next Steps

Further analysis could yield additional insights to further improve the city's traffic safety:

- To improve our prediction ability, we need to more data and better data collection. Unfortunately, some features that could be important for our analysis, such as age, sex, weather, and safety equipment, were dropped due to excessive nulls or unknowns.
- Include data from more years to identify trends and patterns over time.
- Create crash incident maps using location points to visually inspect and identify areas for targeted interventions.
- Conduct more preprocessing steps and hyperparameter tuning on decision tree focusing on those parameters and techniques that can address data imbalance.

## For More Information

See the full analysis in the [Jupyter Notebook](</Chicago Traffic Crashes _ Modeling.ipynb>) or review this [presentation](</Chicago Crashes Presentation.pdf>).

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

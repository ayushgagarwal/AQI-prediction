# AQI-prediction

Predicting the Air Quality Index of 100+ counties across the USA

### Summary

The aim of the project is to predict the concentration of different pollutants in the atmosphere, compute AQI across different US regions, and present the trends using interactive visualizations. We aim to provide personal health recommendations directly to the user’s inbox.  

There are two main benefits of this: users can take preventive measures to stay healthy (prevent allergy and asthma attacks) based on adequate preparation through our recommendations, and government bodies can take effective and quicker decisions based on predicted air quality and pollutants in the atmosphere.

### Innovations

- End-to-end web app/visualization product that deliver personalized recommendations to individuals.  
- Time series forecasting model that uses K-nearest neighbors to understand geospatial effects in conjunction with time series modeling on pollutant concentrations to predict AQI for each region.

### Data Scources/ Preparation

We are using two main sources of data to compile the last 11 years of data for six key atmospheric pollutants and a weather API: 
- BigQuery database (2010-2019) 
- Another official dataset (2020) 
- Weather API (OpenWeatherMap)  

Data preparation included the following tasks: 
- Data cleaning and merging 
- Interpolation of missing values 
- Rolling up data to county level from site level 
- Establishing data quality metrics

### Modeling:

We used a novel time series approach where we considered multiple features such as pollutants, pressure, humidity, wind and temperature for 5 nearest neighbours for each county.  We developed 100 models, one for each county using vector autoregression approach with optimized lag. These models forecasted AQI values for December 2020.

### Data Visualization:

We are using Tableau to build a dashboard that shows the pollutant levels across the states as well as the predicted values and trends of pollutants across the years. 
The user can filter the pollutant, the date range and county name as per the user requirement.

### Email Recommendation:
We are leveraging the Microsoft Power Automate platform to send out daily recurring emails to users based on the location they have signed up for and the existing health conditions they have.
We are using Flask as our framework for the web app which consists of one page containing the registration form and a “Register” button prompting the user to fill in their registration information for email updates.   

The Tableau dashboard is embedded into the web app. 

The link to the web app is:  https://dva-app-test.onrender.com/

A short video that talks about the project - https://youtu.be/ntuTnvEP7HA

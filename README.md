# Modeling Restaurant Inspection Scores in New York City

The main goal of this is to explore what outside factors effect health inspection scores in NYC. To do this we combine 3 datasets:

- **DOHMH Restaurant Inspection Results** – inspection scores, grades, cuisines, locations  
- **NYPD Complaint Data** – crime incidents and locations  
- **PLUTO** – property and tax lot information for NYC buildings  

From these sources, we build a cleaned, integrated restaurant dataset and train decision tree models to predict the most recent inspection score (`last_score`) and study which features (crime, property value, cuisine, etc.) matter most.

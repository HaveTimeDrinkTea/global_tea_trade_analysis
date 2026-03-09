# 🍵 🌱 The Climate & Economic Recipe for Tea: A Geospatial Analysis of Global Tea Yield Drivers
This repository contains a capstone project for the Code Institute Data Analytics with AI bootcamp. This project is built with Python with Pandas and scikit-learn in Jupyter Notebooks and Tableau.

This project includes the following:
* ETL and EDA Pipeline,
* Hypothesis Testing
* Linear regression models
* Interactive Tableau featuring geospatial map, statistical visualizations, and machine learning insights. 

# Project Description
As a trained tea artisan and certified tea assessor from China, I have long been fascinated by how terroir, climate and economics shape the world's tea trade. 

This capstone project brings together my professional passion and data analytics skills to investigate the factors driving tea yields across the world's top 15 tea producing nations. I have built an ETL pipeline in Python to explore the data. I tested two hypothesis on climate and economic impact and also built linear regression models to predict tea yields. I also have created an interactive Tableau dashboard to visualise and explore these my findings. 

While this analysis focuses on climate and economic factors, it acknowledges that tea yield is influenced by many other determinants. 

The project uses data from:
* Food and Agriculture Organization of the United Nations
* WorldBank Climate and Economic data via their Climate Change Knowledge Portal (CCKP) and the wgapi package respectively.

## Project Approach 

As the aim of this 5-day capstone project is to showcase a complete data analytics workflow from forming hypotheses, sourcing data, ETL/EDA of the data, testing the hypotheses, model predictions and presenting the findings on an interactive dashboard. This project also aims to show the use of the Kanban board and on time completion. 

| Phase | Tasks |
|---|---|
| Days 1-2| Hypothesis formation, data sourcing, ETL and EDA |
| Day 3 | Hypothesis testings, linear regression modellings Part 1|
| Day 4 | linear regression modellings Part 2, Tableau Dashboard |
| Day 5 | Bug fixes, Readme documentation and final submission |


## Project Links
* [Github repo](https://github.com/HaveTimeDrinkTea/global_tea_trade_analysis)
* Interactive Tableau Dashboard on [Tableau Public](https://public.tableau.com/app/profile/pei.wang1891/viz/Global_Tea_Trade_Dashboard/GlobalTeaTradeDashboard) or via [download the Global_Tea_Trade_Dashboard.twb](https://github.com/HaveTimeDrinkTea/global_tea_trade_analysis/tree/main/dashboard)
* [Kanban Board on GitHub](https://github.com/users/HaveTimeDrinkTea/projects/2)


# Questions & Hypothesis

The underlying data analystics question for this project is 
>
> _**Can we model and predict tea yields from climate and economic factors in a linear regression model?**_
>
From this primary question, I have derived the following hypothesis which

## Hypothesis 1 (MVP)
>
> **H<sub>0</sub>**: `Mean tea yield` is `the same` in `hot` or `cool` climate countries.
>
## Hypothesis 2 (MVP)
>
> **H<sub>0</sub>**: `In any given year`, the `mean tea yield` does not differ bettween countries with `above median GDP` and those with `below median GDP`.
>

In additional to the primary machine learning question, this project is also interested in the following complementary data analytics question:
>
> _** Can we predict whether a country is tea-dominant or coffee-dominant?**_
> 

## Hypothesis 3: (Could Have)
>
> _**There is no association between climate zone (cool/hot) and whether a country is a tea-dominant or coffee-dominant crop country.**_
>

# Potential Business Impacts & Applications of this Project
This project has potential benefits for 
* tea importors
* agricultural Investments firms
* NGOs on sustainability issues
* policy makers


# Data Sources
The project uses data from:
* [Food and Agriculture Organization of the United Nations](https://www.fao.org/faostat/en/#data/QCL)
* WorldBank Economic data via the [wgapi package](https://pypi.org/project/wbgapi/)
* WorldBank Climate data via their [Climate Change Knowledge Portal](https://climateknowledgeportal.worldbank.org/download-data)


# Results & Findings  

## Hypothese Results
* Hypothesis 1 Climate Vs Tea Yield:
  * The median temperature is computed based on the 25-year average temperature for each country. If in a particular year, the country's annual average temperature is high than its 25-year median then the country given the classification of a "hot" climate zone. Vice versa.
  * Mann-Whitney U test
   * Cool climate countries: mean = 8,8659kg/ha
   * hot climate countries: mean = 7,475 kg/ha
     * Difference +1,184 kg/ha
   * P < 0.05 
  * conclusion: Reject H<sup>0</sup> and conclude that cool climates' tea yields are higher than the hot climates. 

* Hypothesis 2 GDP Vs Tea Yield:
  * The median nominal GDP per capita of the GDPs of the 15 top tea producing countries in any given year. If in a particular year, the country's nominal GDP per capita is higher than the year's median GDP then the country is given the classification of "high GDP". Vice versa.
  * Mann-Whitney U tests on each of the 25 years
   * none of the years showed significant differences as all p values are > 0.05 (range of 0.2810 to 0.9551)
  * conclusion: Fail to reject H<sup>0</sup> and there are no significant difference in tea yield between Low GDP and high GDP countries in any given year.


## Predictive Modelling Results:

* Model 1: Linear Regression on Tea Yield 
  * Features: Temperature and Precipitation
  * The model: 
    * y-intercept: 7956.683666666667
    * Temperature coefficient: 221.907526
    * Precipitation coefficient: -973.099003
  * R<sup>2</sup> on Test set = 0.08
  * MAE on Test set = 1,886kg/ha 
  * Conclusion: Climate alone explains very little vairation in yield

* Model 2: Linear Regression on Tea Yield
  * Features: Temperature, Precipitation and GDP per capita
  * The model: 
    * y-intercept: 7956.683666666667
    * Temperature coefficient: 934.950766
    * Precipitation coefficient: -1351.454758
    * GDP coefficient: 928.510466
  * R<sup>2</sup> on Test set = 0.12
  * MAE on Test set = 1687kg/ha 
  * Conclusion: Despite having a higher R<sup>2</sup> then model 

* 🤔 Interesting note on both models: 
  * The y-intercept for both models is the _**exact same value**_. This intercept value is the predicted yield when all scaled features are at their mean = 0. This can be interpreted as the GDP_Per_Capital not having an impact in the model at all as the baseline prediction has not shifted.
  * Lasso method did not exclude GDP in model 2 probably because it has deemed GDP to be important enough to keep it by exagerating the impact of temperature and precipitation (much larger coefficients) in order to achieve a higher R<sup>2</sup>.
  * We know that nominal GDP per capita cannot be used to compare across years yet the lasso algorithm included it in the model for the sake of better prediction capabilities. This is therefore a good demonstration of why domain knowledge must guide model interpretations.  

* 📌🔍🕵🏻‍♂️ Conclusion: The respective models predicted less than 10% of the yield variations. This confirms that tea productivity is driven by many other factors. 

## Dashboard Presentation
* An interactive dashboard is developed to visualise and explore key insigths from this project.
* The dashboard is made up of the following views:
  * Global Tea Yield (main Year Slider)
    * by geographical map
    * by tiled grid map (to prevent larger countries like China to dominate the view visually)
    * yield vary significantly across regions. 
      * With the old saying "Not All the tea in China" and with my experience in the tea trade, it is surpising to see that China does not has the highest yields.
  * "Dances of the Tea Bubbles" (Animation)
    * shows through animation the effects of temperature vs tea yield over time. 
    * the bubbles showed the size of tea production in tonnes 
  * H1: Climate vs Yield (static)
    * box plot of the results of hypothesis 1
  * Country Leader Board (Sort by yield, temperature and precipitation and also by main year slider) 
* The dashboard also has the following features:
  * hover tool tips giving country-specific details
  * main year slider to filter all charts by year (except "Dances of the Tea Bubbles" and static H1 Findings) 
* How to use the dashboard:
  * Explore by sliding the `Year Filter` to see changes over time
  * click on each country on the geographical map and the tiled grid map to view additional country details
  * sort the leader board to see the top 3 and bottom 3 nations by yield, precipitation and tea yields 
  * Read the square box plot for key statistical findings.

* Interactive Tableau Dashboard on [Tableau Public](https://public.tableau.com/app/profile/pei.wang1891/viz/Global_Tea_Trade_Dashboard/GlobalTeaTradeDashboard) or via [download the Global_Tea_Trade_Dashboard.twb](https://github.com/HaveTimeDrinkTea/global_tea_trade_analysis/tree/main/dashboard)  

# Conclusion 
As the aim of this 5-day capstone project is to showcase a complete data analytics workflow from forming hypotheses, sourcing data, ETL/EDA of the data, testing the hypotheses, model predictions and presenting the findings on an interactive dashboard. This project also aims to show the use of the Kanban board and on time completion. 

Whilst the models achieved low R<sup>2<sup>, this seemingly negative finding is in itself meaningful. The low predictive powers simply confirm that tea yield is shaped by many other factors beyond national climate and GDP data. 

I hope that through this project, I have showed case its true objective and that is rigorously methology, critical thinking and project management.



# Limitations
* This individual capstone project makes no claim to be able to provide the true drivers of tea yield.  The value of this project is to demonstate a complete, rigorous data analytics workflow applied to a personally meaning question. 
  * the low R<sup>2</sup> is expected as it invites a deeper investigation by having access to more rounded and complete datasets. While the model is weak, the process is sound and the limitations are identified. 
* Choice and availablity of data 
  * While this analysis focuses on climate and economic factors, it acknowledges that tea yield is influenced by many other determinants such as the specific tea cultivars, terroir (as a function of climate and soil conditions), skills of the tea growers and the feedback from the tea artisans, farming practices (as a function of agricultural methods and equipment and pest controls etc.)
  * As such, it important to note that  
    * the use of nationally aggregated data (temperature and precipitation) which inevitably masked within-country and/or within region variations. E.g. tea grown in the Himalayas is analysed using the average climate of India as a whole.
    * the impact of the various tea plants cultivars, pest control implementation, soil quality, argriculture practices and the levels of government subsidies and support are not considered.
    * the use of nominal GDP per capita which does not allow cross-year comparisions.
* Models' performance:
  * the climate-only linear regression achieved a R<sup>2</sup> of only 0.08 indicating that only a small fraction of the tea yield variation. 
  * this confirms that many other factors play in dominant role in tea yields as detailed above.
* Scope of this project: 
  * only the Top 15 major tea-producing countries and any conclusions from this analysis may not be generalised to small producers.
  * the period 2000-2024 may not capture long-term climate shifts.

# Further Works that may Address Some of these Limitations: 
* To use GDP per capita (PPP in constant International $) instead of the Nominal GDP per capita used in this project to allow comparision across year. This valuation of GDP accounts for differences in cost of living (inflation) or purchasing power of national currencies between countries and can also be compared across years.
* Incorporating soil data and more accurate climate data from the tea producing areas (based on longtitudes and latitudes) of each country.
* Incorporating farm level data to capture farming practices
* Incorporating other variables such as altitude, irrigation, water quality, tea plant cultivars (high yielding modern cultivars vs antique slow yielding cultivars) and also the quality of the final tea product.

# Additional Further Works:
* Colonial legacy on tea yield
  * an interesting extension to this project is whether or not former British colonies exhibit systematically different tea production patterns (in tea yield, area cultivated). 
* Trade Policies and Market Access
  * With the second Trump administration, there had been significant uncertainties imposed on global trade. Some countries might operate under different trade agreements and tariff structures and market access conditions.
* Climate Change and tea producing regions
  * Using past climate data and climate model predictions to potentially identify how tea growing regions might shift.     


# Jupyter Notebooks
* For ETL and EDA 
  * FAO data [01_ETL_FAO.ipynb](notebooks/01_ETL_FAO.ipynb)
  * World Bank's Economic data [02_ETL_WorldBank.ipynb](notebooks/01_ETL_WorldBank.ipynb)
  * World Bank's Climate data [04_ETL_WorldBank_precipitation](notebooks/04_ETL_WorldBank_precipitation.ipynb) and [04_ETL_WorldBank_temperature](notebooks/04_ETL_WorldBank_temperature.ipynb)
  * ETL for data for Hypothesis [05_Prepare_Data_For_Hypothesis](notebooks/05_Prepare_Data_For_Hypothesis.ipynb)
* For hypotheses testings [06_Hypothesis_Testings](notebooks/06_Hypothesis_Testings.ipynb)
* For Linear Regression [07_Linear_Regression.ipynb](notebooks/07_Linear_Regression.ipynb)


  
# Tech Stack & Libraries
* ![Python](https://img.shields.io/badge/python-3.13%2B-blue)
* Libraries:
  * [![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=fff)](#)
  * [![NumPy](https://img.shields.io/badge/NumPy-4DABCF?logo=numpy&logoColor=fff)](#)
  * ![Matplotlib](https://custom-icon-badges.demolab.com/badge/Matplotlib-71D291?logo=matplotlib&logoColor=fff) & ![seaborn](https://img.shields.io/badge/-Seaborn-3776AB?style=flat&logo=python&logoColor=white&size=40x40)
  * ![Plotly Express](https://img.shields.io/badge/Plotly-239120?style=for-the-badge&logo=plotly&logoColor=white)
* ![Git workflow](https://img.shields.io/badge/Github%20Actions-282a2e?style=for-the-badge&logo=githubactions&logoColor=367cfe)


# How to Reproduce This Project
* (Recommended) Create a virtual environment.
* Clone the repository
> git clone https://github.com/HaveTimeDrinkTea/squidgameeffect.git
* Install dependencies: 
> pip install -r requirements.txt
* Open the Jupyter notebooks: 
> jupyter notebook notebooks/notebooks/01_ETL_FAO.ipynb

> jupyter notebook notebooks/notebooks/01_ETL_WorldBank.ipynb

> jupyter notebook notebooks/03_Analysis_Tea_Yield_Crop_Dominance.ipynb

# License
MIT License [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

# Credits and Acknowledgements
* My tutor [Mr. John Anih](https://github.com/JohnAnih) and [Mr. Mark Briscoe](https://github.com/mbriscoe/)
* eLearning materials of the "Data Analytics with AI" Bootcamp by the Code Institute
* Learnings from Stack Overflow, Mimo.org (Python e-learning) and Python official Websites
* Visualisation guidance:
  * [From Data to Viz](https://www.data-to-viz.com)
  * [The Royal Statistical Society's Best Practices for Data Visualisation](https://royal-statistical-society.github.io/datavisguide/docs/choosing.html)
* Deepseek for
  * Project brainstorming
  * being my Python and Pandas tutor and for helping to resolve code errors
  * Assist in using Plotly Express (especially for trying to put tiny Singapore on their map!)
 

# Contributions
* If you have any query or contribution about this repo, please contact via
  * GitHub [https://github.com/HaveTimeDrinkTea](https://github.com/HaveTimeDrinkTea)


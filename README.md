# 🍵 🌱 The Climate & Economic Recipe for Tea: A Geospatial Analysis of Global Tea Yield Drivers
This repository contains a capstone project for the Code Institute Data Analytics with AI bootcamp. This project is built with Python with Pandas and scikit-learn in Jupyter Notebooks and Tableau.

This project include the following:
* ETL and EDA Pipeline,
* Hypothesis Testing
* Linear regression models
* Interactive Tableau featuring geospatial map, statistical visualizations, and machine learning insights. 

# Project Description
As a trained tea aritsan and certified tea assessor from China, I have long been fascinated by how terroir, climate and economics shape the world's tea trade. 

This capstone project brings together my professional passion and data analytics skills to investigate the factors driving tea yied across the world's top 15 tea producing nations. I have built an ETL pipeline in Python to explore the data. I tested two hypothesis on climate and economic impact and also built linear regression models to predict tea yields. I also have created an interactive Tableau dashboard to visualise and exlpore these my findings. 

While this analysis focuses on climate and economic factors, it acknowledges that tea yield is influenced by many other determinants. 

The project uses data from:
* Food and Agriculture Organization of the United Nations
* WorldBank Climate and Economic data via their Climate Change Knowledge Portal (CCKP) and the wgapi package repectively.


## Project Links
* [Github repo](https://github.com/HaveTimeDrinkTea/global_tea_trade_analysis)
* Interactive Tableau Dashboard on [Tableau Public](https://public.tableau.com/app/profile/pei.wang1891/viz/Global_Tea_Trade_Dashboard/GlobalTeaTradeDashboard) or via (download the Global_Tea_Trade_Dashboard.twb)[https://github.com/HaveTimeDrinkTea/global_tea_trade_analysis/tree/main/dashboard]
* [Kanban Board on GitHub](https://github.com/users/HaveTimeDrinkTea/projects/2)


# Questions & Hypothesis

The underlying data analystics question for this project is 
>
> _**Can we model and predict tea yields from climate and economic factors in a linear regression model?**_
>
From this primary question, I have derived the following hypothesis which

## Hypothesis 1 (MVP)
>
> _**The average tea yield is the same in cool vs hot climate?**_
>
## Hypothesis 2 (MVP)
>
> _**The average tea yield is the same in nations with low vs high GDP per capita?**_
>

In additional to the primary machine learning question, this project is also interested in the followinfg complementary data analytics question:
>
> _** Can we predict whether a country is tea-dominant or coffee-dominant?**_
> 

## Hypothesis 3: (Could Have)
>
> _**There is no association between climate zone (cool/hot) and whether a country is a tea-dominant or coffee-dominant crop country.**_
>

# Potential Business Impacts & Applications of this Project
* For Tea importors / Buyer 
  * Armed with the knowledge of which cimate and GDP 


# Data Sources
The project uses data from:
* [Food and Agriculture Organization of the United Nations](https://www.fao.org/faostat/en/#data/QCL)
* WorldBank Economic data via the [wgapi package](https://pypi.org/project/wbgapi/)
* WorldBank Climate data via their [Climate Change Knowledge Portal](https://climateknowledgeportal.worldbank.org/download-data)


# Results & Findings  
* Part 1 





# Conclusion 
The 

# Limitations
* Choice and availablity of data 
  * While this analysis focuses on climate and economic factors, it acknowledges that tea yield is influenced by many other determinants such as the specific tea cultivars, terror (as a function of climate and soil conditions), skills of the tea growers and the feedback from the tea artisans, farming practices (as a function of agricultural methods and equipment and pest controls etc.)
  * As such, it important to note that  
    * the use of nationally aggregated data (temperature and precipitation) which inevitably masked within-country and/or within region variations.
    * the impact of the various tea plants cultivars, pest control implementation, soil quality, argriculture practices and the levels of government subsidies and support are not considered.
    * the use of nominal GDP per capita which does not allow cross-year comparisions.
* Model performance:
    




# Further Works
* To use GDP per capita (PPP in constant International $) instead of the Nominal GDP per capita used in this project to allow comparision across year. This valuation of GDP accounts for differences in cost of living (inflation) or purchasing power of national currencies between countries and can also be compared across years.
* Colonial impact


# Jupyter Notebooks
* For ETL and EDA 
  * FAO data [01_ETL_FAO.ipynb](notebooks/01_ETL_FAO.ipynb)
  * World Bank Climate and Economic data [02_ETL_WorldBank.ipynb](notebooks/01_ETL_WorldBank.ipynb)
* For Analysis [03_Analysis_Tea_Yield_Crop_Dominance.ipynb](notebooks/03_Analysis_Tea_Yield_Crop_Dominance.ipynb)

  
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


# Generic Real Estate Consulting Project

The target of this project:
The goal of this project is to provide Victoria's residential property rental market overview and some forecasts for rental prices. Subjective recommendations on livable SA2 districts are also offered with the help of statistical models.



This project should be generated in the following ORDER of notebooks:
1. data_pulling.ipynb: notebook file used to retrieve and reformate data directly with a collection of websites. (RUN ALL)
2. scrapy_VL.ipynb: notebook file used to retrieve, clean, and reformate live rental data from domain.com using every postcode (RUN PARTIAL, does not require running to retrieve data, modification to {file_size} and {count} recommended)
3. path_finding.ipynb: notebook file used to generate distance from rental property to some point of interest (RUN PARTIAL, does not require running to retrieve data, request and modify token manually, modification to {gap} and {rounds} recommended)
4. data_preprocessing.ipynb: notebook file used to process manually requested data (RUN ALL)
5. data_merging_VL.ipynb: notebook file used to reformate and concatenate all datasets into dataframe which indexed by {SA2}, by {SA2, year, quarter}, and by {property_id} (RUN ALL)
6. data_visualization.ipynb: notebook file used to plot illustration plots of the raw data (RUN ALL, plotting graphs shown in summary)
7. feature_selection.ipynb: this file generates the significance of features using linear regression
8. feature_predict_analysis.ipynb: this file demonstrates the relationship of the dataset generated in history_info
9. base_feature_selection.ipynb: this file generates the top10 significant features and determines the most important feature
    for predicting house prices
10. LSTM_predict.ipynb: this chapter is roughly divided into two parts, the first part uses a certain SA2 as an example to make a prediction, and the second part is to sort all SA2 after prediction. It returns the top10 growth_rate SA2 with suburb
    names.
11. growth_rate_pics.ipynb: this file visualises the map of suburbs' distribution with the top 10 predicted growth rate
12. liveable_suburbs_pics.ipynb: this file visualises the map of the most liveable and affordable suburbs' distribution 

13. summary.ipynb: A work-through file to introduce our project and explain the findings



ATTENTION:
    1. Some data need to be requested MANUALLY (BEFORE running data_preprocessing.ipynb):
        Website to sign up:
        - datashare: https://datashare.maps.vic.gov.au/
        - Click Sign up in the "Create an account" section and follow the instructions

        To request PTV.data manually:
        - https://datashare.maps.vic.gov.au/search?md=1792cbe0-25e5-52a0-8bc2-cc2294051634
        - sign in and add data to order
        - proceed to order configuration
        - select the geographical of GDA2020 and ESRI shape file format with "select all area available" option checked
        - the file will be sent to the given email
        - download and rename the file as PTV.zip, move it to ../data/raw/

        To request FOI.data manually:
        -  https://datashare.maps.vic.gov.au/search?md=019d7631-1234-5112-9f21-8f7346647b61
        - sign in and add data to order
        - proceed to order configuration
        - select the geographical of GDA2020 and ESRI shape file format with "select all area available" option checked
        - the file will be sent to the given email
        - download and rename the file as FOI.zip, move it to ../data/raw/

    2. OpenRouteService API need a token to request data (BEFORE running path_finding.ipynb):
        website to sign up:
        - https://openrouteservice.org/dev/#/signup
        - follow the instructions to sign up

        To get a token:
        - log in to https://openrouteservice.org/dev/#/home and scroll down to the lowest section
        - Select Token Type and Enter the Token name of your choice.
        - Click Create a token
        - The token will appear in the "Tokens" section

        To use token:
        - copy the token and replace it in {path_finding.ipynb}, variable named "TOKEN" in block 1
        - copy token and replace it in {data_visualization.ipynb}, variable named as "TOKEN" in block 1
    
    3. Scrapy_VL.ipynb and pathfinding.ipynb are codes used to request data using web crawling or API. The results have already been saved in {/data/raw/rent/rent_raw.csv}, {/data/raw/curated/rent_distance.csv}, and {sa2_to_cbd.csv}



Main Contributors:
    BO PAN
    JUNHUA LIU
    WEIQI HAO
    YANRONG ZHANG
    ZHENGHAN ZHANG



Contact:
    Junhua Liu - junhual1@student.unimelb.edu.au
    Weiqi Hao - wvhao@student.unimelb.edu.au
    Zhenghan Zhang - zhenghanz1@student.unimelb.edu.au
    Bo Pan - pbp@student.unimelb.edu.au
    Yanrong Zhang - yanrzhang@student.unimelb.edu.au

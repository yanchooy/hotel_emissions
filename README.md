# Global Hotel Emissions Trend 2016 - 2021
[View rendered notebook here](https://nbviewer.org/github/yanchooy/hotel_emissions/blob/main/global-hotel-emissions-trend-2016-2021.ipynb)

## Introduction
The Cornell Hotel Sustainability Benchmarking Index (CHSB) is an industry-led global data initiative, started in 2013 to enable any hotel to calculate its carbon footprint and benchmark its **energy, water and carbon emissions** at low cost, drawing from a dataset of over 25,000 hotels around the world. Participants in the CHSB index include major hotel brands, operators and owners, representing a total of 646 geographies (64 countries, 84 regions, 410 metro areas, 88 climate zones.)

5 datasets from year 2018 to 2023 (excluding 2022) is available for download [here](https://greenview.sg/services/chsb-index/). Each dataset covers the calendar year of 2 years prior to publishing year i.e. 2018 dataset will cover 2016 data. Due to the impact of Covid-19 on the hotel sector in 2020, the CHSB Index was not published in 2022, but resumed in 2023 with an analysis of 2021 performance.

## Project Goals
With datasets spanning 2016 - 2021 (excluding 2020) and the participation of 64 countries, I am curious to find answers to these questions:

1) What are the carbon emission trends from the past 5 years?
2) Where are the largest and lowest emissions? Can they exchange pointers?
3) As hotel building/operational standards are built upon its market segment classification, it will be interesting to compare emissions across different hotel segments?

## 2019 Data Import, Columns dropping and manipulation
- Data existed as multiple tabs within single excel workbook, needed to be imported and saved as multiple dataframes
- Dropping irrelevant columns containing statistics and granular market segments that were not used in this project
- Reorganising columns for ease of manipulation later

## Data cleaning and verification
- Checking missing values through null heatmaps
- Dropping geographic info that were incomplete to ensure country columns are complete
- Comparing mean and median values to decide which metric to use
- All 11 (out of 12) dataframes have mean-median differences above average of their individual mean-median difference. This suggests that most data within each dataframes have skewed distribution, where mean is larger than median, and median will be a better metric to use to calculate averages.
  
![mean_median_1](https://github.com/yanchooy/hotel_emissions/assets/109457905/cd6ca589-5772-4cbb-8de4-eb8470fcc0d9)
![mean_median_2](https://github.com/yanchooy/hotel_emissions/assets/109457905/c49025e8-9ff5-4ec4-91d2-c5efcb6e6b04)
![mean_median_3](https://github.com/yanchooy/hotel_emissions/assets/109457905/836c60ca-2888-4cfb-8842-8a75d9c7e570)

## Carbon emission - Highest and Lowest emitter  - All Hotels 2019
See documentation for detailed observations

![carbon_1](https://github.com/yanchooy/hotel_emissions/assets/109457905/a0751889-85bc-4a3e-a114-a309c520f963)
![carbon_2](https://github.com/yanchooy/hotel_emissions/assets/109457905/8334f020-8f1c-493e-a1c2-b9266aad4279)
![carbon_3](https://github.com/yanchooy/hotel_emissions/assets/109457905/60a7cdd2-d52a-4afa-9c2f-5e43debec65b)

## Carbon emission - Highest and Lowest emitter  - By hotel Segments 2019
Hotel market segments are divided into the following
- Economy and Midscale
- Upper Midscale
- Upscale
- Upper Upscale
- Luxury
See documentation for detailed observations
![carbon_seg_1](https://github.com/yanchooy/hotel_emissions/assets/109457905/2d86a577-e5ee-4bdf-9a64-ec72afc1f6fd)
![carbon_seg_2](https://github.com/yanchooy/hotel_emissions/assets/109457905/21343f20-fceb-46ab-aa19-a66541a50e97)
![carbon_seg_3](https://github.com/yanchooy/hotel_emissions/assets/109457905/ec0a31f3-4096-43a9-9721-bad4d6975a9b)

## Water and Energy usage - Highest and Lowest emitter - All Hotels & By Hotel Segments 2019
The same analysis was performed for water and energy usage.
See documentation for detailed observations and visualisation

## Comparing data across years between 2016 - 2021 
- Created function to import all 5 excel sheets in their multi-tabs into dataframes and perform same data cleaning
- Used plotly raceplot and lineplot to visualise top emitting countries changes throughout the years
![raceplot_1](https://github.com/yanchooy/hotel_emissions/assets/109457905/a2961134-2626-4183-afd9-75ced7908ebd)

![lineplot](https://github.com/yanchooy/hotel_emissions/assets/109457905/3c2cdc0b-8b20-48a9-b0f2-3da850f500c4)

# Carbon Emissions 2016 - 2021 conclusions
- Overall, for the top carbon emitting countries we are seeing a heartening **downward trend of carbon emissions across all four measures** - 1 night stay, total occupied room in a year, area per square metre and meeting area per square metre per area per hour.

- **With the exception of Vietnam, Hong Kong and Macau** there appears to be a boom recovery in room bookings after the Covid19 recess.

- While the other **top carbon emitting countries in 2016 like Saudi Arabia/ UAE are halving their emissions by 2021** in the per area square metre measure, **Hong Kong's carbon emissions remains worrying high and unwielding** for post-Covid MICE tourism boom.

- **Maldives appears to take an extremely high carbon emission position**, and due to lack of data in some years, it is hard to determine the direction of its trend.

- Earlier we found that **Costa Rica, France, Switzerland, Brazil are consistently low carbon emitting countries in 2019**, while it's worth checking what they have doing well, it is more **fascinating that the world's largest oil producers Saudi Arabia and UAE are able to slash their emissions so quickly within these 5 years**. While there are no details on hotel industry there, projects such as Saudi Green Initiative is a glimmer of hope to where there is a will, there is a way.

## Next Steps
With carbon emission far from net zero, and practically **flat progress in renewable energy adoption on site(as per data) within the past 5 years**, it is worth investigating:

- What are the ways (and projected effectiveness) the hotel industry are working on to bring down their carbon footprints?
- Given each hotel brand has their own sustainability approach, breaking down the analysis into brands comparison (if we can get our hands on the data), to see if there is any information sharing on best practice?

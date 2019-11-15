# South King County Opportunity Youth

This project offers an updated estimate of the number of Opportunity Youth in South King County using the 2017 5-year American Community Survey [(ACS)](https://www.census.gov/programs-surveys/acs/about.html) Public Use Microdata Survey [(PUMS)](https://www.census.gov/programs-surveys/acs/technical-documentation/pums.html).

## Setup Instructions

To download the necessary data, please run the following command:

```bash
# installs necessary requirements and downloads necessary data
# note: this may take anywhere from 10-20 minutes
sh setup.sh
```

### `oy-env` conda environment

This project relies on you using the [`environment.yml`](environment.yml) file to recreate the `oy-env` conda environment. To do so, please run the following commands:

```bash
# create the oy-env conda environment
# note: this make take anywhere from 10-20 minutes
conda env create -f environment.yml

# activate the oy-env conda environment
conda activate oy-env

# make oy-env available to you as a kernel in jupyter
python -m ipykernel install --user --name oy-env --display-name "oy-env"
```







## METHODS: (pulled straight from our Jupiter Notebook)
## Import Data
<!-- Use the associated opportunity_youth.sql file in this repository to run postgreSQL queries to retrieve the opportunity youth summary data from the database. Run the following commands in your terminal: -->
psql opportunity_youth
<!-- <- Make sure this path points to the .sql file in this repository! -->
\i .\opportunity_youth.sql 

## The first big task in our JN is to create all of the Pandas Data Frames that we use in the analyis.
<!-- This is performed by the pullsqldata() function in our .py file. These data frames are created by first using sqlalchemy to perform sql queries, then they use the pandas method to put the results of these queries into DataFrames.  -->

## The next big task is finding the # of Opportunity Youth 
<!-- We do this by summing the pwgtp column from the data frame opp_youth. Our OY Population appears to be 12438.  -->

## Calculating Opportunity Youth Status by Age
<!-- The 2016 report on opportunity youth contains a table showing total opportunity youth and total youth by age, their education status, and their employment status. We recalculate these statistics using the updated information for 2017. To see the original data, see page two in https://roadmapproject.org/wp-content/uploads/2018/09/Opportunity-Youth-2016-Data-Brief-v2.pdf.
The following tables stored in pivot_total_youth_pop and poptotals replicate the original tables and show the breakdown of our estimates of South King Co. youth by their age bracket (16-18, 19-21, or 22-24) and their employment/education status (not an Opportunity Youth, an Opportunity Youth, or a youth working without a HS diploma or GED). We also show the percentage that each of these segments makes up of the total youth population. -->

## Calculating Education Achievement of 2017 Opportunity Youth
<!-- The following two tables contain similar statistics as the previous two tables, but divide up the opportunity youth of South King Co. by their level of education: those without a diploma, those with a HS diploma or GED, those with some college credits but no degree, or those with a college degree (associates or higher). -->

##  Key results from comparing 2017 data to 2014 data
<!-- To compare our updated statistics on opportunity youth in South King County, we included four .csv files in this repository that replicate the data from the 2016 report which were imported into dataframes at the beginning of this Notebook. Below, we plot these datasets side-by-side to highly trends between 2014 and 2017.
The overall youth population has decreased

First, we plot the total number of youths ages 16-24 in the region of interest. We see that there is a drop from approximately 140,000 individuals in the 2014 census to about 115,000 in 2017. -->

## The proportion of opportunity youth in South King Co. has decreased
<!-- Taking into consideration that the total number of youths have decreased, we also see that the percentage of 16-24 year olds in South King County that qualify as opportunity youths have also decreased by about one percent. -->

## The proportion of opportunity youths have decreased across all three age ranges
<!-- The following plots show the percentage of the youth population in the three age groups. In the opportunity youth specifically, the percentage has decreased in all three groups, with the largest decrease in 22-24 year olds, which now make up a smaller percentage of opportunity youth than the 19-21 year olds, a reversal from the 2014 data. -->

## The proportion of opportunity youths with college experience has decreased
<!-- Finally, we plotted the level of education attained by opportunity youths between 2014 and 2017. Opportunity youths that have not completed any schooling other than high school or their GED have increased in proportion compared to those who have college experience, which have decreased in number since 2014. -->

## Visualizing the Opportunity Youth across South King County
<!-- Because population statistics tend to have a spatial dependency, it is important to visualize the Opportunity Youth across the South King County region. We were provided shape files for the puma regions that we were studying, so first we wanted to visualize our defined region. We did this by using the Folium and Geopandas packages which simplify live map production. The following function creates our live Folium Map displaying the region that we studied. -->

## Visualize the spatial distribution of the Opportunity Youth across South King County
<!-- Seeing the region is nice, but it does not add much when trying to interpret trends. Our next step was to visualize the distribution of the OY population across this region. We first call a function that adds the columns to the geopandas dataframe containing: total estimated OY, total youth population, and percent OY. For both of the following maps, we chose to avoid any data classification and instead visualize the population data as continuous. -->

<!-- Next, we call a function to create a choropleth map visualizing total OY pop by puma region. This map makes it clear that the largest OY populations reside in the southern and western urban areas of Seattle, and Vashon Island. The lowest OY populations reside closer to the center of Seattle, Central District, and Beacon Hill. -->

<!-- Finally, we gain more insight by visualizing the OY percent of total youth population across the region. This is potentially a useful metric for interpretation because in a way it normalizes less and more densely populated regions. For example, we can see that the Maple Valley, Hobart, and Eumenclaw region has a faily high percent of OY despite the relatively low total OY population. We can also see that the Tukwila/South West Seattle puma region has both a high total OY population and a high percent of youth. -->


## Future Directions
<!-- This preliminary exploration of the data is contingent on several assumptions based on the original analysis, mainly the selection of geographic areas in South King Co. and the criteria set forth for identifying opportunity youth. We recommend obtaining the 2014 data and following our methods to ensure direct comparability between the datasets.
Furthermore, we would like to explore the trends surrouding the decrease of the total youth population in S. King Co. We would suggest mapping youth population across King Co. to test whether youth population has remained steady or grown, but moved out of S. King Co.
Finally, our finding that there are fewer opportunity youth with college experience suggests that employment opportunities are higher for youth with college degrees. We suggest exploring this trend further by gathering employment data such as employment rates, employment sectors for youths, and the requirements these jobs may have. -->





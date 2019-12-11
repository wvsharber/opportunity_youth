# Data

Scripts to download or generate data.

### Import Data
Use the associated opportunity_youth.sql file in this repository to run postgreSQL queries to retrieve the opportunity youth summary data from the database. Run the following commands in your terminal:

psql opportunity_youth

\i .\opportunity_youth.sql <- Make sure this path points to the .sql file in this repository!

The following command will pull the associated data into dataframes to be used in the rest of this Notebook.
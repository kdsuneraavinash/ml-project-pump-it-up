# ML Project - Pump It Up

Repository: [Repo](https://github.com/kdsuneraavinash/ml-project-pump-it-up)

Notebook: [notebook.ipynb](https://github.com/kdsuneraavinash/ml-project-pump-it-up/blob/master/notebook.ipynb)

Used models: RandomForest, NN (Provided by FastAI) and CatBoost

Competition Link: [Link](https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table)

---

## Missing Values

Following columns had missing values: funder, installer, subvillage, public_meeting, scheme_management, scheme_name, permit and status_group. scheme_name for instance had closer to 50% missing values. 

There weren't missing values in numerical columns, but there were several columns with big 0 value percentage. (so, they could have been originally missing values, but filled with 0) amount_tsh for instance had about 70% 0 values.

## Information on Columns

amount_tsh, as mentioned before had a huge 0 value percentage. However, there was a significant difference of status_group values between the rows with 0 value and non-zero value.

Date recorded seems to have a low impact on the status_group. There were clearly 3 recorded date sections (clusters),  ones before 2010, between 2010 and  2012 June and after 2012 June. However, the before 2010 had significanly less data points and there was not a huge difference between the statistics between the other two.

Funder had a large cardinality. But seems to affect status_group. Also noticed that the funder consited of text that is sometimes misspelled or partial.

gps_height seemed to also have large number of zero values (~35%). After removing them, was able to notice that it had some relation with status_group.

Installer was similar to funder. It also had a large cardinality mainly due to the categories being just text. (So there were names, abbreviations, misspelled organizations, etc...)

Longitude and latitude had 2 primary clusters. One cluster around  tanzania and others near (0, 0) coordinate. (0, 0) is probably missing values. After removing them was able to identify that there is a relation between the location and status_group. Might have to replace (0, 0) coordinates with some good value.

wpt_name was also similar to funder and installer. High cardinality (45684 values). But after combining the values with low counts, the cardinality was reduced.

region and region_code had a lot of overlaps. The same was true for (extraction_type, extraction_type_group, extraction_type_class) and (management, management_group) and (water_quality and quality_group) and (quantity, quantity_group) and (source, source_type, source_class) and (waterpoint_type, waterpoint_type_group). Some of the mentioned columns were groupings of others, so might be safe to remove.

recorded_by column had only one value. So it is not relavent.

## Screenshot

![Screenhot_2021-09-17_13-53](https://user-images.githubusercontent.com/34407567/133750385-ad102f83-17a0-4ab3-9038-47ad30b1deea.png)



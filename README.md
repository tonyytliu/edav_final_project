# STAT 5702 EDAV Final Project
## Group 8

Yitao Liu (yl4343), Boyu Liu (bl2788), Yiyang Sun (ys3284)


## Data Source
UCDP Georeferenced Event Dataset (GED) Global version 19.1 [[source]](https://ucdp.uu.se/downloads/index.html#ged_global)

Also in [`data/raw`](https://github.com/tonyytliu/edav_final_project/tree/master/data/raw).

## Data Processing
The original dataset lists conflicts based on their ids. Different conflicts have different durations. Some conflicts last for one day while some others last for months. In the following studies, we might be interested in finding the pattern based on day/month. Therefore, in the data processing stage, we may want to transform the original dataset into a new one, which records the conflict based on each date, as follows:

Transform

 id | date_start |  date_end  | death 
----|------------|------------|-------
 01 | 2000-01-01 | 2000-01-01 |   10 
 02 | 2000-01-01 | 2000-01-03 |   90  

to

 id | date_start |  date_end  | death |   dates    | avg_death
----|------------|------------|-------|------------|----------
 01 | 2000-01-01 | 2000-01-01 |   10  | 2000-01-01 | 10
 02 | 2000-01-01 | 2000-01-03 |   90  | 2000-01-01 | 30
 02 | 2000-01-01 | 2000-01-03 |   90  | 2000-01-02 | 30
 02 | 2000-01-01 | 2000-01-03 |   90  | 2000-01-03 | 30

Code for such transforming please refer [`Data_Processing.Rmd`](https://github.com/tonyytliu/edav_final_project/blob/master/data/Data_Processing.Rmd); the transformed data file is in [`data/clean`](https://github.com/tonyytliu/edav_final_project/blob/master/data/clean/).

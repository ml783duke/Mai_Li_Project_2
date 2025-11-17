# Air Pollution & Sickle Cell Disease – Project 2

## Overview
This repository contains code and data for Project 2, which explores associations between ambient air pollution and sickle cell disease (SCD)–related health care utilization in Durham County, North Carolina. The main goals are to clean daily air quality data (CO, PM2.5, O3) from the RDU monitor and to perform exploratory plots for downstream epidemiologic analysis. 

## Data
- `AQ_2018.csv`
- `AQ_2019.csv`
- `AQ_2020.csv` (data available through April 2020 only)

Each file contains daily measurements of:
- Daily max 8-hour CO concentration  
- Daily mean PM2.5 concentration  
- Daily max 8-hour Ozone concentration 

All measurements come from the EPA air quality monitor at RDU airport.

## Main files
- `Mai_LI_Project_2.Rmd` – Main R Markdown file with data processing, EDA, and plots.
- `AQ_2018.csv`, `AQ_2019.csv`, `AQ_2020.csv` – Raw daily air quality datasets.

The R Markdown is designed to knit to a Word document as the final project report.

## Methods
A single processing function is used to clean each yearly dataset. For each file, the function: 
- Renames pollutant concentration columns to short, informative variable names without spaces.  
- Parses and formats the date variable.  
- Averages multiple measurements for the same pollutant on the same day to obtain a daily mean.  
- Removes duplicate rows.  
- Loops over pollutant variables and replaces any negative measured concentration with zero.

The cleaned datasets are then combined for plotting.

## Plots
The project generates two main plots: 
1. **Monthly CO & O3 plot**  
   - x-axis: month (1–12)  
   - y-axis: concentration  
   - Points: monthly averages averaged over 2018–2020  
   - 95% confidence interval error bars around each point  
   - CO and O3 shown in different colors  

2. **Monthly PM2.5 by year plot**  
   - x-axis: month (1–12)  
   - y-axis: PM2.5 concentration  
   - Color: year (2018, 2019, 2020)  
   - Geometry chosen to best visualize temporal patterns across years.

## How to reproduce
1. Open this folder as an R Project in RStudio.  
2. Open `Mai_LI_Project_2.Rmd`.  
3. Install any required packages listed at the top of the Rmd.  
4. Knit the document to Word to reproduce the tables and figures.

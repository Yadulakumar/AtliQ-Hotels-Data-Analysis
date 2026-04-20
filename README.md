# AtliQ Hotels Data Analysis 🏨

## Project Overview
This project analyzes the booking and revenue data for AtliQ Hotels, a fictional hotel chain operating in multiple cities in India (Mumbai, Delhi, Bangalore, and Hyderabad). The goal is to uncover insights regarding occupancy rates, revenue generation, and booking trends across different room categories and day types.

## Tools & Libraries Used
* **Python**: Primary programming language.
* **Pandas**: Used for data manipulation, cleaning, and aggregation.
* **Matplotlib**: Used for basic data visualization.
* **Jupyter Notebook**: Interactive environment for code execution and analysis.

## Dataset Structure
The analysis relies on multiple relational datasets stored in the `datasets/` directory:
* `dim_date.csv`: Contains dates, week numbers, and day types (weekday/weekend).
* `dim_hotels.csv`: Contains property IDs, hotel names, categories (Luxury/Business), and cities.
* `dim_rooms.csv`: Contains room IDs and room classes (Standard, Elite, Premium, Presidential).
* `fact_aggregated_bookings.csv`: Contains aggregated data on successful bookings and total capacity per property and room type.
* `fact_bookings.csv`: Granular data containing individual booking IDs, guest counts, revenue generated, and revenue realized.

## Methodology
1. **Data Exploration**: Imported datasets and analyzed data frames to understand shape, unique values, and distributions.
2. **Data Cleaning**: 
   * Filtered out invalid data entries (e.g., negative values for the number of guests).
   * Handled outliers in the `revenue_generated` column using the Mean + 3 Standard Deviations approach.
   * Addressed missing values logically (e.g., retained rows with null ratings as they represent users who simply didn't leave a review).
3. **Data Transformation**: 
   * Engineered new features, such as calculating the Occupancy Percentage (`occ_pct`).
   * Merged dimension tables (`dim_rooms`, `dim_hotels`, `dim_date`) with fact tables to create a comprehensive, analyzable dataset.
4. **Insights Generation**: Aggregated data to answer specific business questions regarding revenue and occupancy.

## Key Insights Discovered
* **Occupancy by Day Type**: Weekends see a significantly higher average occupancy rate (~72.3%) compared to weekdays (~50.9%).
* **Occupancy by City (June 2022)**: Delhi led with the highest occupancy rate (62.47%), followed by Hyderabad (58.46%), Mumbai (58.38%), and Bangalore (56.44%).
* **Total Revenue Realized**: Mumbai generated the highest total revenue among all cities (₹668,569,251).
* **Monthly Revenue**: May 2022 generated the highest revenue (₹408,375,641), followed by July and June.

## How to Run This Project
1. Clone this repository to your local machine.
2. Ensure you have Python installed, along with `pandas` and `matplotlib`.
3. Open `hotels_analysis.ipynb` in Jupyter Notebook or JupyterLab.
4. Run the cells sequentially to view the analysis and data transformations.

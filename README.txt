# Week 1 Data Engineering Lab

## Scenario
A small online shop sends daily order data as a CSV file. A manager wants a reliable summary of valid orders by city.

## Pipeline plan
- Source: `orders.csv` (daily batch file)
- Raw destination: BigQuery table `de_intro.raw_orders`
- Curated output: query results after checking and filtering the data
- User of the output: shop manager

## Local data check
Before reporting, record at least two issues you found in the CSV and what you recommend doing with each.

1. Issue and recommendation: There is a missing value not handled in the csv I suggest filling it with the most frequent value or dropping it 
2. Issue and recommendation: the second issue is that there are a value of zero in the quantity and a value of zero in the total amount 
3. Issue and recommendation: There is duplicates that must be dropped. 

Raw table: de_intro.raw_orders - Rows loaded: 8 - Rows with a missing city: 1 - Rows with a non-positive quantity: 1 - Rows returned by the filtered query: 5 
## What the pipeline does
Complete after the lab: In one sentence, describe how the data moves from the source to a useful output.
We clone the data make commits then we used Big Query. A daily orders.csv file is loaded into a raw BigQuery table, then a SQL query removes rows with missing cities, non-positive quantities, and duplicate order IDs, producing a clean set of valid orders for the shop manager.

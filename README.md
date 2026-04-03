# Automotive Industry Trends Pipeline

This project implements a Databricks medallion-style pipeline to analyze automotive industry trends using three public datasets:

- NHTSA Vehicle Complaints
- DOE Alternative Fuel Stations
- EPA Vehicle Fuel Economy

## Architecture
- **Bronze**: raw ingestion with minimal changes
- **Silver**: cleaning, standardization, and controlled type handling
- **Gold**: aggregated analytical tables

## Main outputs
- `gold.complaints_analysis`
- `gold.vehicle_efficiency`
- `gold.alt_fuel_infrastructure`

## Notebooks
- `00_common_functions`: shared helper functions used across the pipeline
- `00_catalog_and_schemas_setup`: one-time catalog and schema creation
- `01_bronze_ingestion`: raw ingestion into bronze tables
- `02_silver_complaints`: cleaning and standardization of complaints data
- `03_silver_vehicle_fuel_economy`: cleaning and standardization of fuel economy data
- `04_silver_alt_fuel_stations`: cleaning and standardization of fuel stations data
- `05_gold_complaints_analysis`: aggregated complaint metrics
- `06_gold_vehicle_efficiency`: aggregated efficiency metrics
- `07_gold_alt_fuel_infrastructure`: aggregated infrastructure metrics

## Run order
1. `00_catalog_and_schemas_setup`
2. `01_bronze_ingestion`
3. `02_silver_complaints`
4. `03_silver_vehicle_fuel_economy`
5. `04_silver_alt_fuel_stations`
6. `05_gold_complaints_analysis`
7. `06_gold_vehicle_efficiency`
8. `07_gold_alt_fuel_infrastructure`

## Repository contents
- notebooks / scripts
- processed data
- PowerPoint presentation

## Notes
The loading step was simulated by writing Delta tables in Databricks.  
A daily batch schedule is recommended for automation.

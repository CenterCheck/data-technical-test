# Data Technical Test: Location Matching & Revenue Analysis

## Overview
This test evaluates your ability to solve real-world data linkage challenges and analyze business metrics. The problem contains two core components:
1. Matching similar-but-nonidentical business locations across datasets
2. Developing a revenue adjustment methodology

We emphasize methodological rigor over specific implementation choices.

## Problem Statement

### Part A: Location Matching
Create a linkage solution between:
- `raw_financials` (financial records)
- `business_location` (POI location data)

Key requirements:
- Matching must account for name/address variations
- Simple string equality is insufficient
- Document your matching strategy's assumptions

### Part B: Revenue Analysis
1. Create `financial` table with:
   - Matched location IDs
   - Raw/adjusted revenue columns
2. Develop a multiplier system for revenue adjustment: assuming the raw revenue is only card transactions, create a method to estimate the total revenue (all transactions types)
3. Create comparative visualizations
4. Address theoretical validation questions

## Theoretical Considerations
In your solution, briefly address:

1. **Statistical Validation**  
"If we had verified sales data for a subset of locations:  
- How would you calculate the minimum sample size needed to statistically validate your matching approach?  
- What parameters would this calculation depend on?"

2. **Model Comparison**  
"If comparing multiple revenue adjustment models:  
- What metrics would you use to evaluate superiority?  
- How would you ensure comparison validity?"

## Data Structure

### raw_financials (s3://centercheck-shared-data-science-technical-test/raw_financials.parquet - [download](https://centercheck-shared-data-science-technical-test.s3.us-west-2.amazonaws.com/raw_financials.parquet))
`id | name | address | city | state | postal code | start_at | end_at | revenue`

### business_locations (s3://centercheck-shared-data-science-technical-test/business_locations.parquet - [download](https://centercheck-shared-data-science-technical-test.s3.us-west-2.amazonaws.com/business_locations.parquet))
`id | business_entity_id | name | street_address | city | state | postal_code | area_sq_ft`

Note: Contains real-world inconsistencies (address typos, name variations)

## Deliverables
1. Jupyter Notebook with:
   - Reproducible data processing pipeline
   - Implemented solution
   - Visualizations
   - Theoretical answers

2. CSV/DataFrame of `financial` table

3. Brief report containing:
   - Methodology justification
   - Key assumptions
   - Solution limitations

## Evaluation Criteria
1. Matching methodology:
   - Handling of real-world data inconsistencies
   - Documentation of tradeoffs

2. Revenue analysis:
   - Logical justification for adjustment approach
   - Visualization clarity

3. Theoretical understanding:
   - Relevance of statistical concepts
   - Metric selection rationale

4. Code quality:
   - Reproducibility
   - Modularity
   - Documentation

## Submission Requirements
- Python 3.8+ solution
- Self-contained environment setup
- Clear README for reproduction
- 1-week completion window

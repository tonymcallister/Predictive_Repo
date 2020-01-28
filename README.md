# Predictive Maintenance
There are a lot of unscheduled maintenance events that cause delays and disruptions on turbofan engines.

# Datasets
https://ti.arc.nasa.gov/tech/dash/groups/pcoe/prognostic-data-repository/#turbofan.

NASA Turbofan fault dataset produced from the C-MAPP aircraft health monitoring tool.
Engine degradation simulation was carried out using C-MAPSS. Four different were sets simulated under different combinations of operational conditions and fault modes. Records several sensor channels to characterize fault evolution. The data set was provided by the Prognostics CoE at NASA Ames.

Data Elements:
* unit number
* time, in cycles
* operational setting 1
* operational setting 2
* operational setting 3
* sensor measurement 1
* sensor measurement 2 ...
* sensor measurement 26

Wishlist data:

* Historical Pilot reports of incidents
* Flight crew maintenance observations
* Maintenance log books
* Weather/Turbulence conditions
* Frequency of use
* Load conditions
* Geographic location of hangar
* Fuel Quality

# Modeling Strategy
1. Check data quality - clean noise 
- e.g. per readme.txt file, the data is contaminated with sensor noise
- scrub timestamps to common format
- create new column (FAN_ID) in RUL* file
2. EDA
- Plot sensor reading values  against operational settings (define independent and dependent variables)
- Remove features that do not matter
- Calculate RUL for training set by engine type
- Merge RUL to test data to prepare for validation
3. Create Regression Model
4. Train, Test, Validate

# End Goal
Calculate RUL for an engine type using sensor readings and operational settings to alert engineers when engine is getting close to end of life.

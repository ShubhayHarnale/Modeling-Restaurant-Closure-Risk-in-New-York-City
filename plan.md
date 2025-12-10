# Project Implementation Plan - Final Project

**Project:** Predicting Restaurant Inspection Scores in New York City  
**Authors:** Nicholas Martino (nsm143), Shubhay Harnale (sh1615)  
**Timeline:** 2 Days to Completion

---

## ✓ COMPLETED - Phase 1: Data Acquisition & Exploration

### Step 1: Environment Setup ✓
- Created project directory structure
- Set up Python virtual environment
- Installed core dependencies

### Step 2: Data Acquisition ✓
- ✅ Downloaded DOHMH NYC Restaurant Inspection Results
- ✅ Downloaded NYPD Complaint Data Historic (CSV)
- ✅ Downloaded PLUTO dataset (CSV)
- ❌ Yelp data not used (no NYC coverage)

### Step 3: Initial Data Exploration ✓
- Created exploratory Jupyter notebooks for each dataset
- Cleaned DOHMH data to restaurant-level table (26,572 restaurants)
- Cleaned NYPD data (9.49M crime records)
- Cleaned PLUTO data (857K property records)

---

## 🚀 FINAL PROJECT - Remaining Work

### Day 1: Data Integration & Feature Engineering ✅ COMPLETE

#### Task 1: Complete Data Cleaning ✅ DONE
- ✅ Finish NYPD data cleaning notebook (9,491,467 crime records)
- ✅ Finish PLUTO data cleaning notebook (857,025 property records)
- ✅ Finish DOHMH data cleaning notebook (26,572 restaurants)

**Deliverables:**
- ✅ `nypd_complaints_clean.csv`
- ✅ `pluto_nyc_clean.csv`
- ✅ `dohmh_restaurants_clean.csv`

#### Task 2: Create Master Dataset ✅ DONE
**In notebook: `data_integration.ipynb`**
- ✅ Load all three cleaned datasets
- ✅ Create geospatial features using cKDTree:
  - ✅ Count crimes within ~500m of each restaurant
  - ✅ Match restaurants to nearest PLUTO property records
- ✅ Merge all data into single master dataset

**Deliverables:**
- ✅ `master_restaurant_dataset.csv` with all features combined
- ✅ Feature set: inspection scores, crime counts, property values, building age

---

### Day 2: Modeling & Demo Notebook

#### Task 3: Feature Engineering ✅ DONE
**In notebook: `feature_engineering.ipynb`**
- ✅ Create features from merged data:
  - ✅ Crime density (crimes_nearby)
  - ✅ Property value (property_assesstot)
  - ✅ Building age (property_yearbuilt)
  - ✅ Cuisine category encoding
  - ✅ Borough & ZIP code encoding
- ✅ Handle missing values (none found after cleaning)
- ✅ Train/test split (80/20)

**Deliverables:**
- ✅ Final feature matrix ready for modeling (X_train, X_test, y_train, y_test)
- ✅ Clear documentation of features

#### Task 4: Build Predictive Model 
**In notebook: `modeling_and_results.ipynb`**
- **Option A - Regression:** Predict inspection score (0-100+)
  - Linear Regression, Random Forest Regressor, XGBoost
  - Evaluate with RMSE, MAE, R²
- **Option B - Classification:** Predict grade (A vs B vs C)
  - Logistic Regression, Random Forest, XGBoost
  - Evaluate with accuracy, precision, recall, F1
- Feature importance analysis
- Create visualizations

**Deliverables:**
- Trained models saved in `models/` folder
- Performance comparison table
- Feature importance insights

#### Task 5: Demo Preparation 
**Create: `DEMO_NOTEBOOK.ipynb`**
- Clean, executive-summary style notebook showing:
  1. Problem statement & research question
  2. Data overview (3 sources, key statistics)
  3. Sample integrated data (restaurant + crime + property features)
  4. Model results (performance metrics, feature importance)
  5. Example predictions (restaurants with predicted scores)
  6. Key insights (what factors influence inspection scores?)

**Deliverables:**
- Professional demo notebook with clear narrative
- All visualizations polished and labeled
- Results interpretation for non-technical audience

---

## Data Sources

| Dataset | Source | Records | Key Fields |
|---------|--------|---------|------------|
| **DOHMH Inspections** | [NYC Open Data](https://data.cityofnewyork.us/Health/DOHMH-New-York-City-Restaurant-Inspection-Results/43nn-pn8j) | 26,572 restaurants | scores, grades, lat/long |
| **NYPD Complaints** | [NYC Open Data](https://catalog.data.gov/dataset/nypd-complaint-data-historic) | 9.49M records | crime type, severity, lat/long |
| **PLUTO** | [NYC Open Data](https://data.cityofnewyork.us/City-Government/Primary-Land-Use-Tax-Lot-Output-PLUTO-/64uk-42ks) | 857K records | building age, value, land use |

---

## Success Criteria for Demo

The demo should clearly show:
1. ✅ Data from 3 sources successfully integrated
2. ✅ Meaningful features extracted (crime density, property characteristics)
3. ✅ Working predictive model with reasonable performance
4. ✅ Clear insights about what neighborhood factors influence inspection scores
5. ✅ Professional visualizations and presentation

---



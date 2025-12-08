# Project Implementation Plan - Final Project

**Project:** Modeling Restaurant Closure Risk in New York City  
**Authors:** Nicholas Martino (nsm143), Shubhay Harnale (sh1615)  
**Timeline:** 2 Days to Completion

---

## ✓ COMPLETED - Phase 1: Data Acquisition & Exploration

### Step 1: Environment Setup ✓
- Created project directory structure
- Set up Python virtual environment
- Installed core dependencies

### Step 2: Data Acquisition ✓
- Downloaded Yelp Open Dataset (JSON format)
- Downloaded NYPD Complaint Data Historic (CSV)
- Downloaded PLUTO dataset (CSV)

### Step 3: Initial Data Exploration ✓
- Created exploratory Jupyter notebooks for each dataset
- Filtered Yelp data to NYC restaurants only
- Analyzed closure rates, ratings, and business characteristics
- Explored crime data structure and temporal patterns
- Examined property tax data structure

---

## 🚀 FINAL PROJECT - Remaining Work

### Day 1: Data Integration & Feature Engineering

#### Task 1: Complete Data Cleaning ✅ DONE
- ✅ Finish NYPD data cleaning notebook 
- ✅ Finish PLUTO data cleaning notebook
- ✅ Save all cleaned datasets

**Deliverables:**
- ✅ `nypd_complaints_clean.csv`
- ✅ `pluto_nyc_clean.csv`
- ✅ `yelp_restaurants_nyc.csv`

#### Task 2: Create Master Dataset
**In new notebook: `04_data_integration.ipynb`**
- Load all three cleaned datasets
- Create simple geospatial features using pandas:
  - Count crimes within 0.01° (~1km) of each restaurant
  - Match restaurants to PLUTO records by nearest coordinates
- Merge all data into single master dataset

**Deliverables:**
- `master_restaurant_dataset.csv` with all features combined
- Simple feature set: ratings, review_count, crime_nearby, property_value, building_age

---

### Day 2: Modeling & Demo Notebook

#### Task 3: Feature Engineering 
**In notebook: `05_feature_engineering.ipynb`**
- Create basic features from merged data:
  - Restaurant age (if dates available)
  - Price tier encoding
  - Top 5-10 cuisine categories as binary flags
  - Crime density bins (low/medium/high)
  - Simple rating features (stars, review count bins)
- Handle missing values (simple imputation)
- Train/test split (by date if possible, otherwise random 80/20)

**Deliverables:**
- Final feature matrix ready for modeling
- Clear documentation of features

#### Task 4: Build Predictive Model 
**In notebook: `06_modeling_and_results.ipynb`**
- Train 2-3 simple models:
  - Logistic Regression (baseline)
  - Random Forest
  - Gradient Boosting (XGBoost or LightGBM)
- Evaluate with accuracy, precision, recall, F1, ROC-AUC
- Feature importance analysis
- Create visualizations:
  - ROC curves
  - Feature importance bar chart
  - Confusion matrix
  - Predicted risk distribution

**Deliverables:**
- Trained models saved in `models/` folder
- Performance comparison table
- Feature importance insights

#### Task 5: Demo Preparation 
**Create: `DEMO_NOTEBOOK.ipynb`**
- Clean, executive-summary style notebook showing:
  1. Problem statement (2 cells)
  2. Data overview (3-4 cells with key statistics)
  3. Sample integrated data (show restaurant + crime + property features)
  4. Model results (accuracy, ROC curve, feature importance)
  5. Example predictions (show 5-10 restaurants with risk scores)
  6. Key insights and findings (2-3 takeaways)

**Deliverables:**
- Professional demo notebook with clear narrative
- All visualizations polished and labeled
- Results interpretation for non-technical audience

---

## Simplified Scope for 2-Day Timeline

**What We're DOING:**
- ✅ Using pandas for all data processing (no database needed)
- ✅ Simple geospatial joins using coordinate proximity
- ✅ Basic feature engineering with existing data
- ✅ Standard ML models (sklearn, xgboost)
- ✅ Clear visualizations and interpretability

**What We're SKIPPING:**
- ❌ PostgreSQL database setup (too time-consuming)
- ❌ Complex geospatial queries with PostGIS
- ❌ Advanced feature engineering (time series analysis, NLP on reviews)
- ❌ Deep learning models
- ❌ Extensive hyperparameter tuning
- ❌ Production deployment

## Expected Final Deliverables

1. **Notebooks** (6 total):
   - `yelp_exploration.ipynb` ✅
   - `nypd_exploration.ipynb` ✅
   - `pluto_exploration.ipynb` ✅
   - `data_integration.ipynb` (NEW)
   - `feature_engineering.ipynb` (NEW)
   - `modeling_and_results.ipynb` (NEW)
   - `DEMO_NOTEBOOK.ipynb` (NEW - for presentation)

2. **Processed Data**:
   - All cleaned CSVs in `data/processed/`
   - Master dataset with all features

3. **Models**:
   - Saved model files in `models/`
   - Performance metrics summary

4. **Documentation**:
   - Updated README with results
   - Final report summarizing findings

---

## Success Criteria for Demo

The demo should clearly show:
1. ✅ Data from 3 sources successfully integrated
2. ✅ Meaningful features extracted (crime, property, business characteristics)
3. ✅ Working predictive model with reasonable performance (>70% accuracy)
4. ✅ Clear insights about what factors predict restaurant closure
5. ✅ Professional visualizations and presentation


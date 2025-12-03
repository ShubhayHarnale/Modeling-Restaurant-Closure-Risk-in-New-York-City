# Project Implementation Plan - Interim Report

**Project:** Modeling Restaurant Closure Risk in New York City  
**Authors:** Nicholas Martino (nsm143), Shubhay Harnale (sh1615)

## Phase 1: Project Setup & Data Acquisition

### Step 1: Environment Setup ✓
- Create project directory structure
- Set up Python virtual environment
- Install core dependencies (pandas, numpy, jupyter, sqlalchemy)
- Initialize Git repository

**Deliverables:**
- `requirements.txt` with all dependencies
- Organized folder structure (`data/`, `notebooks/`, `src/`, `sql/`)

### Step 2: Data Acquisition ✓
- Download Yelp Open Dataset (JSON format)
- Download NYPD Complaint Data Historic (CSV)
- Download PLUTO dataset (CSV)
- Store all raw data in `data/raw/` directory

**Deliverables:**
- All three datasets downloaded and documented
- Data dictionary/readme describing each dataset's structure

### Step 3: Initial Data Exploration
- Clean up data using SQL
- Create exploratory Jupyter notebooks for each dataset
- Understand data schemas and formats
- Check data quality (missing values, duplicates, outliers)
- Filter Yelp data to NYC restaurants only
- Verify geospatial coordinates are valid

**Deliverables:**
- `01_yelp_exploration.ipynb` - Basic statistics, closure rates, category distributions
- `02_nypd_exploration.ipynb` - Crime patterns, temporal trends, geospatial coverage
- `03_pluto_exploration.ipynb` - Property characteristics, tax lot distributions

**Key Metrics to Report:**
- Number of NYC restaurants in Yelp dataset
- Percentage of closed vs. open restaurants
- Date range of reviews available
- Number of crime incidents in dataset
- Coverage area of PLUTO data

## Phase 2: Database Design & Implementation

### Step 4: Database Schema Design
- Design relational schema for three data sources
- Create Entity-Relationship (ER) diagram
- Define primary and foreign keys
- Plan indexing strategy for geospatial queries

**Deliverables:**
- `schema.sql` with table definitions
- ER diagram (PDF/PNG)
- Documentation of join strategies

### Step 5: Data Loading Pipeline
- Set up PostgreSQL database with PostGIS extension
- Write ETL scripts to load raw data into database
- Implement data validation and error handling
- Create SQL views for common queries

**Deliverables:**
- `src/load_data.py` - Python scripts for ETL
- `sql/create_tables.sql` - Database schema
- `sql/load_data.sql` - Data loading queries
- Database connection configuration

## Progress Checkpoints

### Interim Report Goals
At this stage, we should demonstrate:
1. ✓ Successfully acquired all three datasets
2. ✓ Completed initial exploratory data analysis
3. ✓ Identified data quality issues and cleaning requirements
4. ✓ Designed database schema
5. In Progress: Loading data into database

### Next Steps (Post-Interim Report)
- Complete database population
- Implement geospatial joins (crime proximity, PLUTO matching)
- Feature engineering pipeline
- Model development and evaluation


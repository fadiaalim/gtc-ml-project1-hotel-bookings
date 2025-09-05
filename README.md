# GTC ML Project 1 - Hotel Bookings

## 📌 Project Overview
This project is part of the GTC Machine Learning course.  
The goal is to clean and preprocess the **hotel_bookings.csv** dataset to prepare it for building a machine learning model that predicts booking cancellations.

---

## 🛠️ Steps Performed

### Phase 1: Exploratory Data Analysis (EDA)
- Loaded the dataset and generated summary statistics.
- Identified missing values and visualized them.
- Detected outliers in key numerical columns (`adr`, `lead_time`).

### Phase 2: Data Cleaning
- Handled missing values:
  - `company`, `agent` → replaced with `0`.
  - `country` → imputed with mode.
  - `children` → imputed with median.
- Removed duplicate rows.
- Capped outliers in `adr` (values above 1000 set to 1000).
- Converted date columns to proper datetime format.

### Phase 3: Feature Engineering & Preprocessing
- Created new features:
  - `total_guests = adults + children + babies`
  - `total_nights = stays_in_weekend_nights + stays_in_week_nights`
  - `is_family = 1 if children + babies > 0 else 0`
- Encoded categorical variables:
  - One-hot encoding for low-cardinality columns.
  - Frequency encoding for high-cardinality columns (e.g., `country`).
- Removed data leakage columns (`reservation_status`, `reservation_status_date`).
- Split the dataset into training and testing sets (80/20 split).

---

## 📂 Repository Contents
- `hotel_bookings.csv` → Original dataset.  
- `hotel_bookings_project.ipynb` → Jupyter Notebook with full cleaning process.  
- `README.md` → Project documentation (this file).  

---

## 🚀 How to Run
1. Clone this repository:
   ```bash
   git clone https://github.com/USERNAME/gtc-ml-project1-hotel-bookings.git

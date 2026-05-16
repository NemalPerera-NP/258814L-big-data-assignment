# Yelp Big Data Analytics and Recommendation system

This project is a PySpark-based mini project built on the Yelp dataset.

It does two connected tasks in one notebook:

- **Part A:** big data analytics on Yelp businesses using business, review, check-in, and tip data
- **Part B:** a business recommendation system built from the processed Part A outputs

The main notebook is:

- [03_yelp_integrated_analytics_recommendation_pipeline.ipynb](/D:/personal/projects/bigdata/big-data-analytics/notebooks/03_yelp_integrated_analytics_recommendation_pipeline.ipynb)

## Project Structure

```text
hvac-big-data-analytics/
├── data/
│   ├── yelp_academic_dataset_business.json
│   ├── yelp_academic_dataset_review.json
│   ├── yelp_academic_dataset_checkin.json
│   ├── yelp_academic_dataset_tip.json
│   └── Dataset_User_Agreement.pdf
├── notebooks/
│   └── 03_yelp_integrated_analytics_recommendation_pipeline.ipynb
├── outputs/
│   ├── figures/
│   └── tables/
├── slides/
├── requirements.txt
└── README.md
```

## What You Need Before Running

You need these installed on your machine:

- **Python**  
  Tested in this project with Python `3.14.x`

- **Java**  
  Required by Spark. A recent JDK such as Java `17+` is recommended.

- **Git**  
  Optional, only needed if you are cloning the repository

## Dataset Requirement

The Yelp dataset is **not included** in the repo/zip for distribution.

You must download the Yelp Academic Dataset yourself and place these files directly inside the project's [data](big-data-analytics/data) folder:

- `yelp_academic_dataset_business.json`
- `yelp_academic_dataset_review.json`
- `yelp_academic_dataset_checkin.json`
- `yelp_academic_dataset_tip.json`

Optional:

- `yelp_academic_dataset_user.json`

This project currently uses:

- business
- review
- checkin
- tip

### Where to Get the Dataset

Download it from the official Yelp Open Dataset page:

- [Yelp Open Dataset](https://business.yelp.com/data/resources/open-dataset/)

After downloading, extract the files and copy the required JSON files into the `data/` folder.

## Setup Instructions

### 1. Get the Project Files

You can either:

- clone the Git repo
- or extract the project zip into a folder

Example using Git:

```powershell
git clone <your-repo-url>
cd big-data-analytics
```

If you received a zip file, just extract it and open the project root folder.

### 2. Create a Virtual Environment

From the project root:

```powershell
python -m venv .venv
```

### 3. Activate the Virtual Environment

On Windows PowerShell:

```powershell
.\.venv\Scripts\Activate
```

On Windows Command Prompt:

```cmd
.venv\Scripts\activate.bat
```

### 4. Install the Dependencies

```powershell
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 5. Place the Yelp Dataset Files in `data/`

Your [data](big-data-analytics/data) folder should contain at least:

```text
data/
├── yelp_academic_dataset_business.json
├── yelp_academic_dataset_review.json
├── yelp_academic_dataset_checkin.json
└── yelp_academic_dataset_tip.json
```

## How to Run the Project

### Option 1: Run in Jupyter Notebook

From the project root, with the virtual environment activated:

```powershell
jupyter notebook
```

or

```powershell
jupyter lab
```

Then open:

- `notebooks/03_yelp_integrated_analytics_recommendation_pipeline.ipynb`

### Option 2: Run Through VS Code

If you use VS Code:

1. Open the project folder
2. Select the `.venv` Python interpreter
3. Open the notebook
4. Run the cells from top to bottom

## Recommended Execution Order

Run the notebook from the beginning in order.

Main flow:

1. Spark setup and dataset loading
2. Data cleaning and structuring
3. Data quality checks
4. Feature engineering
5. Enriched business layer creation
6. Part A analytics and visualizations
7. Part B recommendation system
8. Evaluation and final sections

## Output Produced by the Notebook

The notebook generates:

- cleaned and enriched Spark DataFrames
- figures in [outputs/figures](big-data-analytics/outputs/figures)
- processed business-level CSV outputs in `data/processed` or equivalent export cells when run
- recommendation examples and evaluation tables inside the notebook

Examples of output:

- business quality analysis
- engagement analysis
- activity analysis
- popularity-based recommendations
- content-based recommendations
- recommendation evaluation

## Manual Recommendation Testing

At the end of the notebook, there is an optional testing block that lets you:

- enter a business name
- optionally enter city and state
- test the content-based recommendation output
- test the popularity baseline

This is useful for:

- checking the recommender manually
- creating demo video examples

## Common Issues

### 1. Dataset file not found

If you see a file-not-found error, make sure the required Yelp JSON files are directly inside `data/`.

They should **not** be inside older nested folders like:

- `data/raw/...`
- `Yelp-JSON/...`

### 2. Java / Spark error

If Spark fails to start, check:

- Java is installed
- `java -version` works in your terminal

### 3. Slow notebook execution

The review dataset is large, so some cells can take time.

This is normal, especially during:

- dataset loading
- aggregations
- feature engineering
- recommendation evaluation

### 4. CSV export or path issues

Make sure you run the notebook from the project root environment with the correct folder structure.

## Recreating the Environment From Scratch

If the `.venv` folder has been deleted, the basic recovery steps are:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
jupyter notebook
```

Then:

1. add the Yelp dataset files into `data/`
2. open the notebook
3. run all cells from top to bottom

## Notes

- The notebook is designed to be run sequentially
- The project depends on the Yelp JSON files being present locally
- The recommendation part depends on the processed outputs created earlier in the notebook


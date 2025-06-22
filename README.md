# 🏥 Barbados Health Registry Cleaning & EDA

This repository contains a Google Colab notebook for cleaning and exploring the **Barbados Health Facility Registry**. It includes:
- Exploratory Data Analysis (EDA)
- A reproducible cleaning pipeline
- Final cleaned dataset exported as a tidy CSV file

---

## 📁 Files

- `health_registry_eda_clean_complete.ipynb` – Main notebook for cleaning and EDA
- `health_registry.csv` – Raw data file (stored in Google Drive)
- `cleaned_health_registry.csv` – Cleaned dataset (output saved to Google Drive)

---

## ▶️ How to Run the Notebook (Google Colab)

### 1. Open the notebook

Click here to open the notebook in Colab:  
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/BrianSandiford/Technical-Assignment---Barbados/blob/main/health_registry_eda_clean.ipynb)


Or upload it manually to https://colab.research.google.com

---

### 2. Mount Google Drive

> ⚠️ **Note:** You must be logged into your **Google account** to use this feature.

To access the raw `health_registry.csv` file from your Google Drive and save the output:


1. Open your notebook in **Google Colab**

2. In the **left sidebar**, click the **folder icon** 📁 to open the **Files pane**

3. Click the **"Mount Drive"** button at the top (you’ll see a small Google Drive icon)

4. A prompt will appear asking you to **authorize access to your Google Drive**

5. Sign in and allow the required permissions

6. Once mounted, you will see a new folder in the file pane:

```bash
/content/drive/

```
### 3. Load Your Dataset

Replace the path with your own file location on Google Drive:

```python
import pandas as pd

file_path = '/content/drive/MyDrive/your-folder/health_registry.csv'
df = pd.read_csv(file_path)
```
### 4. Run All Cells

Go to Runtime > Run all or press `Ctrl + F9` to run the entire notebook from top to bottom.

### 5. Save Output to Google Drive

```python
output_path = '/content/drive/MyDrive/your-folder/cleaned_health_registry.csv'
df_clean.to_csv(output_path, index=False)
```

You can then download or share the output CSV directly from your Google Drive.


## 📌 Key Assumptions & Cleaning Decisions

- Duplicates are dropped using `df.drop_duplicates()`
- `capacity` is cleaned into a numeric column.Extracted numeric values only.
- `region` is standardized using `.str.title()` and cleaned to remove variations of `"Parish"`
- Reversed or corrupted region names (like `"WERDNA .TS"`) are detected and fixed
- GPS coordinates are extracted from multiple formats, including:
  - `POINT(long lat)`
  - `lat, long`
  - DMS format like `13°9′5″N 58°58′44″W`
- All dates (`licence_issue_date`, `inspection_date`) are parsed and standardized to datetime format

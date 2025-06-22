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

To access the raw `health_registry.csv` file from your Google Drive and save the output:

```python
from google.colab import drive
drive.mount('/content/drive')
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

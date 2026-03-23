# Data

> ⚠️ **Raw data is not stored in this repository** to respect data licensing and keep the repo lightweight.

## Dataset: UCI Student Performance Dataset

**Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/320/student+performance)

**Citation:**
> Cortez, P., & Silva, A. (2008). Using data mining to predict secondary school student performance. In Proceedings of 5th Annual Future Business Technology Conference (pp. 5-12).

## Download Instructions

1. Go to: https://archive.ics.uci.edu/dataset/320/student+performance
2. Download the ZIP archive
3. Place the extracted files in this `data/` folder:
   ```
   data/
   ├── student-mat.csv    ← Mathematics subject data (used in this project)
   └── student-por.csv    ← Portuguese subject data
   ```

## Updating Notebook Paths

The notebooks were originally built in Google Colab and load data from `/content/archive.zip`.

**To run locally**, update the data loading cell in each notebook:

```python
# Original (Colab):
with zipfile.ZipFile('/content/archive.zip', 'r') as z:
    z.extractall('/content/')
df = pd.read_csv('/content/student-mat.csv', sep=';')

# Local replacement:
df = pd.read_csv('../data/student-mat.csv', sep=';')
```

## Data Dictionary

| Feature | Type | Description |
|---|---|---|
| `school` | binary | Student school (GP / MS) |
| `sex` | binary | Student sex (M / F) |
| `age` | numeric | Student age (15–22) |
| `address_type` | binary | Urban or rural |
| `family_size` | binary | ≤3 or >3 |
| `parent_status` | binary | Parents living together or apart |
| `mother_education` | ordinal | Mother's education level (0–4) |
| `father_education` | ordinal | Father's education level (0–4) |
| `mother_job` | nominal | Mother's occupation |
| `father_job` | nominal | Father's occupation |
| `school_choice_reason` | nominal | Reason for choosing school |
| `guardian` | nominal | Student's guardian |
| `travel_time` | ordinal | Home to school travel time |
| `study_time` | ordinal | Weekly study time |
| `failures` | numeric | Number of past class failures |
| `extra_support` | binary | Extra educational support |
| `family_support` | binary | Family educational support |
| `extra_paid_class` | binary | Extra paid classes |
| `activities` | binary | Extracurricular activities |
| `nursery` | binary | Attended nursery school |
| `higher_edu` | binary | Wants to pursue higher education |
| `internet` | binary | Internet access at home |
| `romantic` | binary | In a romantic relationship |
| `family_relationship` | ordinal | Quality of family relationships (1–5) |
| `free_time` | ordinal | Free time after school (1–5) |
| `going_out` | ordinal | Going out with friends (1–5) |
| `weekday_alcohol` | ordinal | Workday alcohol consumption (1–5) |
| `weekend_alcohol` | ordinal | Weekend alcohol consumption (1–5) |
| `health` | ordinal | Current health status (1–5) |
| `absences` | numeric | Number of school absences |
| `grade_1` | numeric | First period grade (0–20) |
| `grade_2` | numeric | Second period grade (0–20) |
| `final_grade` | numeric | Final grade — **target variable** (0–20) |

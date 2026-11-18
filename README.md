# Python DS Assignment 2: Data Visualization (NYC Taxi Trips)

Data cleaning and visualization of the Seaborn `taxis` dataset using Pandas, Matplotlib and Seaborn.

## Overview

Taxi services generate large amounts of trip data every day. This project cleans the raw data, handles missing values, and visualizes patterns in fares, distances, tips and customer behavior.

## Dataset

Loaded directly from Seaborn:

```python
import seaborn as sns
df = sns.load_dataset("taxis")
```

Key columns: `pickup`, `dropoff`, `passengers`, `distance`, `fare`, `tip`, `tolls`, `total`, `color`, `payment`, `pickup_zone`, `dropoff_zone`, `pickup_borough`, `dropoff_borough`.

## Data Cleaning

| Column(s) | Strategy |
|---|---|
| `payment` | Imputed with mode |
| `dropoff_zone`, `dropoff_borough` | Imputed with mode |
| `pickup_zone`, `pickup_borough` | Rows dropped (critical grouping columns, so imputing would distort results) |

Numeric columns had no missing values, so no mean/median imputation was needed.

## Visualizations

**Matplotlib / Pandas plot**
- Line chart: fare over pickup time
- Bar chart: total fare by `pickup_borough`
- Pie chart: trip distribution by payment method
- Histogram: distribution of trip distance
- Box plot: tip amount by `pickup_borough`

**Seaborn**
- Count plot: number of trips per `pickup_borough`
- Scatter plot: distance vs fare, colored by `pickup_borough`
- Heatmap: correlation of distance, fare, tip, tolls and total
- Pair plot: distance, fare, tip and total, colored by `pickup_zone`
- Violin plot: fare distribution by payment method

## Project Structure

```
.
├── taxi_assignment.ipynb   # Main notebook (cleaning + all plots)
├── requirements.txt        # Python dependencies
└── README.md
```

## Setup and Run

1. Clone the repository:
   ```bash
   git clone https://github.com/dhilipsadha-cmyk/taxi-data-visualization.git
   cd taxi-data-visualization
   ```
2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   venv\Scripts\activate        # Windows
   source venv/bin/activate     # macOS/Linux
   ```
3. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn ipykernel
   ```
4. Open `taxi_assignment.ipynb` in VS Code or Jupyter, select the `venv` kernel, and click **Run All**.

An internet connection is needed the first time, since `sns.load_dataset("taxis")` downloads the data from GitHub.

## Tools

Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter (VS Code)

## Author

Dhilip Kumar

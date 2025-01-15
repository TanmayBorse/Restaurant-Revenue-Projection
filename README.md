# 🍽️ Restaurant Revenue Prediction

Welcome to the **Restaurant Revenue Prediction** project! This project aims to predict restaurant revenue based on multiple factors such as location, type, and other demographic, real estate, and commercial data. The insights from this prediction can assist businesses in making more informed decisions about site selection for new restaurant locations.

## 📂 Dataset Overview

We are working with two datasets:
- **Training Dataset (train.csv)**: Contains data for 137 restaurants.
- **Test Dataset**: Includes 100,000 restaurant entries for prediction (without revenue information).

### Data Fields

| Column         | Description                                                             |
|----------------|-------------------------------------------------------------------------|
| `Id`           | Unique identifier for each restaurant.                                  |
| `Open Date`    | The date the restaurant opened.                                          |
| `City`         | The city where the restaurant is located (names may contain Unicode).    |
| `City Group`   | City classification: `Big Cities` or `Other`.                           |
| `Type`         | Type of the restaurant: `FC` (Food Court), `DT` (Drive Thru), `MB` (Mobile). |
| `Revenue`      | The (transformed) revenue of the restaurant in a given year (target variable). |
| Obfuscated Columns: |
| `Demographic Data` | Obfuscated demographic information about the location. |
| `Real Estate Data` | Obfuscated real estate-related data for the restaurant site. |
| `Commercial Data`  | Obfuscated commercial activity data related to the restaurant. |

## ⚙️ Requirements

To get started with this project, you will need the following:

- **Python 3.9+**
- **Jupyter Notebook** (Anaconda 3 recommended)

### Install Required Libraries:

- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

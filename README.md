<h1 align="center"> 🌟 Hospitality Fraud Detection 🌟 </h1>
<p align="center">using <b>SAS Enterprise Miner 🖥⛏</b><br><br>

## 🖋 About Project:
Airbnb, a platform for short-term lodging, faces challenges such as regulatory scrutiny and criticism for its impact on housing prices and community life. The key issue is distinguishing between hosts offering legal short-term rentals and those running illegal, hotel-like operations. To address this, a comprehensive analysis using cluster and classification techniques on Edinburgh's listing data will be conducted. The goal is to identify patterns that differentiate genuine short-term rentals from businesses, contributing valuable insights to community decision-making and addressing urgent housing concerns. This project was carried out in SAS Enterprise Miner.

**Skills and tools used**
- Exploratory Data Analysis (Variable Identification, Univariate Analysis, Bi-variate analysis)
- Correlation Analysis
- Variable Reduction (Principal component analysis)
- Cluster Analysis
- ML modelling (decision tree)
- Model Performance evaluation 
<br><br>

## 📃 Table of Contents:
  - [Context](#-context)
  - [Objectives](#-objectives)
  - [Data Description](#-data-description)
  - [Process Flow](#-process-flow)
  - [Initial Data Exploration](#-initial-data-exploration)
  - [Data Pre-processing](#-data-pre-processing)
  - [EDA](#-eda)
  - [Dimensionality Reduction](#-dimensionality-reduction)
      - [Pearson Correlation Analysis](#-pearson-correlation-analysis)
      - [Principal Component Analysis](#-principal-component-analysis)
      - [Cluster Analysis](#-cluster-analysis)
  - [Model Implementation](#-model-implementation)
      - [Data Preparation](#-data-preparation)
      - [Decision Tree](#-decision-tree)
  - [Analysis](#-analysis)
  - [References](#-references)

## 🖋 Context:
Airbnb facilitates short-term lodging and tourism-related activities, allowing guests to search for accommodations using filters such as location, price, and property type. Users provide personal and payment information before booking, and some hosts may request government-issued identification. Hosts provide details about their listings, including the number of guests, property type, amenities, and minimum nights for a reservation.
The platform incorporates a review system where hosts and guests can share their experiences and rate each other. However, concerns about future stays may impact the truthfulness and impartiality of reviews. Airbnb's policy requires users to forego anonymity, potentially affecting users' willingness to leave negative reviews.
Criticism of Airbnb includes its impact on housing prices, nuisances, and security issues in cities where it operates, leading to regulatory scrutiny in various regions, including San Francisco, New York City, and the European Union. The sharing economy, of which Airbnb is a part, presents both opportunities and challenges for homeowners, communities, and governments.
One significant issue revolves around whether hosts are operating permanent hotel-like rentals (illegal short-term rentals) or occasionally sharing their primary residence (legal short-term rentals). The responsibility to address housing shortages, nuisances, and safety concerns falls on communities, necessitating a detailed analysis of listing data from Edinburgh to differentiate between legal and illegal short-term rentals.
To achieve this, a cluster analysis (unsupervised learning) will be conducted using detailed listing data (listings.csv). This analysis aims to identify meaningful patterns and rules based on host information, property characteristics, and overall guest ratings. Additionally, a classification model will be developed to differentiate between genuine short-term rentals and those operating as businesses. A comprehensive literature search will complement data exploration and preparation for the clustering and classification tasks.

[![](https://img.shields.io/badge/back%20to%20top-%E2%86%A9-blue)](#-table-of-contents)
<br><br>

## 📌 Objectives:
The goal of this analysis is to identify patterns proving/disproving a host’s involvement in illegal rental activities. 
The domain knowledge gained on the sharing economy (the business domain to which Airbnb belongs) will be used throughout the report in making decisions on variable classification, cluster interpretation and model evaluation. A key takeaway from the project will be to understand how the model outcome can be integrated with Edinburgh regulations for possible implementation. Guest characteristics, Airbnb’s limitations and host activity will be used to gain insight on activity. Ultimately, this project will contribute to the efforts of  platforms like Inside Airbnb in improving the sharing economy in Edinburgh. 
Some questions of interest which will be answered after modelling are: 
 - Are listings with high occupancy rate likely to be illegal?
 - Are certain property types more or less likely to be illegal?
 - Are verified hosts more or less likely to engage in illegal activity?
<br><br>

## 🧾 Data Description:
Airbnb does not release data on its listings however, InsideAirbnb scrapes publicly available data about listings from their website. The Edinburgh data (16 December 2022) used in this project is available to download from [InsideAirbnb](http://insideairbnb.com/get-the-data). The *listings* data has majorly been used for modelling while the *calendar* and *reviews* data was used to gain understanding of the measurement parameters.

![Data set description](https://github.com/Providence-o/Hospitality-fraud-detection-with-decision-tree-using-clustering-analysis-PCA-SAS-Enterprise-Miner/blob/8a127ac61b96987e6872df471176f94bc2e6ce91/Graphs%20%26%20Images/Data%20description.png)

[![](https://img.shields.io/badge/back%20to%20top-%E2%86%A9-blue)](#-table-of-contents)
<br><br>

## ⚙ Process Flow
![Process Flow](https://github.com/Providence-o/Hospitality-fraud-detection-with-decision-tree-using-clustering-analysis-PCA-SAS-Enterprise-Miner/blob/8a127ac61b96987e6872df471176f94bc2e6ce91/Graphs%20%26%20Images/Process%20flow.png)
<br><br>

## 📊 Initial Data Exploration
![Pre-cleaning interval summary stats](https://github.com/Providence-o/Hospitality-fraud-detection-with-decision-tree-using-clustering-analysis-PCA-SAS-Enterprise-Miner/blob/8a127ac61b96987e6872df471176f94bc2e6ce91/Graphs%20%26%20Images/Pre-cleaning%20Interval%20Summary%20Statistics.png)

![Pre-cleaning class summary stats](https://github.com/Providence-o/Hospitality-fraud-detection-with-decision-tree-using-clustering-analysis-PCA-SAS-Enterprise-Miner/blob/8a127ac61b96987e6872df471176f94bc2e6ce91/Graphs%20%26%20Images/Pre-cleaning%20Class%20Summary%20Statistics.png)
   - Missing values are detected in several character and numerical columns
   - Several numerical variables had skewed distributions.  

[![](https://img.shields.io/badge/back%20to%20top-%E2%86%A9-blue)](#-table-of-contents)
<br><br>

## 🛠 Data Pre-processing
### 1️⃣ Cleaning the raw data set- dropping variables & observations
Data cleaning was done following defined criteria in Microsoft Excel using filters. There were 7,387 observations with 25 columns post cleaning.

**Cleaning criteria:**

![Cleaning](https://github.com/Providence-o/Hospitality-fraud-detection-with-decision-tree-using-clustering-analysis-PCA-SAS-Enterprise-Miner/blob/8e67416bb309b5497b950b3286791a5c06f21354/Graphs%20%26%20Images/Cleaning%20criteria.png)
   - Numerical variables *accommodates* and *price* have a minimum of 0. It is highly unlikely           that a listing on Airbnb would be free and accommodate no-one, so this was regarded             as poor data. Therefore, the two corresponding listings were dropped.
   - *reviews_per_month* and *review_score_rating*  had a large number of missing variables,             this was permissible because not every guest leaves reviews. 

**Resulting Summary statistics of Interval and Class Variables for analysis:**

![post cleaning](https://github.com/Providence-o/Hospitality-fraud-detection-with-decision-tree-using-clustering-analysis-PCA-SAS-Enterprise-Miner/blob/8e67416bb309b5497b950b3286791a5c06f21354/Graphs%20%26%20Images/Post-cleaning%20Summary%20statistics%20.png)

### 2️⃣ Filtering Outliers
The filter node was applied to have an understanding of the outliers that exist. No class variables were excluded at the original 1% cutoff. However, the interval variables were heavily filtered based on their deviation from the mean. 

![filter node](https://github.com/Providence-o/Hospitality-fraud-detection-with-decision-tree-using-clustering-analysis-PCA-SAS-Enterprise-Miner/blob/8e67416bb309b5497b950b3286791a5c06f21354/Graphs%20%26%20Images/Filtering%20Node.png)
   - This is undesirable for this business case as the model needs to be trained to have the ability to accurately identify illegal listings based on specified criteria as it sometimes may be presented with listings that have extreme values.
   - For instance: post-filtering only ≤ 4-bedroom listings were left. This excludes several property types (condo, bungalow, rental unit, entire home)  from the analysis.
   - The results from this node were therefore disregarded. 

### 3️⃣ Variable Transformation
   - All class variables (except binary) transformed using Group Rare Levels @ 4% cutoff. 
   - Max.Normal applied to *review_scores_rating* and *longitude* 
   - Log10 transformation on all other numerical variables
   - No transformation on *availability_365* and *latitude*

![transformation](https://github.com/Providence-o/Hospitality-fraud-detection-with-decision-tree-using-clustering-analysis-PCA-SAS-Enterprise-Miner/blob/8e67416bb309b5497b950b3286791a5c06f21354/Graphs%20%26%20Images/Variable%20Transformation.png)

### 4️⃣ Creation of New Variables 
To improve illegal activity predictions, _occupancy_rate_ and _listing_income_ have been introduced as new derived variables.

_occupancy_rate_ - days booked divided by the days available to be booked (Airbnb, 2023)

```
(reviews_per_month * minimum_nights * 12)/availability_365
```

_listing_income_ - occupancy rate multiplied by the nightly price (An, 2023)

```
price * occupancy_rate * 365
```

These variables were log transformed for normalization as their formulas were derived from initial variables that produced skewed results

![new variables](https://github.com/Providence-o/Hospitality-fraud-detection-with-decision-tree-using-clustering-analysis-PCA-SAS-Enterprise-Miner/blob/8e67416bb309b5497b950b3286791a5c06f21354/Graphs%20%26%20Images/New%20variables%20summary%20statistics.png)

[![](https://img.shields.io/badge/back%20to%20top-%E2%86%A9-blue)](#-table-of-contents)
<br><br>

## 📈 EDA

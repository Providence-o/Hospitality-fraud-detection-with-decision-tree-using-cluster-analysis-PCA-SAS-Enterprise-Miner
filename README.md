<h1 align="center"> 🌟 Hospitality Fraud Detection 🌟 </h1>
<p align="center">using <b>SAS Enterprise Miner 🖥⛏</b><br><br>

## 🖋 About Project:
Airbnb, a platform for short-term lodging, faces challenges such as regulatory scrutiny and criticism for its impact on housing prices and community life. The key issue is distinguishing between hosts offering legal short-term rentals and those running illegal, hotel-like operations. To address this, a comprehensive analysis using cluster and classification techniques on Edinburgh's listing data will be conducted. The goal is to identify patterns that differentiate genuine short-term rentals from businesses, contributing valuable insights to community decision-making and addressing urgent housing concerns. This project was carried out in SAS Enterprise Miner. 
*   Skills and tools used 
      - Exploratory Data Analysis (Variable Identification, Univariate Analysis, Bi-variate 
        analysis)
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
   
[![](https://img.shields.io/badge/back%20to%20top-%E2%86%A9-blue)](#-table-of-contents)
<br><br>





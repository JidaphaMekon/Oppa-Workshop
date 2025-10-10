# Oppa-Workshop

Oppa Workshop Preparation

This process involves preparing for the upcoming workshop as part of the International Conference at Oppa Workshop, based on the reviewers' recommendations. The preparation includes revising the accepted paper, 
addressing all reviewer comments, and organizing presentation materials to align with the conference standards.

1. Data Preparation

Data was retrieved from Yahoo Finance via API. The dataset consists of NASDAQ-listed companies in the Mega Cap category within the Technology sector. 
The time period spans from 2019 to 2024, which was selected to sufficiently capture seasonal trends and market fluctuations relevant to time series forecasting tasks.

🏢 Companies Overview

This project uses historical stock data from the following mega-cap technology companies listed on the NASDAQ exchange. These companies were selected for their large market capitalization and significant influence on the tech sector and overall stock market behavior.

Ticker	Company Name	Description
AAPL	Apple Inc.	A global technology leader known for its consumer electronics (iPhone, Mac), software, and digital services such as iCloud and Apple Music.
AMD	Advanced Micro Devices, Inc.	Designs and manufactures CPUs and GPUs, competing directly with Intel and NVIDIA in the computing and gaming markets.
AVGO	Broadcom Inc.	Develops semiconductor and infrastructure software solutions, widely used in networking, broadband, and data centers.
GOOG	Alphabet Inc. (Class C)	Non-voting stock of Google's parent company. Alphabet owns Google, YouTube, Android, Google Cloud, and other tech initiatives.
GOOGL	Alphabet Inc. (Class A)	Voting stock of Alphabet Inc., with the same economic interest as GOOG but includes shareholder voting rights.
META	Meta Platforms, Inc.	Formerly Facebook, the company owns Facebook, Instagram, WhatsApp, and is a major player in the Metaverse and social media space.
MSFT	Microsoft Corporation	One of the largest tech companies globally, known for Windows OS, Microsoft Office, Azure Cloud, and Xbox gaming platform.
NVDA	NVIDIA Corporation	Leader in GPU technology, powering gaming, AI research, data centers, and autonomous systems.

2. 🛠️ Data Processing

To evaluate the impact of time-series completeness and imputation methods, two types of datasets were prepared:

1. Raw Data (No Holiday Adjustment)

This dataset was retrieved directly from the Yahoo Finance API. It includes only trading days and excludes non-trading days such as weekends and market holidays. This represents the standard format commonly used in financial modeling.

2. Calendar-Aligned Data with US Holidays

In this version, a complete time calendar was constructed using the New York Stock Exchange (NYSE) calendar, which includes both trading and non-trading days. As a result, this dataset contains missing values on holidays.

To fill these missing values, three interpolation methods were applied:

Linear Interpolation

Nearest Interpolation

Forward Fill Interpolation

At this stage, no specific logic or additional factors have been used in selecting the fill values. The primary goal is to observe and compare how different interpolation methods affect model performance. It is acknowledged that interpolation may introduce bias into the dataset.

3. Comparison Between Filled and Unfilled Datasets

The results from the interpolated datasets will be compared to the original dataset without interpolation, to assess whether the imputation introduces significant differences in model outcomes.

4. Bias Evaluation

An evaluation will be conducted to assess whether the imputation introduces systematic bias that may affect model performance. This step will help determine whether interpolating missing values is beneficial or whether it distorts the model’s ability to learn actual patterns in the market.

✅ Note: This step is still under consideration, and further analysis will determine if bias evaluation should be included in the final study.


Data Study Overview

This section is designed for beginners who want to understand the basics of stock price data processing. The author presents the data steps in a clear, numbered sequence to help readers follow along easily.

Data Preparation Lists

Import datasets
Retrieve stock price data from Yahoo Finance.

Trading day only dataset
This dataset includes only official trading days (excluding weekends and holidays).

Trading day + holiday dataset with interpolation techniques
This dataset covers all calendar days including trading days and holidays. Missing values on holidays are filled using:

Linear Interpolation

Nearest Neighbor Interpolation

Forward Fill Interpolation

Code Provided

All code is available and runnable in Google Colab notebooks (.ipynb) and Python scripts (.py).

Numbered Data Processing Steps

1. Trading day only dataset

2. Trading day + holiday + Linear Interpolation

3. Trading day + holiday + Nearest Neighbor Interpolation

4. Trading day + holiday + Forward Fill Interpolation


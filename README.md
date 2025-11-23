📦 AI-Powered Customer Review Analysis System
Automated Sentiment Detection, Key Phrase Extraction & Summarization using AWS Lambda, Comprehend, SageMaker & QuickSight
🚀 Overview

This project implements an AI-driven customer review analytics pipeline built entirely using AWS cloud services. It automatically performs:

Sentiment Analysis

Key Phrase Extraction

Text Summarization

ETL & Data Processing

Interactive Dashboard Visualization

The final output is an Amazon QuickSight dashboard displaying:
✔ Sentiment distribution
✔ Category insights
✔ Keyword patterns
✔ AI-generated summaries

<p align="center"><br><em>Figure 1: QuickSight Dashboard – Customer Review Insights</em></p>
🧭 Table of Contents

Overview

Architecture

Architecture Description

Features Implemented

Dataset Used

AWS Services Used

How It Works

Dashboard Sheets

Sample Output

Tech Stack

🏗 Architecture
<p align="center"><br><em>Figure 2: End-to-End Customer Review Processing Pipeline</em></p>
Amazon S3 (Input CSV)
        ↓
AWS Lambda (ETL + Comprehend)
        ↓
Amazon Comprehend (Sentiment + Key Phrases)
        ↓
Amazon DynamoDB (Processed Data Storage)
        ↓
Amazon SageMaker (Summarization Model)
        ↓
AWS Lambda (Summary Generator)
        ↓
Amazon QuickSight (Dashboard)

🔹 Architecture Description
1. Data Source (Amazon S3)

Customer review CSV uploaded to S3

Upload triggers a Lambda function

2. ETL & AI Processing (AWS Lambda + Comprehend)

Data cleaning & normalization

Sentiment classification (Positive / Negative / Neutral / Mixed)

Key phrase extraction

3. Processed Storage (Amazon DynamoDB)

Stores enriched review entries:

ReviewID

Rating

Text

Category

Sentiment

Sentiment Score

Key Phrases

4. Text Summarization (Amazon SageMaker)

Lambda aggregates review text

SageMaker JumpStart model produces summaries

5. Dashboard Visualization (Amazon QuickSight)

Imports data from DynamoDB / S3

Provides interactive dashboards & insights

🚀 Features Implemented
✔ Automatic Review Processing

Uploads CSV → Lambda cleans & processes reviews end-to-end.

✔ Sentiment Analysis (Comprehend)

Detects:

Positive

Negative

Neutral

Mixed

✔ Key Phrase Extraction

Identifies important customer keywords such as:
quality, size, material, return policy…

✔ AI-Powered Summarization (SageMaker)

Generates dataset-level summaries.

✔ DynamoDB Storage

Fully structured and query-optimized data store.

✔ QuickSight Dashboard

Includes:

Donut Chart (Sentiment Distribution)

Bar Chart (Rating Insights)

Heatmap (Category vs Sentiment)

Word Cloud (Key Phrases)

KPI Cards

Searchable Review Table

📁 Dataset Used

Women’s Clothing E-Commerce Reviews Dataset

Contains:

Review Text

Clothing ID

Age

Rating

Positive Feedback Count

Department / Division / Category

Total Records: ~23,000 reviews

🔧 AWS Services Used
Service	Purpose
Amazon S3	Input CSV storage
AWS Lambda	ETL, Comprehend integration, summarization
Amazon Comprehend	Sentiment analysis & key phrase extraction
Amazon DynamoDB	Structured review storage
Amazon SageMaker	Text summarization model
Amazon QuickSight	Dashboard visualization
🧪 How It Works
1️⃣ Upload Review File

User uploads the CSV

S3 triggers Lambda

2️⃣ Processing Pipeline

Lambda performs:

Data validation

Cleansing

Comprehend Sentiment API call

Key phrase extraction

DynamoDB insertion

3️⃣ Summarization Process

Second Lambda:

Extracts all review text

Sends to SageMaker for summarization

Saves outputs

4️⃣ Visualization

QuickSight loads enriched data for visual dashboards.

📊 Dashboard Sheets
Sheet 1 — Business Overview

Total Reviews

Avg Rating

Positive Sentiment %

Sentiment Pie Chart

Rating Distribution

Sheet 2 — Product Insights

Category vs Sentiment Heatmap

Avg Rating by Category

Key Phrase Word Cloud

Category Filter

Sheet 3 — Customer Review Details

Searchable Review Table

Sentiment Score by Review

Individual Review Key Phrases

AI Summary

🧾 Sample Output

84% reviews are Positive

Frequent keywords: quality, size, fit, material

Dresses & Tops show highest sentiment

AI summaries reflect customer emotions accurately

🧩 Tech Stack
Layer	Tools
Programming	Python (Lambda)
AI/ML	Comprehend, SageMaker
Storage	S3, DynamoDB
Visualization	QuickSight
Automation	S3 Event Triggers
Cloud Platform	AWS

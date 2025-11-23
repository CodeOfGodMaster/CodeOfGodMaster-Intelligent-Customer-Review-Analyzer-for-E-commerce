📦 AI-Powered Customer Review Analysis System
Automated Sentiment Detection, Key Phrase Extraction & Summarization using AWS Lambda, Comprehend, SageMaker & QuickSight
🚀 Overview

This project implements an AI-driven customer review analytics pipeline using AWS cloud services.
It automatically performs:

Sentiment Analysis

Key Phrase Extraction

Text Summarization

ETL & Data Processing

Interactive Dashboard Visualization

The final output is an Amazon QuickSight dashboard showing sentiment distribution, category insights, keyword patterns, and AI-generated summaries.

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

Upload triggers Lambda for ingestion

2. ETL & AI Processing (AWS Lambda + Comprehend)

Data cleaning & normalization

Sentiment classification

Key phrase extraction

3. Processed Storage (Amazon DynamoDB)

Stores enriched review entries including:

ReviewID

Rating

Text

Category

Sentiment

Score

Key Phrases

4. Text Summarization (Amazon SageMaker)

Lambda aggregates text

SageMaker JumpStart model generates dataset-level summaries

5. Dashboard Visualization (QuickSight)

Loads data from DynamoDB/S3

Provides KPIs, charts, heatmaps, interactive filters

🚀 Features Implemented
✔ Automatic Review Processing

Uploads CSV → triggers Lambda → cleans & processes reviews automatically.

✔ Sentiment Analysis (Amazon Comprehend)

Detects:

Positive

Negative

Neutral

Mixed

✔ Key Phrase Extraction

Identifies meaningful customer keywords.

✔ AI-Powered Summarization (SageMaker)

Generates both product-level and dataset-level summaries.

✔ DynamoDB Storage

Stores enriched, structured review data.

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

Includes:

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

CSV uploaded to S3

Triggers Lambda automatically

2️⃣ Processing Pipeline

Lambda performs:

Reads rows

Cleans invalid entries

Calls Comprehend

Stores results in DynamoDB

3️⃣ Summarization

Second Lambda:

Extracts review text

Sends to SageMaker

Saves summary

4️⃣ Visualization

QuickSight loads processed dataset and generates dashboards.

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

Word Cloud (Key Phrases)

Category Filter

Sheet 3 — Customer Review Details

Searchable Review Table

Sentiment Score by Review

Key Phrase Word Cloud

Individual Review Insights

🧾 Sample Output

84% reviews are positive

Frequent keywords: quality, size, fit, material

Dresses & Tops show highest satisfaction

AI summaries reflect customer emotions accurately

🧩 Tech Stack
Layer	Tools
Programming	Python (Lambda)
AI/ML	Amazon Comprehend, SageMaker
Storage	S3, DynamoDB
Visualization	QuickSight
Automation	S3 Event Triggers
Cloud Platform	AWS

# data_engineering_project
 
## YouTube Insights for Community Banking Ads

JPMorgan Chase is launching an advertising campaign for its Community Development Banking division, which focuses on supporting vibrant and diverse neighborhoods by offering loans, investments, and services to low- and moderate-income families and communities across the US, Canada, and the United Kingdom. The company plans to use YouTube as the primary platform for promoting their NGO project advertisements. To ensure the success of this strategy, a comprehensive analysis of YouTube data is necessary. This project will involve collecting, processing, and analyzing pertinent YouTube metrics to assess the feasibility and potential impact of the NGO advertisements on the platform. The objective is to determine if YouTube is the most effective medium for reaching the target audience and achieving the campaign's goals.

## Complete project walkthrough:
Link : https://medium.com/@motwanihimanshi01/youtube-insights-for-community-banking-ads-45a2bd0a222f

## Objective of the project:
<img width="1423" alt="Screenshot 2024-08-02 at 6 32 33 AM" src="https://github.com/user-attachments/assets/8c66332d-01bd-488f-8120-5a196cd09afa">

## Debrief AWS Sevices:
<img width="697" align="center" alt="image" src="https://github.com/user-attachments/assets/956b63a3-83bd-4678-abb2-50e263bbaf6d">

## Dataset Used

This Kaggle dataset contains statistics (CSV files) on daily popular YouTube videos over several months. There are up to 200 trending videos published every day to many locations all over the world. The data for each region is in its own file. The video title, channel title, publication time, tags, views, likes and dislikes, description, and comment count are among the items included in the data. A category_id field, which differs by area, is also included in the JSON file linked to the region

Link: https://www.kaggle.com/datasets/datasnaek/youtube-new

## Project Architecture Diagram:
<img width="1497" alt="project flow diagram" src="https://github.com/user-attachments/assets/808ef0f6-d08d-436f-bc55-97397bdd28ef">


## High level project Flow

Kaggle Dataset --> Landing Area --> Glue job and Lambda function --> enriched/cleansed --> ETL pipeline --> Analytics/Reporting --> Quicksight Dashboard.

### Detailed Project Flow

1. **Data Ingestion:**
   - Ingest all data from the Kaggle dataset into an S3 bucket (using CLI or direct upload).
2. **Glue Catalog Creation:**
   - Build tables by crawling all the data and create a Glue Catalog for ETL.
3. **Data Preprocessing:**
   - Use AWS Lambda to preprocess the data, converting JSON files into tables (scripts provided), and store the cleaned data in a separate S3 bucket.
4. **Second Crawling:**
   - Create another crawler for the cleansed data. Use AWS Athena (ad hoc query tool) to query the cleaned/enriched data.
5. **ETL Pipeline Construction:**
   - Build an ETL pipeline for the enriched/cleansed data to make it available for analytics. Use AWS Glue Studio, selecting the source as the cleaned data and raw data from the 
     Glue Catalog, and join them on category ID. Store the resulting data in a new S3 bucket, referred to as the analytics bucket.

 <img width="658" alt="image" src="https://github.com/user-attachments/assets/e5ad2994-1c73-4ced-95f7-d269431c9a3b">

## Create Visualizations to achieve the project goals:

**Analyze View Counts by Category:**
- Calculate the number of views for each category of NGO content on YouTube.

**Content Listings by Region:**
- Determine the number of NGO-related videos available in the CA, US, and GB regions.

**Identify Channels:**
- Identify the YouTube channels that prominently feature NGO-related content.

## Key skill development from this project:

1. **Problem-Solving**
2. **AWS Services Proficiency**
3. **Data Ingestion and Storage**
4. **ETL Processes**
5. **Serverless Computing**
6. **Data Cataloging and Metadata Management**
7. **Ad-hoc Querying**
8. **Data Integration**
9. **Automation and Workflow Management**
10. **SQL and Data Analysis**
11. **Data Cleaning and Transformation**
12. **Project Management**

# Jumia-Sentiment-Analysis-Modern-Data-Stack
 
# 🛍️ Brand Sentiment Analysis for Jumia Ghana Using Social Media Data  

## 1. Project Overview  

### **Project Title:**  
**Brand Sentiment Analysis for Jumia Ghana Using Social Media Data**

### **Objective:**  
To analyze how Ghanaians perceive **Jumia** on major social platforms, identify emerging topics around the brand, and provide actionable insights to improve brand reputation, customer satisfaction, and marketing strategies.

### **Key Goals:**  
- Collect brand mentions of “Jumia” from social media sources (Twitter/X,Facebook, YouTube).  
- Perform text cleaning and sentiment classification (positive, neutral, negative).  
- Identify common themes (e.g., delivery experience, pricing, customer service).  
- Visualize trends and insights for Jumia Ghana’s marketing team.

---

## 2. Data Stack & Architecture  

```text
[Social Media APIs / Scrapers]  
         ↓  
      Airbyte (Data Extraction)  
         ↓  
      dbt (Data Transformation)  
         ↓  
      Databricks (Data Lakehouse)  
         ↓  
      Power BI (Visualization)  
         ↓  
      Airflow (Pipeline Automation)
```

| **Source**       | **Access Method**                         | **Type of Data**                        | **Notes**                 |
| ---------------- | ----------------------------------------- | --------------------------------------- | ------------------------- |
| **Twitter/X**    | Twitter API v2 (Academic or Free-tier)    | Tweets mentioning “Jumia”               | Real-time brand sentiment |
| **YouTube**      | YouTube Data API                          | Comments on Jumia Ghana ads             | Product perception        |
| **Facebook**     | Facebook Graph API                        | Comments on Jumia’s page posts          | Complaint & praise data   |



## 3. Data Processing & Transformation

### Using dbt + Databricks:

Stage 1: Clean text (remove emojis, links, stopwords).

Stage 2: Apply sentiment model (e.g., TextBlob or Hugging Face transformer).

Stage 3: Tag mentions by category (delivery, product quality, pricing, etc.).

Stage 4: Aggregate data for Power BI dashboard (weekly & monthly summaries).

## 4. Power BI Dashboard

Main Pages:

1. Overall Sentiment Overview
Pie chart of positive/neutral/negative sentiment.

2. Trending Topics:
Word cloud or bar chart of most mentioned issues.

3. Sentiment Over Time:
Line chart showing improvement/decline in sentiment.

4. Category Insights:
Sentiment by topic — e.g., delivery vs. pricing vs. customer support.

5. Platform Comparison:
Which social platform has the most engagement or negativity.

## 5. Automation (Airflow)

Once the full workflow is tested manually, Airflow DAGs will:

1. Trigger Airbyte jobs (to pull latest data daily).

2. Run dbt transformations (clean and structure new data).

3. Load into Databricks (append to master dataset).

4. Refresh Power BI dataset (via API or gateway).

Send weekly summary report email.


## 7.Folder Structure (Professional Format)
jumia_brand_sentiment/

1. airbyte/     --------------    # Data Extraction
   
2. DBT/         --------------    # Models and Transformations
   
3. Airflow/     --------------    # DAGS for automation

4. Scripts/     --------------    # python files for extracting data

5. powerbi/     --------------    # Dashboard file (.pbix)
   
6. docs/        --------------    # Reports and documentation

└── README.md   --------------    # Overview & setup guide  


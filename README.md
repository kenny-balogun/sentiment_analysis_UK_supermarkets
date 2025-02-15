# Sentiment Analysis of Supermarket Reviews: Insight for Business Strategy  

## Overview  

In today's digital world, customer reviews are a powerful source of business intelligence.  
This project applies **sentiment analysis and text classification** to customer reviews of major UK supermarket chains,  
providing actionable insights to improve service quality and customer satisfaction.  

By leveraging **Multinomial Naïve Bayes (MNB) and Sentiment Intensity Analysis (VADER)**,  
this study identifies key sentiment drivers and helps businesses address customer concerns effectively.  

## Objectives  

- Perform **text classification** of supermarket reviews into sentiment categories.  
- Apply **VADER sentiment analysis** to assess sentiment polarity.  
- Identify key themes in **positive and negative** customer feedback.  
- Provide **data-driven recommendations** for improving customer experience.  

## Dataset  

The dataset consists of **5,000 customer reviews** scraped from **Trustpilot** using an open-source Google Colab notebook.  
It covers five of the UK's largest supermarket chains:  

- **Sainsbury’s**  
- **Tesco**  
- **Lidl**  
- **Aldi**  
- **Asda**  

### Ethical Considerations  

- **Data Anonymization:** Identifiable fields (e.g., usernames, locations) were removed to ensure privacy.  
- **Legal Compliance:** The dataset was anonymized in adherence to **GDPR regulations**.  

## Exploratory Data Analysis (EDA)  

Key insights from the data exploration phase:  

- **Rating Distribution:**  
  - Majority of reviews are **negative (1-star ratings)**, indicating widespread customer dissatisfaction.  
- **Company-wise Sentiment Trends:**  
  - **Sainsbury’s**: Strong **positive** sentiment for staff and product quality but complaints about stock issues.  
  - **Tesco**: Good **pricing (Clubcard)** but poor refund process.  
  - **Lidl**: Customers praise affordability but report **checkout inefficiencies**.  
  - **Aldi**: Positive reviews on **product quality**, but issues with **self-checkout and staff attitude**.  
  - **Asda**: Rewards program is well-received, but refunds and order fulfillment generate **negative sentiment**.  

## Data Preprocessing  

To ensure clean and structured data, the following preprocessing steps were applied:  

- **Duplicate Removal**: Identified and removed redundant entries.  
- **Text Cleaning**:  
  - Tokenization (splitting text into words).  
  - Lowercasing for uniformity.  
  - Stop-word removal (e.g., "the", "is", "and").  
  - Stemming (e.g., "shopping" → "shop") using **Porter Stemmer**.  
- **Feature Engineering**:  
  - **Binning Ratings** into broader sentiment categories (`Bad`, `Good`, `Excellent`) for classification.  
- **Vectorization**: Converted text reviews into numerical format using **CountVectorizer**, resulting in **12,288 unique tokens**.  

## Model Development  

### **1. Text Classification - Multinomial Naïve Bayes (MNB)**  

- **Goal:** Classify customer reviews into sentiment categories (`Bad`, `Good`, `Excellent`).  
- **Handling Imbalanced Data:**  
  - The dataset was highly imbalanced, with **"Bad" reviews significantly more frequent**.  
  - **SMOTE (Synthetic Minority Oversampling Technique)** was applied to balance the dataset.  
- **Performance:**  
  - **Imbalanced Model Accuracy:** **82%**, but struggled with minority classes.  
  - **SMOTE-Balanced Model Accuracy:** Improved F1-score to **82%**, showing better generalization.  

### **2. Sentiment Intensity Analysis - VADER**  

- **Goal:** Evaluate the polarity and intensity of each review.  
- **Compound Score Interpretation:**  
  - **Positive Sentiment:** Score > 0  
  - **Negative Sentiment:** Score ≤ 0  
- **Findings:**  
  - **55% of reviews were negative**, indicating general dissatisfaction with supermarket services.  
  - Sainsbury’s had the **most positive reviews**, while Asda had the **most negative reviews**.  

## Key Findings  

- **Common Positive Sentiments:**  
  - **Quality Products:** Customers appreciate well-stocked shelves and product variety.  
  - **Helpful Staff:** Friendly and knowledgeable employees enhance customer experience.  
  - **Loyalty Programs:** Clubcard (Tesco) and Asda Rewards boost customer engagement.  

- **Common Negative Sentiments:**  
  - **Customer Service Issues:** Poor refund handling, unhelpful staff.  
  - **Checkout Experience:** Slow self-checkout and technical problems.  
  - **Delivery & Stock Issues:** Frequent complaints about unavailable products.  

## Business Implications  

- **Customer-Centric Strategy:** Retailers can tailor services based on customer sentiment trends.  
- **Operational Efficiency:** Addressing checkout and delivery issues can significantly enhance satisfaction.  
- **Brand Loyalty:** Improving loyalty programs and staff training can foster stronger customer relationships.  

## Actionable Recommendations  

- **Improve Customer Service:** Train staff to handle refund issues more efficiently.  
- **Optimize Checkout Process:** Address **self-checkout inefficiencies** and invest in user-friendly interfaces.  
- **Enhance Stock Management:** Reduce stockouts through **real-time inventory tracking**.  
- **Expand Loyalty Programs:** Extend discounts and personalized offers to increase **customer retention**.  
- **Implement Better Feedback Channels:** Create internal review systems to gather real-time customer insights.  

## Future Enhancements  

- **Deep Learning Models:** Explore **LSTMs or Transformers** for improved text sentiment analysis.  
- **Real-Time Dashboard:** Build a **visual dashboard** for tracking customer sentiment dynamically.  
- **Topic Modeling:** Use **LDA or BERTopic** to extract more granular themes from customer reviews.  

## How to Run  

### Clone the Repository  

```sh
git clone https://github.com//kenny-balogun/sentiment_analysis_UK_supermarkets.git
```
### Install Dependencies

```sh
pip install -r requirements.txt
```

### Run the Notebook

```sh
jupyter notebook sentiment_analysis_UK_supermarkets.ipynb
```

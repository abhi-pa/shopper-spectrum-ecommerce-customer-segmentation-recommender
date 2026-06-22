# 🛒 Shopper Spectrum: Customer Segmentation and Product Recommendations in E-Commerce

An end-to-end machine learning project that analyzes online retail transaction data to segment customers using RFM analysis and K-Means clustering, and to recommend products using item-based collaborative filtering. Includes an interactive Streamlit web app.

## 📋 Project Overview

The global e-commerce industry generates massive volumes of transaction data containing rich patterns about how customers shop. Shopper Spectrum analyzes a real online retail dataset (~540,000+ transactions across 38 countries, spanning roughly 13 months) to extract these patterns and turn them into actionable business tools:

- **Customer Segmentation** — group customers into meaningful segments (High-Value, Regular, Occasional, At-Risk) based on their purchasing behaviour.
- **Product Recommendation** — suggest the top 5 most similar products for any given item, based on customer purchase patterns.

**Project Type:** Unsupervised Machine Learning (Clustering) + Recommendation System

## ✨ Features

- RFM (Recency, Frequency, Monetary) analysis of customer behaviour
- Customer segmentation using K-Means clustering
- Item-based collaborative filtering using cosine similarity
- Interactive Streamlit app with two modules:
  - 🎁 Product Recommendation
  - 👥 Customer Segmentation
- Graceful error handling and a clean, business-friendly interface

## 🗂️ Dataset

The dataset (`online_retail.csv`) contains invoice-level transaction records with the following fields:


|
 Column 
|
 Description 
|
|
---
|
---
|
|
 InvoiceNo 
|
 Invoice number (a "C" prefix indicates a cancellation) 
|
|
 StockCode 
|
 Product code 
|
|
 Description 
|
 Product name 
|
|
 Quantity 
|
 Quantity purchased 
|
|
 InvoiceDate 
|
 Date and time of the transaction 
|
|
 UnitPrice 
|
 Price per unit (GBP) 
|
|
 CustomerID 
|
 Unique customer identifier 
|
|
 Country 
|
 Country of the customer 
|

### Data Cleaning
- Removed rows with missing CustomerID (segmentation depends on identifying the buyer)
- Removed cancelled transactions (invoices flagged with a "C" prefix)
- Removed rows with negative or zero quantities and prices

## 🧠 Methodology

1. **Data preprocessing & cleaning** — handle missing values, cancellations, and invalid records.
2. **RFM feature engineering** — compute Recency, Frequency, and Monetary values per customer.
3. **Scaling** — apply a log transform (`log1p`) followed by standard scaling.
4. **Clustering** — segment customers with K-Means and assign business-friendly labels.
5. **Recommendation** — build an item-based collaborative filtering model using cosine similarity.
6. **Deployment** — serve both models through an interactive Streamlit app.

### Customer Segments


|
 Segment 
|
 Description 
|
|
---
|
---
|
|
 🟢 High-Value 
|
 Recent, frequent, high-spending customers. Prioritize loyalty rewards and VIP treatment. 
|
|
 🔵 Regular 
|
 Steady, dependable customers with moderate frequency and spend. Good for upsell offers. 
|
|
 🟡 Occasional 
|
 Infrequent buyers with lower spend. Target with engagement campaigns. 
|
|
 🔴 At-Risk 
|
 Customers who haven't purchased recently. Prioritize win-back/retention campaigns. 
|

## 📁 Repository Structure

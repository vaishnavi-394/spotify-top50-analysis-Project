# Spotify Top 50 SQL Data Analysis 📊

Analyze Spotify's Top 50 USA streaming data using SQL to uncover music trends, artist patterns & track insights.

![Spotify Logo](![Spotify imgjpeg](https://github.com/user-attachments/assets/e81bf706-dea5-4384-b293-7c1c472c18d3)
)
<img src="spotify_logo.jpg" width="600">


## 📂 Project Overview
This project involves analyzing a Spotify dataset with various attributes about tracks, albums, and artists using SQL. It covers an end-to-end process of normalizing a denormalized dataset, performing SQL queries of varying complexity (easy, medium, and advanced). The primary goals of the project are to practice Basic SQL skills and generate valuable insights from the dataset.
---

## 📊 **Project Steps**
1. 📌 **Dataset Exploration**
Before writing SQL queries, first explore the dataset to understand key attributes:

🎵 Song – track name

👤 Artist – performer of the track

🗓 Release_date – when the track was released

📊 Streams & Popularity – track’s performance metrics

⏱ Duration_ms – track length in milliseconds

🔖 Album_type & is_explicit – content categorization

This step helps identify trends & decide which questions to answer.

**Table Creation & Data Import
Create table spotify_streaming_top_50_usa in MySQL

Import cleaned dataset ("C:\Users\Shreya\OneDrive\Desktop\DATA ANALYTICS\SQL FOLDER\PROJECTS\spotify-streaming-top-50-usa.csv")**

3. 🛠 **DataSet Schema**:  
```sql
CREATE TABLE spotify_streaming_top_50_usa (
    track_id INT AUTO_INCREMENT PRIMARY KEY,
    date DATE,
    position INT,
    song VARCHAR(200),
    artist VARCHAR(150),
    streams BIGINT,
    url VARCHAR(300),
    popularity INT,
    duration_ms INT,
    album_type VARCHAR(50),
    release_date DATE,
    is_explicit BOOLEAN
);
'''
**Exploratory Data Analysis (EDA) using SQL**
** 1.Dataset Size & Unique Counts**
** 2.Release Dates Overview**
** 3. Distribution by Album Type & Explicit **
** 4.Popularity Statistics**
** 5.Text & Title Analysis**
** 6.Songs Released per Year**
** 7.Top 5 most popular songs**


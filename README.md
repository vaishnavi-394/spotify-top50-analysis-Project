# Spotify Top 50 SQL Data Analysis 📊

Analyze Spotify's Top 50 USA streaming data using SQL to uncover music trends, artist patterns & track insights.

(![Spotify imgjpeg](https://github.com/user-attachments/assets/e81bf706-dea5-4384-b293-7c1c472c18d3)
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

 Exploratory Data Analysis (EDA) using SQL
 1.Dataset Size & Unique Counts
 2.Release Dates Overview**
 3. Distribution by Album Type & Explicit 
 4.Popularity Statistics
 5.Text & Title Analysis
 6.Songs Released per Year
 7.Top 5 most popular songs

Querying the Data
After the data is inserted, various SQL queries can be written to explore and analyze the data. Queries are categorized into easy, medium, and advanced levels to help progressively develop SQL proficiency.

Easy Queries
Simple data retrieval, filtering, and basic aggregations.


Medium Queries
More complex queries involving grouping, aggregation functions, and joins.

Advanced Queries
Nested subqueries

# 🎵 Spotify SQL Practice Queries

> A collection of practical SQL queries performed on the **Spotify Top 50 USA dataset**, covering aggregation, subqueries, filters & text functions.

---

## 📊 **Practice Questions & Queries**

---

### **1️⃣ Retrieve the names of all tracks with popularity > 80**

🔍 *Simple filter to get highly popular tracks.*

```sql
SELECT song, popularity
FROM spotify_streaming_top_50_usa
WHERE popularity > 80;
```

---

### **2️⃣ List all unique album types present in the dataset**

📦 *Helps explore track categorization.*

```sql
SELECT DISTINCT album_type
FROM spotify_streaming_top_50_usa;
```

---

### **3️⃣ Get the total number of tracks released after 2020**

🕒 *Focus on modern releases.*

```sql
SELECT COUNT(*) AS 'TOTAL TRACKS'
FROM spotify_streaming_top_50_usa
WHERE YEAR(release_date) >= 2020;
```

---

### **4️⃣ Find all tracks that belong to the album type 'single'**

🎶 *Show tracks released as singles.*

```sql
SELECT song, artist, album_type
FROM spotify_streaming_top_50_usa
WHERE album_type = 'single';
```

---

### **5️⃣ Count the total number of tracks by each artist**

👤 *Identify most prolific artists.*

```sql
SELECT artist, COUNT(*) AS 'TOTAL TRACKS'
FROM spotify_streaming_top_50_usa
GROUP BY artist;
```

---

### **6️⃣ List tracks with above average popularity**

⭐ *Find tracks that performed better than dataset average.*

```sql
SELECT song, popularity
FROM spotify_streaming_top_50_usa
WHERE popularity > (
  SELECT AVG(popularity)
  FROM spotify_streaming_top_50_usa
);
```

---

### **7️⃣ List all tracks that have the same artist as 'Lavender Haze'**

🔗 *Subquery to find related tracks by the same artist.*

```sql
SELECT DISTINCT song, artist
FROM spotify_streaming_top_50_usa
WHERE artist IN (
  SELECT artist
  FROM spotify_streaming_top_50_usa
  WHERE song = 'Lavender Haze'
);
```

---

### **8️⃣ Find tracks with longest and shortest duration (in minutes)**

⏱ *Showcase duration extremes in the dataset.*

```sql
SELECT DISTINCT song, CONCAT(ROUND(duration_ms / 60000, 2), ' mins') AS duration_minutes
FROM spotify_streaming_top_50_usa
WHERE duration_ms = (SELECT MAX(duration_ms) FROM spotify_streaming_top_50_usa)
   OR duration_ms = (SELECT MIN(duration_ms) FROM spotify_streaming_top_50_usa);
```

---

### **9️⃣ Find tracks whose album\_type matches the most popular track's album\_type**

📌 *Use subquery to filter by album type of the top track.*

```sql
SELECT song, album_type, popularity
FROM spotify_streaming_top_50_usa
WHERE album_type = (
  SELECT album_type
  FROM spotify_streaming_top_50_usa
  ORDER BY popularity DESC
  LIMIT 1
);
```

---

### **🔟 Artists with longer-than-average tracks (albums after 2020)**

🚀 *Explore newer music trends based on track length.*

```sql
SELECT DISTINCT song, artist
FROM spotify_streaming_top_50_usa
WHERE duration_ms > (
  SELECT AVG(duration_ms)
  FROM spotify_streaming_top_50_usa
  WHERE release_date >= '2020-01-01'
);
```

---

## ✅ **✨ Why these queries matter?**

* Strengthen SQL subquery & aggregation skills
* Practice real-world data analysis scenarios
* Build a professional data analyst portfolio

---

⭐ *Connect on [LinkedIn]([https://linkedin.com/in/yourprofile](https://www.linkedin.com/in/vaishnavi-chakraborty-85b949292/)) for more SQL & data projects!*

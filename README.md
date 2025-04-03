
# 📁 Data Modeling with Apache Cassandra

This project demonstrates how to build an **ETL pipeline**, process event data using **Pandas**, and design query-specific **Cassandra tables** using **CQL (Cassandra Query Language)**. It's focused on modeling and querying song play event data from a music streaming app.

---

## 🎯 Project Overview

The goal is to take denormalized song play event logs and build a small-scale database using **Apache Cassandra** to support specific analytical queries. The project emphasizes **query-driven schema design**, a key principle when working with NoSQL databases.

---

## 🔄 ETL Pipeline

- Load raw event data from a CSV file
- Process and clean the data using **Pandas**
- Extract relevant fields to match query requirements
- Insert data row-by-row into Cassandra tables using the `cassandra-driver`

The ETL process is handled entirely in a Jupyter Notebook, with an emphasis on data transformation tailored to each use case.

---

## 📦 Dataset

The dataset is a pre-processed `.csv` file (`event_datafile_new.csv`), originally extracted from multiple JSON logs. It includes fields such as:

- `artist`, `song`, `length`, `user_id`, `session_id`, `item_in_session`
- User information like `first_name`, `last_name`, `gender`, `level`, `location`

---

## 🛠️ Technologies Used

- **Python 3**
- **Jupyter Notebook**
- **Pandas** for data wrangling
- **Apache Cassandra** and **CQL** for NoSQL database design
- **Cassandra Python Driver** (`cassandra-driver`) for inserting/querying data

---

## 🧠 Key Concepts & Deliverables

- 🔄 **ETL Process**: Data is read and transformed with Pandas, then inserted into appropriate Cassandra tables.
- 🧱 **Query-Based Schema Design**: Tables are created specifically to support predefined user queries.
- 🔑 **Primary Key Strategy**: Proper use of partition keys and clustering keys for fast, scalable reads.

---

## 🔍 Target Queries & Table Design

Each of the following queries is supported by its own Cassandra table, carefully modeled to optimize performance and allow efficient data access:

1. **Query 1**: What song was played during `sessionId = 338` and `itemInSession = 4`?
2. **Query 2**: Retrieve all songs played in `sessionId = 182` by `userId = 10`, sorted by `itemInSession`.
3. **Query 3**: Return every user (first and last name) who listened to the song `'All Hands Against His Own'`.

---

## 🚀 How to Run

1. Clone this repo:
   ```bash
   git clone https://github.com/haoranwang99/your-repo-name.git
   cd your-repo-name
   ```

2. Install dependencies:
   ```bash
   pip install pandas cassandra-driver jupyter
   ```

3. Start Jupyter:
   ```bash
   jupyter notebook
   ```

4. Open the notebook:
   - `Data Modelling with Apache Cassandra.ipynb`

5. Run all cells to execute the ETL pipeline, create tables, insert data, and run the target queries.

---

## ✅ Project Structure

```
├── event_datafile_new.csv                # Cleaned source data
├── Data Modelling with Apache Cassandra.ipynb  # Jupyter Notebook
├── README.md                             # Project documentation
```

---

## 🧹 Cleanup

The notebook includes commands to:
- Drop all Cassandra tables once queries are complete
- Shutdown the Cassandra session and cluster connection properly

---

## 👤 Author

Created by **Haoran Wang**  
GitHub: [@haoranwang99](https://github.com/haoranwang99)

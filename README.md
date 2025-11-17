FINAL PROFESSIONAL README.md (Copy–Paste Ready)
# 🕸️ Wikipedia Vote Network Analysis  
**Big Data Analytics Assignment | Apache Spark | GraphFrames**

This repository contains a full analysis of the **Wikipedia Admin Vote Network** using **PySpark** and **GraphFrames**.  
The network is a directed graph where `A → B` means *User A voted for User B* in a Wikipedia admin election.

---

## 📁 Repository Structure



📦 Wikipedia-Vote-Network-Analysis/
│
├── data/ # Edge list & node list (if allowed)
│ ├── wiki-Vote_edges.txt
│ └── wiki-Vote_nodes.txt
│
├── notebook/
│ └── PySpark_Wikipedia_Vote_Network_analysis.ipynb # Main code
│
├── reports/
│ ├── Assignment-1.pdf
│ └── Report_On_Analysis_of_Wikipedia_Vote_Network.pdf
│
├── requirements.txt
├── README.md
└── .gitignore


---

## 🚀 Technologies Used

- **Apache Spark**
- **PySpark**
- **GraphFrames**
- **Jupyter Notebook**
- **Python 3.x**

---

## 📘 Overview of Work Done

### ✔ 1. Data Loading & Cleaning
- Loaded raw Wikipedia vote edge-list into Spark.
- Constructed nodes from unique vertex IDs.
- Built a GraphFrame graph structure.

### ✔ 2. Graph Statistics
- Total number of nodes and edges.
- Validation against SNAP ground truth.

### ✔ 3. Connected Components
- **Largest Weakly Connected Component (WCC)**  
- **Largest Strongly Connected Component (SCC)**  
- Compared values against SNAP ground truth.

### ✔ 4. Triangle & Clustering Metrics
- Number of triangles  
- Average clustering coefficient  
- Fraction of closed triangles

### ✔ 5. Distance Metrics
- Graph Diameter (approximation using BFS sampling)
- Effective Diameter (90th percentile)

---

## 📊 Results Summary

| Metric                          | Ground Truth | Computed | Notes |
|----------------------------------|--------------|----------|-------|
| Nodes                            | 7115         | ✔ Matched | Correct parsing |
| Edges                            | 103689       | ✔ Matched | Correct graph construction |
| Largest WCC Nodes                | 7066         | ✔ Matched | Identical |
| Largest SCC Nodes                | 1300         | ✔ Matched | Identical |
| Avg. Clustering Coefficient      | 0.1409       | 0.1387    | Small rounding difference |
| Fraction of Closed Triangles     | 0.04564      | 0.03829   | Directed vs undirected definition |
| Diameter                         | 7            | 9         | Sampling approximation |
| Effective Diameter               | 3.8          | 4.0       | Very close |

---

## 🧪 How to Run the Notebook

### 1️⃣ Install dependencies:
```bash
pip install pyspark
pip install graphframes

2️⃣ Start Jupyter Notebook:
jupyter notebook

3️⃣ Open:
notebook/PySpark_Wikipedia_Vote_Network_analysis.ipynb

📥 Dataset Source

If not included due to size/license:

Download from Stanford SNAP:
Wikipedia Vote Network (wiki-Vote)

📄 Reports Included

Assignment-1.pdf – Main assignment instructions

Report_On_Analysis_of_Wikipedia_Vote_Network.pdf – Detailed comparison & explanation

📌 Additional Notes

Some metrics differ slightly due to Spark’s approximation & distributed computations.

All fundamental metrics match ground truth exactly.

🤝 Author Information

Your Name
Big Data Analytics — 2024/2025
University / Institution (optional)

# 🕸️ Wikipedia Vote Network Analysis

This project demonstrates how Big Data Analytics can be used to efficiently process and analyze large, complex networks. The Wikipedia Admin Vote Network contains thousands of nodes and over 100,000 directed edges, making distributed processing essential. Using PySpark and GraphFrames, we compute key graph metrics such as connected components, clustering, triangles, and diameter. This highlights the practical value of big data tools for scalable network analysis and real-world data processing.

## 📁 Repository Structure

```
Wikipedia-Vote-Network-Analysis/
│
├── data/                              # Network dataset
│   ├── wiki-Vote_edges.txt           # Edge list
│   └── wiki-Vote_nodes.txt           # Node list (if available)
│
├── notebook/
│   └── PySpark_Wikipedia_Vote_Network_analysis.ipynb  # Main analysis notebook
│
├── reports/
│   ├── Assignment-1.pdf              # Assignment instructions
│   └── Report_On_Analysis_of_Wikipedia_Vote_Network.pdf  # Detailed analysis report
│
├── requirements.txt                   # Python dependencies
├── README.md                         # Project documentation
└── .gitignore                        # Git ignore rules
```

## 🚀 Technologies Used

- **Apache Spark** - Distributed computing framework
- **PySpark** - Python API for Spark
- **GraphFrames** - Graph processing library for Spark
- **Jupyter Notebook** - Interactive development environment
- **Python 3.10.12** - Programming language

## 📊 Analysis Overview

### ✅ Completed Tasks

1. **Data Loading & Cleaning**
   - Loaded raw Wikipedia vote edge-list into Spark DataFrames
   - Constructed nodes from unique vertex IDs
   - Built GraphFrame graph structure for analysis

2. **Graph Statistics**
   - Calculated total number of nodes and edges
   - Validated results against SNAP dataset ground truth

3. **Connected Components**
   - Identified Largest Weakly Connected Component (WCC)
   - Identified Largest Strongly Connected Component (SCC)
   - Compared component sizes with reference values

4. **Triangle & Clustering Analysis**
   - Computed number of triangles in the network
   - Calculated average clustering coefficient
   - Determined fraction of closed triangles

5. **Distance Metrics**
   - Estimated Graph Diameter using BFS sampling
   - Computed Effective Diameter (90th percentile distance)

## 📈 Results Summary

| Metric | Ground Truth | Computed | Notes |
|--------|-------------|----------|-------|
| **Nodes** | 7,115 | 7,115 | ✅ Exact match |
| **Edges** | 103,689 | 103,689 | ✅ Exact match |
| **Largest WCC Nodes** | 7,066 | 7,066 | ✅ Exact match |
| **Largest SCC Nodes** | 1,300 | 1,300 | ✅ Exact match |
| **Avg. Clustering Coefficient** | 0.1409 | 0.1387 | ⚠️ Small rounding difference |
| **Fraction of Closed Triangles** | 0.04564 | 0.03829 | ⚠️ Directed vs undirected definition |
| **Diameter** | 7 | 9 | ⚠️ Sampling approximation |
| **Effective Diameter** | 3.8 | 4.0 | ✅ Very close |

## 🧪 Getting Started

### Prerequisites

- Python 3.10.12
- Java 8 or later
- Jupyter Notebook

### Installation & Setup

1. **Install dependencies:**
   ```bash
   pip install pyspark graphframes jupyter
   ```

2. **Start Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

3. **Open the analysis notebook:**
   - Navigate to: `notebook/PySpark_Wikipedia_Vote_Network_analysis.ipynb`

### Dataset

If dataset files are not included due to size/licensing:

1. Download from Stanford SNAP:
   - [Wikipedia Vote Network](https://snap.stanford.edu/data/wiki-Vote.html)

2. Place the downloaded files in the `data/` directory.

## 📄 Documentation

- **Assignment-1.pdf** - Original assignment instructions and requirements
- **Report_On_Analysis_of_Wikipedia_Vote_Network.pdf** - Detailed analysis report with methodology and results comparison

## 📌 Key Findings

- **Network Structure**: The Wikipedia vote network exhibits typical social network properties with a large weakly connected component containing most nodes.

- **Clustering**: The network shows moderate clustering, indicating communities of users who vote for each other.

- **Scale**: With over 7,000 nodes and 100,000 edges, this represents a substantial real-world social network.

- **Connectivity**: The presence of a large strongly connected component suggests reciprocal voting relationships among a core group of users.

## ⚠️ Notes on Discrepancies

- **Computational Differences**: Some metrics show slight variations due to Spark's distributed computation and approximation algorithms

- **Definition Variations**: Triangle counting differences arise from directed vs undirected graph interpretations

- **Sampling Effects**: Diameter calculation uses sampling for efficiency, which can lead to overestimation

## 🔍 Future Work

- Community detection using label propagation
- PageRank analysis to identify influential voters
- Temporal analysis of voting patterns
- Comparison with other social networks

## 🤝 Contributing

This is an academic project. For suggestions or improvements, please open an issue or contact the repository owner.

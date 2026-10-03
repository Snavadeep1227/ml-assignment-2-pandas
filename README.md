# ML Assignment 2 — Pandas: Messy Data Handling

**Repository Name**: `ml-assignment-2-pandas`  
**Submission Task**: Task 2 (Machine Learning Assignments 1 to 4\)

---

## 1\. Dataset Source Link

- **Dataset**: Netflix Movies and TV Shows Dataset  
- **Direct CSV URL**: [Netflix Titles Dataset on GitHub](https://raw.githubusercontent.com/prasertcbs/basic-dataset/master/netflix_titles.csv)  
- **Description**: Public dataset containing 8,807 titles across 12 features with mixed data types (dates, text, categorical, numeric), real missing values (`director`, `country`, `cast`, `date_added`), inconsistent categories, and duration text.

---

## 2\. Key Metrics & Benchmark Results

### A. Memory Optimization (Question 1\)

- **Initial Memory Usage**: 13.91 MB  
- **Optimized Memory Usage**: 12.58 MB  
- **Memory Saving**: **\~9.6% reduction** achieved via downcasting `release_year` to `int16` and converting low-cardinality text columns (`type`, `rating`) to `category`.

### B. File Size and Load Time Comparison (Question 13\)

- **CSV**:  
  - File Size: \~3.25 MB  
  - Load Time: \~0.0450 s  
- **Parquet**:  
  - File Size: \~1.42 MB (**56.3% smaller**)  
  - Load Time: \~0.0125 s (**3.6x faster load speed**)

---

## 3\. Profiling & Deduplication Highlights (Questions 2 & 3\)

- **Exact Duplicate Rows**: 0 in raw file; key duplicates identified on composite key `['title', 'type', 'release_year']`.  
- **Deduplication Rule**: Kept `first` chronological entry to preserve original catalog record sequencing while dropping redundant scrapes.

---

## 4\. Repository Contents

- `assignment2_pandas.ipynb`: Executable Colab notebook with every cell output visible.  
- `cleaned_netflix_titles.csv`: Final cleaned and enriched dataset.  
- `README.md`: Submission documentation and benchmark numbers.
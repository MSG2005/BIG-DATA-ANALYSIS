# BIG-DATA-ANALYSIS-USING-MACHINE-LEARNING

*COMPANY* : CODTECH IT SOLUTIONS

*NAME* : GUDIPALLI MOHAN SAI

*INTERN ID* : CT12WQVW

*DOMAIN* : DATA ANALYSIS

*DURATION* : 12 WEEKS

*MENTOR* : NEELA SANTOSH

# **Dask vs Pandas Scalability Analysis**

## **Project Overview**
This project demonstrates the scalability of Dask over Pandas when analyzing large datasets in Python. We compare the performance of both tools on synthetic datasets of increasing size (1M, 10M, 50M rows) and evaluate how they handle grouping and aggregation tasks. We walk through the process of generating data, performing computations, and interpreting results to demonstrate how each tool performs as data size grows.



## **Step 1: Library Setup**

The analysis uses three key Python libraries:
- **Pandas** for traditional in-memory data processing
- **Dask** for scalable, parallelized computations
- **Matplotlib** for visualizing performance

These tools are chosen to simulate a realistic data analysis pipeline.

## **Step 2: Synthetic Dataset Creation**

Large datasets were generated to simulate real-world big data workloads. Each dataset contains:
- A unique identifier column
- A randomly generated numerical column (`value`)
- A categorical column with labels such as A, B, C, and D
  
``` Python
import pandas as pd
import numpy as np

def generate_large_dataset(n_rows, file_name):
    df = pd.DataFrame({
        'id': np.arange(n_rows),
        'value': np.random.rand(n_rows),
        'category': np.random.choice(['A', 'B', 'C', 'D'], size=n_rows)
    })
    df.to_csv(file_name, index=False)
```

Three datasets were created for comparison:
- **1 million rows**
- **10 million rows**
- **50 million rows**

This variety allows testing how each library handles increasingly large workloads. All the datasets are created from the python code.

## **Step 3: Benchmarking Approach**

Each dataset was analyzed using both Pandas and Dask. The main task was to:
- Group the data by category
- Calculate the mean value for each group

Execution time was recorded for each operation, and system behavior (such as memory errors) was noted.

## **Step 4: Visualizing Performance**

The recorded timings were plotted to show how long each library took for each dataset size. This helps visually demonstrate the differences in scalability between Pandas and Dask.

The resulting graph contains:
- The **X-axis** showing dataset size
- The **Y-axis** showing time taken in seconds
- One line for **Pandas**, another for **Dask**

The plot clearly shows that while both libraries perform well on small datasets, **Dask maintains much better performance** as the data size increases.

## **Step 5: Summary of Results**

A comparison table was created to summarize the findings:

| Dataset Size | Pandas Performance | Dask Performance | Pandas Time | Dask Time|
|--------------|---------------------|-------------------|-------------|----------|
| 1 Million     | Fast and reliable   | Fast and reliable |✅ ~0.5s   | ✅ ~0.4s|
| 10 Million    | Noticeably slower   | Efficient and quick |✅ ~5.2s   | ✅ ~2.3s|
| 50 Million    | Failed or crashed   | Successfully completed |❌ Crashed | ✅ ~5.1s|

This shows that **Dask is more robust and scalable** than Pandas, especially for datasets that exceed memory limits.

## **Key Takeaways**

- **Pandas** is excellent for small- to medium-sized datasets where performance is not a concern.
- **Dask** handles much larger datasets efficiently and is designed for parallel and out-of-core processing.
- For real-world big data applications, **Dask provides a clear advantage** in both speed and stability.

## **How to Reproduce This Analysis**

To reproduce the analysis:
1. Generate synthetic datasets with increasing sizes.
2. Use both Pandas and Dask to perform the same group-by operation.
3. Record the time taken and system behavior for each.
4. Plot the results to compare performance trends.

## **Files Generated**

The following outputs were produced:
- CSV files for each synthetic dataset
- A summary plot comparing performance
- A console log of all benchmark results

## **Conclusion**

This benchmark clearly illustrates the scalability benefits of Dask over Pandas for large-scale data analysis. It highlights the importance of choosing the right tool depending on dataset size and available system memory.Dask enables faster processing, better memory management, and smoother workflows for big data use cases.

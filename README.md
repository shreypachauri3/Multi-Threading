# Methodology

The methodology involved executing matrix multiplication tasks with varying numbers of threads on a system with 8 CPU threads. The tasks were performed using Python's `threading` module, where each thread performed matrix multiplication independently. The number of threads ranged from 1 to 8, and for each configuration, the execution time was measured.

# Result Table

The table below presents the execution time (in seconds) for matrix multiplication with different numbers of threads:

| Num Threads | Execution Time (seconds) |
|-------------|--------------------------|
| 1           | 2.30                     |
| 2           | 2.21                     |
| 3           | 2.24                     |
| 4           | 2.43                     |
| 5           | 2.49                     |
| 6           | 2.41                     |
| 7           | 2.74                     |
| 8           | 2.34                     |

# Result Graph

The following graph illustrates the relationship between the number of threads and execution time:

![pic1](https://github.com/shreypachauri3/Multi-Threading/assets/78973003/e70512ac-eb05-4f08-ae72-9729614b7eee)
![pic2](https://github.com/shreypachauri3/Multi-Threading/assets/78973003/b8577a02-6838-4d45-a48c-acccb715a667)
![pic3-final](https://github.com/shreypachauri3/Multi-Threading/assets/78973003/74715d3d-ad32-45a3-8118-409313e54178)

# Conclusions

## 1. Resource Contention
The execution time slightly increases when using 4, 5, 6, and 7 threads compared to using 2 or 3 threads. This suggests that beyond a certain point, the CPU threads might experience resource contention, leading to diminishing returns as additional threads compete for resources.

## 2. Memory Bandwidth Limitation
Matrix multiplication tasks involve intensive memory access. Beyond a certain thread count, memory bandwidth might become a bottleneck, resulting in diminishing returns. This is indicated by the lack of significant improvement in execution time with increasing threads.

## 3. Task Parallelism vs. Data Parallelism
If the matrix multiplication task is not highly parallelizable, adding more threads may not significantly improve performance. The relatively consistent execution times across different thread counts suggest that the task may not benefit greatly from parallelization beyond a certain point.

## 4. Synchronization Overhead
Frequent synchronization between threads, such as accessing shared resources or coordinating work, can lead to overhead that outweighs the benefits of parallelism. This could contribute to the observed lack of improvement in execution time with increasing threads.

# Recommendations

- **Optimize Resource Usage:** Experiment with different thread counts to identify the optimal balance between parallelism and resource contention.
  
- **Profile and Optimize:** Profile the code to identify bottlenecks and optimize memory access patterns or algorithmic approaches.
  
- **Use Parallelization Techniques:** Consider using parallelization techniques like thread pooling or task scheduling to manage resources efficiently and reduce overhead.









<div align="center">

<h1>🚀 Algorithmic Engineering: AI Infra & Data Systems</h1>

<strong>A systematic approach to mastering the fundamentals of high-performance systems, data pipelines, and intelligent infrastructure.</strong>

<br/>
<br/>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=flat&logo=c%2B%2B&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=flat&logo=python&logoColor=ffdd54)
![Apache Spark](https://img.shields.io/badge/Apache%20Spark-FDEE21?style=flat&logo=apachespark&logoColor=black)
![LeetCode](https://img.shields.io/badge/LeetCode-000000?style=flat&logo=LeetCode&logoColor=#d16c06)

*"We do not learn algorithms and data structures to pass interviews. We learn them to build the foundations of intelligent systems."*

</div>

---

## 🧭 Navigation

- [🧭 Navigation](#-navigation)
- [🎯 Philosophy & Focus](#-philosophy--focus)
- [🏗️ Repository Structure](#️-repository-structure)
- [⚡ Core Problem Set & Implementation](#-core-problem-set--implementation)
  - [1. C/C++ Focus (AI Infra & Core Systems)](#1-cc-focus-ai-infra--core-systems)
  - [2. Python & Data Engineering Focus](#2-python--data-engineering-focus)
  - [3. Concurrency & Parallelism](#3-concurrency--parallelism)
- [🏗️ System Design & Engineering](#️-system-design--engineering)
  - [Mini-Project: High-Performance LRU Cache](#mini-project-high-performance-lru-cache)
  - [System Design: DataCody Agent](#system-design-datacody-agent)
- [📈 Progress & Metrics](#-progress--metrics)
- [🚀 Getting Started](#-getting-started)

---

## 🎯 Philosophy & Focus

This repository is not just a collection of solutions. It is a **living portfolio** demonstrating the engineering mindset required for roles in:

*   **AI Infrastructure:** Building low-latency, high-throughput systems for model training and serving.
*   **Intelligent Data Systems (DataCody Agent, FuelGenius):** Designing data pipelines, workflow compilers, and metadata management systems.
*   **Data Platform Engineering:** Creating scalable services for data ingestion, transformation, and analytics.

The code here emphasizes:
*   **Performance & Memory Awareness:** C/C++ solutions that consider cache locality, allocation costs, and Big-O complexity.
*   **Data Scalability:** Python solutions that leverage Pandas for in-memory efficiency and demonstrate distributed thinking (Spark/Hive).
*   **System Reliability:** Robust error handling, comprehensive testing, and clear documentation.
*   **Real-World Applicability:** Connecting algorithmic patterns to their use cases in caching, scheduling, and data processing.

---

## 🏗️ Repository Structure

This structure is designed for clarity, scalability, and automation.

```bash
Algorithmic-Engineering/
│
├── README.md                          # Overview + badges + progress board
├── LICENSE
├── .gitignore
│
├── .github/                           # CI/CD & Repo automation
│   └── workflows/
│       ├── cpp_ci.yml                 # C++ tests w/ GTest
│       ├── python_ci.yml              # Pytest + Pandas + Spark checks
│       └── lint.yml                   # Clang-Format & Black
│
├── scripts/                           # DevOps & Productivity
│   ├── setup_environment.sh
│   ├── run_tests.sh
│   ├── generate_stats.py              # Auto-generate problem stats
│   ├── sync_readme.py                 # Auto update README progress
│   └── export_diagrams.sh             # Convert mermaid -> images
│
│
├── src/
│   ├── core/                          # Your reusable engineering library
│   │   ├── cpp/
│   │   │   ├── CMakeLists.txt
│   │   │   ├── containers/            # Custom DS for interviews & infra
│   │   │   │   ├── lru_cache/
│   │   │   │   │   ├── include/lru_cache.h
│   │   │   │   │   ├── src/lru_cache.cpp
│   │   │   │   │   └── tests/test_lru_cache.cpp
│   │   │   │   ├── ring_buffer/
│   │   │   │   └── skiplist/
│   │   │   ├── concurrency/           # Multi-thread infra-level primitives
│   │   │   │   ├── thread_pool/
│   │   │   │   ├── lock_free_queue/
│   │   │   │   └── semaphore/
│   │   │   ├── graph/                 # Graph engine (for real workload)
│   │   │   ├── trees/
│   │   │   └── utils/
│   │   └── python/
│   │       ├── data_structures/       # DS in Python (heap/tree/utils)
│   │       ├── de_utils/
│   │       │   ├── spark_utils.py
│   │       │   ├── pandas_utils.py
│   │       │   └── hive_parser.py     # (Optional) Parse Hive outputs
│   │       └── concurrency/
│
│   ├── solutions/                     # LeetCode Engineering Solutions
│   │   ├── cpp/
│   │   │   ├── 0001-two-sum.cpp
│   │   │   ├── 0146-lru-cache.cpp
│   │   │   ├── 0295-find-median-from-data-stream.cpp
│   │   │   ├── concurrency/           # LC 多线程题
│   │   │   │   ├── 1114-print-in-order.cpp
│   │   │   │   └── 1188-design-bounded-blocking-queue.cpp
│   │   │   └── …
│   │   ├── python/
│   │   │   ├── 0001-two-sum.py
│   │   │   ├── data_engineering/      # DE + SQL reasoning
│   │   │   │   ├── 0176-second-highest-salary.sql
│   │   │   │   ├── 0185-department-top-three-salaries.sql
│   │   │   │   ├── pandas/
│   │   │   │   │   └── groupby_transform_cases.py
│   │   │   │   └── spark/
│   │   │   │       └── window_functions.py
│   │   │   └── …
│   │   ├── sql/
│   │   │   ├── easy/
│   │   │   ├── medium/
│   │   │   └── hard/
│   │   └── system_design_problems/
│   │       ├── tinyurl.md
│   │       ├── distributed_queue.md
│   │       └── data-workflow-compiler.md    # Your signature problem
│
│   └── system_design/                 # Infra-level thinking
│       ├── adr/                       # Architecture Decision Records
│       │   ├── 0001-why-thread-pool.md
│       │   ├── 0002-cache-layering.md
│       │   └── 0003-data-pipeline-compiler-core.md
│       ├── datacody_agent/
│       │   ├── DESIGN.md
│       │   ├── diagrams/
│       │   │   ├── pipeline-flow.mmd
│       │   │   └── architecture.png
│       │   └── prototype/
│       │       └── mini_compiler_demo.py
│       └── fuelgenius/
│           ├── TRAINING_DATA_SYSTEM.md
│           └── sampler/
│
│
├── tests/                             # Unified test structure
│   ├── cpp/
│   │   ├── test_core.cpp
│   │   └── test_solutions.cpp
│   ├── python/
│   │   ├── test_pandas.py
│   │   ├── test_spark.py
│   │   └── test_algorithms.py
│   └── sql/
│       └── validate_queries.py
│
│
├── docs/                              # Knowledge Base
│   ├── cheatsheets/
│   │   ├── cpp_stl.md
│   │   ├── linux_bash.md
│   │   ├── spark_sql.md
│   │   └── pandas.md
│   ├── patterns/
│   │   ├── sliding_window.md
│   │   ├── monotonic_stack.md
│   │   └── streaming_pipeline.md
│   ├── interview/
│   │   ├── ai_infra_100_questions.md
│   │   ├── cpp_system_questions.md
│   │   └── behavioral_star.md
│   └── articles/
│       ├── how-to-think-like-ai-infra-eng.md
│       └── from-leetcode-to-system-engineer.md
│
│
└── progress/                          # Growth tracking
    ├── solved_log.csv
    ├── stats.png
    ├── roadmap_90_days.md
    └── retrospective.md
```

---

## ⚡ Core Problem Set & Implementation

This curated list targets the exact skills needed for your career path.

### 1. C/C++ Focus (AI Infra & Core Systems)

*Problems that involve building complex data structures, managing memory, and achieving O(1) performance.*

| Problem | Title & Link | Key Concepts | Why It Matters |
|:--------|:-------------|:-------------|:---------------|
| **0146** | [LRU Cache](https://leetcode.com/problems/lru-cache/) | Hash Map, Doubly Linked List, O(1) ops | **The canonical caching problem.** Foundational for OS, DBs, and CDNs. |
| **0460** | [LFU Cache](https://leetcode.com/problems/lfu-cache/) | Hash Maps, Balanced Trees, O(1) complexity | Tests deep data structure composition skills. |
| **0295** | [Find Median from Data Stream](https://leetcode.com/problems/find-median-from-data-stream/) | Two Heaps (Min & Max) | Essential for real-time analytics and monitoring systems. |
| **0588** | [Design In-Memory File System](https://leetcode.com/problems/design-in-memory-file-system/) | Trie, OOP Design, API Design | Models hierarchical data, relevant for config systems and metadata stores. |
| **0642** | [Design Search Autocomplete System](https://leetcode.com/problems/design-search-autocomplete-system/) | Trie, Prefix Search, Ranking | Core intelligence for search bars and data discovery tools. |
| **0212** | [Word Search II](https://leetcode.com/problems/word-search-ii/) | Trie, Backtracking, DFS | Pattern matching on a grid; applicable to data validation and parsing. |

### 2. Python & Data Engineering Focus

*Problems that train your data-wrangling, SQL, and distributed processing mindset.*

| Problem | Title & Link | Implementation Focus & Key Concepts |
|:--------|:-------------|:-----------------------------------|
| **0176** | [Second Highest Salary](https://leetcode.com/problems/second-highest-salary/) | **Spark SQL:** `dense_rank()`, `window` functions. **Pandas:** `nlargest`, `drop_duplicates`. Handling NULLs. |
| **0178** | [Rank Scores](https://leetcode.com/problems/rank-scores/) | **Spark SQL:** Window functions (`rank` vs `dense_rank`). **Pandas:** `groupby` and `transform`. |
| **0185** | [Department Top Three Salaries](https://leetcode.com/problems/department-top-three-salaries/) | **Spark SQL:** Correlated subqueries or window functions with partitioning. **Pandas:** `merge`, `groupby`, and complex filtering. |
| **0262** | [Trips and Users](https://leetcode.com/problems/trips-and-users/) | Complex business logic, date-time handling, and conditional aggregation. Represents real-world metric calculation. |
| **0601** | [Human Traffic of Stadium](https://leetcode.com/problems/human-traffic-of-stadium/) | Identifying contiguous sequences. A common pattern in sessionization and event stream processing. |

### 3. Concurrency & Parallelism

*Problems that mirror the scheduling and coordination challenges in distributed data pipelines.*

| Problem | Title & Link | Key Concepts |
|:--------|:-------------|:-------------|
| **1114** | [Print in Order](https://leetcode.com/problems/print-in-order/) | Mutex, Condition Variables. Basic thread sequencing. |
| **1115** | [Print FooBar Alternately](https://leetcode.com/problems/print-foobar-alternately/) | Semaphores. Control interleaved execution of two threads. |
| **1188** | [Design Bounded Blocking Queue](https://leetcode.com/problems/design-bounded-blocking-queue/) | **CRITICAL.** Producer-Consumer pattern. Mutex, Condition Variables. The backbone of data pipelines. |
| **1226** | [The Dining Philosophers](https://leetcode.com/problems/the-dining-philosophers/) | Deadlock prevention, Resource hierarchy. |

---

## 🏗️ System Design & Engineering

### Mini-Project: High-Performance LRU Cache

This demonstrates moving from a "solution" to a "component."

**`src/core/cpp/lru_cache/include/lru_cache.h`**
```cpp
#ifndef ALGORITHMIC_ENGINEERING_LRU_CACHE_H
#define ALGORITHMIC_ENGINEERING_LRU_CACHE_H

#include <unordered_map>
#include <list>
#include <mutex> // For thread-safety

namespace core {
    
template <typename K, typename V>
class LRUCache {
public:
    explicit LRUCache(size_t capacity);
    
    // Core API
    bool get(const K& key, V& value);
    void put(const K& key, const V& value);
    
    // Observability for production systems
    size_t size() const;
    double hit_rate() const;
    void clear_stats();

private:
    void evict();
    void promote(typename std::list<std::pair<K, V>>::iterator it);
    
    size_t capacity_;
    std::list<std::pair<K, V>> items_; // (key, value) pairs in access order
    std::unordered_map<K, typename std::list<std::pair<K, V>>::iterator> cache_map_;
    
    // Metrics
    std::atomic<size_t> hits_{0};
    std::atomic<size_t> misses_{0};
    mutable std::mutex mutex_; // For thread-safe access
};

} // namespace core

#endif //ALGORITHMIC_ENGINEERING_LRU_CACHE_H
```
**Key Features:**
*   **Namespace & Include Guards:** Professional C++ structure.
*   **Thread Safety:** Uses `mutex` for concurrent access.
*   **Observability:** Provides `hit_rate()` and other metrics.
*   **Template Design:** Reusable for any key-value type.
*   **Comprehensive Tests:** Unit tests in `tests/` validate correctness under concurrent load.

### System Design: DataCody Agent

**Problem:** Design an intelligent agent that automates dataset profiling, quality checks, and model recommendation.

**Key Discussion Points (Architecture Decision Record - ADR):**

1.  **Service Decomposition:**
    *   **Ingestion Service:** Handles streaming/batch data from S3, Kafka. Built with async Python/Go.
    *   **Profiling Service:** Uses Spark for distributed statistical profiling (mean, std, histogram, null-count).
    *   **Metadata Catalog:** PostgreSQL for structured metadata, Neo4j for data lineage graphs.
    *   **Recommendation Engine:** Lightweight ML model (e.g., Random Forest) that takes dataset stats (num_cols, avg_val, etc.) and suggests a model type (classification, regression).

2.  **Data Flow:**
    ```
    Data Ingest -> (Trigger) -> Spark Profiling Job -> Write Metadata -> Feature Extraction -> Model Recommendation -> Cache Result (Redis)
    ```

3.  **Pipeline Integration:**
    *   The agent is triggered via a webhook from a CI/CD pipeline (e.g., GitLab CI, Airflow DAG) whenever a new dataset version is registered.
    *   Uses a **Bash script** (`scripts/trigger_agent.sh`) as the pipeline entry point, which calls the agent's REST API.

---

## 📈 Progress & Metrics

*   **`progress/solved_log.csv`:** Auto-generated by a Python script that parses your LeetCode submissions.
    ```csv
    date,problem_id,title,difficulty,language,time_taken_minutes,notes
    2023-10-27,146,LRU Cache,Hard,C++,45,Need to review edge case: capacity=0
    ```
*   **`progress/roadmap_90_days.md`:** A phased plan.
    *   **Phase 1 (Days 1-30):** Core DSA & SQL Mastery.
    *   **Phase 2 (Days 31-60):** Concurrency & System Design Deep Dive.
    *   **Phase 3 (Days 61-90):** Integration & Mock Interviews.
*   **`progress/mistakes_retrospective.md`:** A log of errors and lessons learned, fostering a growth mindset.

---

## 🚀 Getting Started

1.  **Clone and Setup:**
    ```bash
    git clone https://github.com/yourusername/Algorithmic-Engineering.git
    cd Algorithmic-Engineering
    ./scripts/setup_environment.sh
    ```

2.  **Run Tests:**
    ```bash
    # Run C++ tests
    ./scripts/run_tests.sh cpp
    # Run Python tests
    ./scripts/run_tests.sh python
    ```

3.  **Solve a Problem:**
    *   Create a new file in `src/solutions/` (e.g., `src/solutions/cpp/1234-new-problem.cpp`).
    *   Implement the solution with detailed comments and time/space complexity.
    *   Write corresponding unit tests.
    *   Update the `progress/` logs.

4.  **Contribute:** PRs are welcome for new solutions, optimizations, or documentation improvements.

---

<div align="center">

**This is more than a study guide—it's the foundation of your engineering legacy. Build, learn, and iterate.**

</div>







---











## **LeetCode Solutions & Interview Prep**

### **Overview**
This repository documents my journey in mastering Data Structures, Algorithms, and System Design principles. The focus is on building a strong foundation for roles in **AI Infrastructure**, **Data-Intelligent Systems**, and **High-Performance Data Engineering**. Solutions are implemented with an emphasis on performance, readability, and real-world applicability, primarily using **C/C++** for core algorithms and **Python** for data-intensive problems.

**Key Focus Areas:**
*   **Performance-Critical Systems:** C/C++ implementations focusing on memory management and low-latency.
*   **Large-Scale Data Processing:** Python solutions leveraging Pandas, PySpark SQL, and understanding of distributed systems (Spark/Hive).
*   **System Automation & DevOps:** Scripts and pipelines for automation (Linux Bash, Pipeline tools).
*   **API & System Design:** Architecting scalable and robust systems.

---

### **Repository Structure**
```
Algorithmic-Engineering/
│
├── README.md                          # Overview + badges + progress board
├── LICENSE
├── .gitignore
│
├── .github/                           # CI/CD & Repo automation
│   └── workflows/
│       ├── cpp_ci.yml                 # C++ tests w/ GTest
│       ├── python_ci.yml              # Pytest + Pandas + Spark checks
│       └── lint.yml                   # Clang-Format & Black
│
├── scripts/                           # DevOps & Productivity
│   ├── setup_environment.sh
│   ├── run_tests.sh
│   ├── generate_stats.py              # Auto-generate problem stats
│   ├── sync_readme.py                 # Auto update README progress
│   └── export_diagrams.sh             # Convert mermaid -> images
│
│
├── src/
│   ├── core/                          # Your reusable engineering library
│   │   ├── cpp/
│   │   │   ├── CMakeLists.txt
│   │   │   ├── containers/            # Custom DS for interviews & infra
│   │   │   │   ├── lru_cache/
│   │   │   │   │   ├── include/lru_cache.h
│   │   │   │   │   ├── src/lru_cache.cpp
│   │   │   │   │   └── tests/test_lru_cache.cpp
│   │   │   │   ├── ring_buffer/
│   │   │   │   └── skiplist/
│   │   │   ├── concurrency/           # Multi-thread infra-level primitives
│   │   │   │   ├── thread_pool/
│   │   │   │   ├── lock_free_queue/
│   │   │   │   └── semaphore/
│   │   │   ├── graph/                 # Graph engine (for real workload)
│   │   │   ├── trees/
│   │   │   └── utils/
│   │   └── python/
│   │       ├── data_structures/       # DS in Python (heap/tree/utils)
│   │       ├── de_utils/
│   │       │   ├── spark_utils.py
│   │       │   ├── pandas_utils.py
│   │       │   └── hive_parser.py     # (Optional) Parse Hive outputs
│   │       └── concurrency/
│
│   ├── solutions/                     # LeetCode Engineering Solutions
│   │   ├── cpp/
│   │   │   ├── 0001-two-sum.cpp
│   │   │   ├── 0146-lru-cache.cpp
│   │   │   ├── 0295-find-median-from-data-stream.cpp
│   │   │   ├── concurrency/           # LC 多线程题
│   │   │   │   ├── 1114-print-in-order.cpp
│   │   │   │   └── 1188-design-bounded-blocking-queue.cpp
│   │   │   └── …
│   │   ├── python/
│   │   │   ├── 0001-two-sum.py
│   │   │   ├── data_engineering/      # DE + SQL reasoning
│   │   │   │   ├── 0176-second-highest-salary.sql
│   │   │   │   ├── 0185-department-top-three-salaries.sql
│   │   │   │   ├── pandas/
│   │   │   │   │   └── groupby_transform_cases.py
│   │   │   │   └── spark/
│   │   │   │       └── window_functions.py
│   │   │   └── …
│   │   ├── sql/
│   │   │   ├── easy/
│   │   │   ├── medium/
│   │   │   └── hard/
│   │   └── system_design_problems/
│   │       ├── tinyurl.md
│   │       ├── distributed_queue.md
│   │       └── data-workflow-compiler.md    # Your signature problem
│
│   └── system_design/                 # Infra-level thinking
│       ├── adr/                       # Architecture Decision Records
│       │   ├── 0001-why-thread-pool.md
│       │   ├── 0002-cache-layering.md
│       │   └── 0003-data-pipeline-compiler-core.md
│       ├── datacody_agent/
│       │   ├── DESIGN.md
│       │   ├── diagrams/
│       │   │   ├── pipeline-flow.mmd
│       │   │   └── architecture.png
│       │   └── prototype/
│       │       └── mini_compiler_demo.py
│       └── fuelgenius/
│           ├── TRAINING_DATA_SYSTEM.md
│           └── sampler/
│
│
├── tests/                             # Unified test structure
│   ├── cpp/
│   │   ├── test_core.cpp
│   │   └── test_solutions.cpp
│   ├── python/
│   │   ├── test_pandas.py
│   │   ├── test_spark.py
│   │   └── test_algorithms.py
│   └── sql/
│       └── validate_queries.py
│
│
├── docs/                              # Knowledge Base
│   ├── cheatsheets/
│   │   ├── cpp_stl.md
│   │   ├── linux_bash.md
│   │   ├── spark_sql.md
│   │   └── pandas.md
│   ├── patterns/
│   │   ├── sliding_window.md
│   │   ├── monotonic_stack.md
│   │   └── streaming_pipeline.md
│   ├── interview/
│   │   ├── ai_infra_100_questions.md
│   │   ├── cpp_system_questions.md
│   │   └── behavioral_star.md
│   └── articles/
│       ├── how-to-think-like-ai-infra-eng.md
│       └── from-leetcode-to-system-engineer.md
│
│
└── progress/                          # Growth tracking
    ├── solved_log.csv
    ├── stats.png
    ├── roadmap_90_days.md
    └── retrospective.md
```

---

### **Core Problem Set & Implementation Focus**

This list is curated for your specific tech stack and career goals.

#### **1. C/C++ Focus (AI Infra & Core Systems)**
*These problems test memory management, pointers, and building complex, efficient data structures.*

| Problem # | Title | Key Concepts | Why Important? |
| :--- | :--- | :--- | :--- |
| [146](https://leetcode.com/problems/lru-cache/) | **LRU Cache** | Hash Map, Doubly Linked List, O(1) operations | **Fundamental for caching** in OS, databases, and infra. A classic system design question. |
| [460](https://leetcode.com/problems/lfu-cache/) | LFU Cache | Hash Map, Linked Lists, O(1) complexity | Even more complex caching policy. Shows deep DS understanding. |
| [588](https://leetcode.com/problems/design-in-memory-file-system/) | Design In-Memory File System | Trie, Hash Map, Object-Oriented Design | Tests system modeling skills, relevant for any infrastructure role. |
| [642](https://leetcode.com/problems/design-search-autocomplete-system/) | Design Search Autocomplete System | Trie, Sorting, Prefix Search | Core to intelligent systems and search functionality. |
| [295](https://leetcode.com/problems/find-median-from-data-stream/) | Find Median from Data Stream | Two Heaps (Min & Max) | Essential for data streaming applications and real-time analytics. |
| [239](https://leetcode.com/problems/sliding-window-maximum/) | Sliding Window Maximum | Deque, Monotonic Queue | Common pattern in data streams and network processing. |
| [212](https://leetcode.com/problems/word-search-ii/) | Word Search II | Trie, Backtracking, DFS | Combines a complex data structure with graph traversal. |
| [224](https://leetcode.com/problems/basic-calculator/) | Basic Calculator | Stack, String Parsing | Tests your ability to handle state and parse expressions, like a mini-interpreter. |

#### **2. Python & Data Engineering Focus (Pandas, Spark SQL)**
*Focus on data manipulation, SQL, and efficient handling of large datasets.*

| Problem # | Title | Key Concepts | Implementation Focus |
| :--- | :--- | :--- | :--- |
| [176](https://leetcode.com/problems/second-highest-salary/) | Second Highest Salary | SQL: `DENSE_RANK()`, `OFFSET`, `LIMIT` | **Spark SQL / Hive** translation. Handling NULLs. |
| [178](https://leetcode.com/problems/rank-scores/) | Rank Scores | SQL: Window Functions (`RANK`, `DENSE_RANK`) | **Spark SQL**: Using Window functions for ranking. |
| [185](https://leetcode.com/problems/department-top-three-salaries/) | Department Top Three Salaries | SQL: Correlated Subqueries, Window Functions | **Pandas**: `groupby`, `transform`, `rank`. **Spark SQL**: Window functions with partitioning. |
| [601](https://leetcode.com/problems/human-traffic-of-stadium/) | Human Traffic of Stadium | SQL: Complex Joins, Window Functions | Identifying contiguous segments in data - a common ETL task. |
| [262](https://leetcode.com/problems/trips-and-users/) | Trips and Users | SQL: Complex Filtering, Aggregation, `CASE` | Real-world business logic and metric calculation. |
| [1158](https://leetcode.com/problems/market-analysis-i/) | Market Analysis I | SQL: `JOIN`, `GROUP BY`, `COUNT`, `CASE` | Standard business intelligence query. |
| [Pandas 50](https://leetcode.com/studyplan/pandas-50-lc/) | (LeetCode Pandas Study Plan) | `merge`, `groupby`, `pivot_table`, `melt` | Master all core Pandas operations for data wrangling. |

#### **3. Algorithmic Patterns (Essential for All Roles)**
*   **Graph Algorithms:** BFS, DFS, Topological Sort (for task scheduling), Dijkstra's (for routing).
*   **Dynamic Programming:** Knapsack, Longest Common Subsequence, State Machine DP.
*   **Tree Traversals:** Inorder/Preorder/Postorder, Level Order, BST operations.
*   **Binary Search:** Both on arrays and in application (e.g., capacity planning).

---

### **System Design & Engineering Implementation**

This section is critical for `DataCody Agent`, `FuelGenius`, and `AI Infra` roles.

#### **Mini-Project: Implementing a High-Performance LRU Cache in C++**
This goes beyond just solving the problem on LeetCode. It's about building a robust, testable component.

**`cpp/src/core/lru_cache.h`**
```cpp
#ifndef LRU_CACHE_H
#define LRU_CACHE_H

#include <unordered_map>
#include <list>

template <typename K, typename V>
class LRUCache {
public:
    explicit LRUCache(size_t capacity);
    V get(K key);
    void put(K key, V value);
    // Add methods for metrics (e.g., hit rate) for observability.
    double get_hit_rate() const;

private:
    void evict();

    size_t capacity_;
    std::list<std::pair<K, V>> items_; // Doubly-linked list for order
    std::unordered_map<K, typename std::list<std::pair<K, V>>::iterator> cache_map_; // For O(1) access
    size_t hits_{0};
    size_t misses_{0};
};

#endif // LRU_CACHE_H
```
**Implementation (`lru_cache.cpp`)** would include the detailed logic, and **`tests/test_lru_cache.cpp`** would validate correctness and performance under load.

#### **System Design Problem: Design DataCody Agent**
*A hypothetical question directly related to your goal.*

**Problem:** Design an intelligent agent ("DataCody") that can profile datasets, suggest quality checks, and recommend suitable ML models.

**Key Discussion Points:**
1.  **Service Architecture:** Microservices vs Monolith. API design (REST/gRPC) for interactions.
2.  **Data Ingestion & Profiling:** How to handle large, streaming datasets? Using Spark for distributed profiling? Integration with data lakes (S3/HDFS).
3.  **Metadata Storage:** What database to use? Relational (PostgreSQL) for structured metadata, or a graph DB (Neo4j) for data lineage?
4.  **Model Recommendation Engine:** A separate service. How is it trained? How are features (dataset statistics) fed into it?
5.  **Caching & Performance:** Use Redis/Memcached to cache profile results and model recommendations.
6.  **Pipeline Integration:** How would this agent fit into a CI/CD pipeline for data? (e.g., triggered on new data version).

---

### **Interview Preparation & Notes**

#### **Coding Interview Guide**
*   **Clarify:** Ask questions. (Constraints, input/output format, edge cases).
*   **Example:** Walk through a small example to validate understanding.
*   **Brute Force:** State the naive solution and its complexity.
*   **Optimize:** Discuss better approaches (BUD: Bottlenecks, Unnecessary work, Duplicate work). Use known patterns.
*   **Implement:** Write clean, modular code. Use meaningful variable names.
*   **Test:** Walk through your code with the initial example and edge cases.

#### **Language-Specific Notes**
*   **C++:** Know the STL inside out (`vector`, `map`, `unordered_map`, `set`, `priority_queue`). Understand object lifecycle, rule of three/five, move semantics, and smart pointers.
*   **Python:** Understand the GIL, list comprehensions, generators, decorators, and the `collections` module (`defaultdict`, `Counter`, `deque`).

#### **Behavioral Questions (Using the STAR Method)**
*   Prepare stories for: "A challenging technical project," "A time you had a conflict," "How you handled a tight deadline."
*   Relate answers back to your projects and the skills required for `AI Infra` and `Data Systems`.

---

### **How to Use This Repository**
1.  **Fork this template** to your own GitHub.
2.  **Solve Problems Systematically:** For each problem, create a file in the appropriate `src/solutions/` directory.
3.  **Write Tests:** Always write corresponding unit tests in the `tests/` directory. This demonstrates professional coding habits.
4.  **Document:** Add a comment at the top of each solution file with the problem description, approach, and time/space complexity.
5.  **Iterate on Design:** Use the `system_design/` folder to draft and refine your answers to system design questions.

**Keep Grinding! This organized approach will pay off immensely in your interviews.**

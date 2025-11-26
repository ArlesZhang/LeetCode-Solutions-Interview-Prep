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

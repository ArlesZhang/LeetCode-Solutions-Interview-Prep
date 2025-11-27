
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

## Navigation

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

## Philosophy & Focus

This repository documents my journey in mastering Data Structures, Algorithms, and System Design principles. The focus is on building a strong foundation for roles in **AI Infrastructure**, **Data-Intelligent Systems**, and **High-Performance Data Engineering**.

**Key Focus Areas:**
*   **Performance-Critical Systems:** C/C++ implementations focusing on memory management and low-latency.
*   **Large-Scale Data Processing:** Python solutions leveraging Pandas, PySpark SQL, and understanding of distributed systems.
*   **System Automation & DevOps:** Scripts and pipelines for automation (Linux Bash, Pipeline tools).
*   **API & System Design:** Architecting scalable and robust systems.

---

## Repository Structure

```
LeetCode-Solutions-Interview-Prep/
├── 📚 docs/                           # 知识库文档
│   ├── articles/                      # 技术文章和深度思考
│   │   ├── from-leetcode-to-system-engineer.md    # 职业发展路径
│   │   └── how-to-think-like-ai-infra-eng.md      # AI基础设施思维模式
│   ├── cheatsheets/                   # 速查手册
│   │   ├── cpp_stl.md                 # C++标准库快速参考
│   │   ├── linux_bash.md              # Linux命令和脚本技巧
│   │   ├── pandas.md                  # Pandas数据处理备忘
│   │   └── spark_sql.md               # Spark SQL语法和优化
│   ├── interview/                     # 面试准备资料
│   │   ├── ai_infra_100_questions.md  # AI基础设施面试题
│   │   ├── behavioral_star.md         # 行为面试STAR方法
│   │   └── cpp_system_questions.md    # C++系统级开发问题
│   └── patterns/                      # 算法和系统模式
│       ├── monotonic_stack.md         # 单调栈模式及应用
│       ├── sliding_window.md          # 滑动窗口模式
│       └── streaming_pipeline.md      # 流式处理管道设计
│
├── ⚖️ LICENSE                         # 开源许可证
├── 📈 progress/                       # 学习进度跟踪
│   ├── retrospective.md               # 学习回顾和反思
│   ├── roadmap_90_days.md             # 90天学习路线图
│   └── solved_log.csv                 # 解题记录统计
│
├── 📖 README.md                       # 项目主文档
├── ⚙️ scripts/                        # 自动化脚本
│   ├── export_diagrams.sh             # 导出架构图
│   ├── generate_stats.py              # 生成学习统计数据
│   ├── run_tests.sh                   # 运行测试套件
│   ├── setup_environment.sh           # 环境配置脚本
│   └── sync_readme.py                 # 同步README进度
│
├── 💻 src/                            # 源代码核心
│   ├── 🔧 core/                       # 可复用工程组件库
│   │   ├── cpp/                       # C++高性能组件
│   │   │   ├── CMakeLists.txt         # C++项目构建配置
│   │   │   ├── concurrency/           # 并发编程原语
│   │   │   │   ├── lock_free_queue/   # 无锁队列实现
│   │   │   │   ├── semaphore/         # 信号量同步
│   │   │   │   └── thread_pool/       # 线程池管理
│   │   │   ├── containers/            # 自定义数据结构
│   │   │   │   ├── lru_cache/         # LRU缓存实现
│   │   │   │   │   ├── include/lru_cache.h        # 头文件
│   │   │   │   │   ├── src/lru_cache.cpp          # 实现文件
│   │   │   │   │   └── tests/test_lru_cache.cpp   # 单元测试
│   │   │   │   ├── ring_buffer/       # 环形缓冲区
│   │   │   │   └── skiplist/          # 跳表数据结构
│   │   │   ├── graph/                 # 图算法引擎
│   │   │   ├── trees/                 # 树结构和算法
│   │   │   └── utils/                 # 工具函数
│   │   └── python/                    # Python数据工程工具
│   │       ├── concurrency/           # Python并发编程
│   │       ├── data_structures/       # Python数据结构实现
│   │       └── de_utils/              # 数据工程工具集
│   │           ├── hive_parser.py     # Hive查询解析器
│   │           ├── pandas_utils.py    # Pandas工具函数
│   │           └── spark_utils.py     # Spark会话管理
│   │
│   ├── 🎯 solutions/                  # LeetCode解决方案
│   │   ├── cpp/                       # C++算法实现
│   │   │   ├── 0001-two-sum.cpp       # 两数之和
│   │   │   ├── 0146-lru-cache.cpp     # LRU缓存设计
│   │   │   ├── 0295-find-median-from-data-stream.cpp  # 数据流中位数
│   │   │   └── concurrency/           # 并发编程题目
│   │   │       ├── 1114-print-in-order.cpp          # 顺序打印
│   │   │       └── 1188-design-bounded-blocking-queue.cpp  # 阻塞队列
│   │   ├── python/                    # Python解决方案
│   │   │   ├── 0001-two-sum.py        # Python版两数之和
│   │   │   └── data_engineering/      # 数据工程题目
│   │   │       ├── 0176-second-highest-salary.sql    # 第二高薪水
│   │   │       ├── 0185-department-top-three-salaries.sql  # 部门前三薪水
│   │   │       ├── pandas/            # Pandas数据处理
│   │   │       │   └── groupby_transform_cases.py    # 分组转换案例
│   │   │       └── spark/             # Spark处理模式
│   │   │           └── window_functions.py           # 窗口函数应用
│   │   ├── sql/                       # SQL专项练习
│   │   │   ├── easy/                  # 简单难度
│   │   │   │   └── 0175-combine-two-tables.sql       # 合并两表
│   │   │   ├── hard/                  # 困难难度
│   │   │   │   └── 0185-department-top-three-salaries.sql  # 部门前三
│   │   │   └── medium/                # 中等难度
│   │   │       └── 0176-second-highest-salary.sql    # 第二高薪水
│   │   └── system_design_problems/    # 系统设计题目
│   │       ├── data-workflow-compiler.md     # 数据工作流编译器设计
│   │       ├── distributed_queue.md          # 分布式队列设计
│   │       └── tinyurl.md                    # 短链接系统设计
│   │
│   └── 🏗️ system_design/              # 系统架构设计
│       ├── adr/                       # 架构决策记录
│       │   ├── 0001-why-thread-pool.md        # 线程池选择原因
│       │   ├── 0002-cache-layering.md         # 缓存分层设计
│       │   └── 0003-data-pipeline-compiler-core.md  # 数据管道编译器核心
│       ├── datacody_agent/            # DataCody智能代理设计
│       │   ├── DESIGN.md              # 整体架构设计文档
│       │   ├── diagrams/              # 架构图
│       │   │   └── pipeline-flow.mmd  # 管道流程图
│       │   └── prototype/             # 原型实现
│       │       └── mini_compiler_demo.py      # 迷你编译器演示
│       └── fuelgenius/                # FuelGenius项目设计
│           ├── sampler/               # 数据采样器
│           │   └── data_sampler.py    # 数据采样实现
│           └── TRAINING_DATA_SYSTEM.md        # 训练数据系统设计
│
└── ✅ tests/                          # 测试套件
    ├── cpp/                           # C++测试
    │   ├── test_core.cpp              # 核心组件测试
    │   └── test_solutions.cpp         # 解决方案测试
    ├── python/                        # Python测试
    │   ├── test_algorithms.py         # 算法测试
    │   ├── test_pandas.py             # Pandas功能测试
    │   └── test_spark.py              # Spark功能测试
    └── sql/                           # SQL测试
        └── validate_queries.py        # 查询验证测试
```

---

## Core Problem Set & Implementation

### 1. C/C++ Focus (AI Infra & Core Systems)

| Problem | Title & Link | Key Concepts | Why It Matters |
|:--------|:-------------|:-------------|:---------------|
| **0146** | [LRU Cache](https://leetcode.com/problems/lru-cache/) | Hash Map, Doubly Linked List, O(1) ops | **Fundamental for caching** in OS, databases, and infra. |
| **0460** | [LFU Cache](https://leetcode.com/problems/lfu-cache/) | Hash Maps, Balanced Trees, O(1) complexity | Tests deep data structure composition skills. |
| **0295** | [Find Median from Data Stream](https://leetcode.com/problems/find-median-from-data-stream/) | Two Heaps (Min & Max) | Essential for real-time analytics and monitoring systems. |
| **0588** | [Design In-Memory File System](https://leetcode.com/problems/design-in-memory-file-system/) | Trie, OOP Design, API Design | Models hierarchical data, relevant for config systems and metadata stores. |
| **0239** | [Sliding Window Maximum](https://leetcode.com/problems/sliding-window-maximum/) | Deque, Monotonic Queue | Common pattern in data streams and network processing. |
| **0642** | [Design Search Autocomplete System](https://leetcode.com/problems/design-search-autocomplete-system/) | Trie, Prefix Search, Ranking | Core intelligence for search bars and data discovery tools. |
| **0212** | [Word Search II](https://leetcode.com/problems/word-search-ii/) | Trie, Backtracking, DFS | Pattern matching for data validation and parsing. |

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

| Problem | Title & Link | Key Concepts |
|:--------|:-------------|:-------------|
| **1114** | [Print in Order](https://leetcode.com/problems/print-in-order/) | Mutex, Condition Variables |
| **1115** | [Print FooBar Alternately](https://leetcode.com/problems/print-foobar-alternately/) | Semaphores. Control interleaved execution of two threads. |
| **1188** | [Design Bounded Blocking Queue](https://leetcode.com/problems/design-bounded-blocking-queue/) | Producer-Consumer pattern, Mutex, Condition Variables |
| **1226** | [The Dining Philosophers](https://leetcode.com/problems/the-dining-philosophers/) | Deadlock prevention, Resource hierarchy |

| Problem Name | LeetCode # | Difficulty | Key Concepts | Relevance to Your Goals | Link |
|-------------|------------|------------|--------------|------------------------|------|
| **Fizz Buzz Multithreaded** | #1195 | 🟠 Medium | Synchronization | Concurrent output coordination | [🔗](https://leetcode.com/problems/fizz-buzz-multithreaded/) |
| **Web Crawler Multithreaded** | #1242 | 🟠 Medium | Concurrent BFS, Thread pools | Distributed web scraping patterns | [🔗](https://leetcode.com/problems/web-crawler-multithreaded/) |


#### 4. Advanced System Design Problems

| Problem Name | LeetCode # | Difficulty | Key Concepts | Relevance to Your Goals | Link |
|-------------|------------|------------|--------------|------------------------|------|
| **Design Twitter** | #355 | 🟠 Medium | Social Graph, Feed System | Large-scale system design | [🔗](https://leetcode.com/problems/design-twitter/) |
| **Design Hit Counter** | #362 | 🟠 Medium | Real-time Metrics, Time Windows | Monitoring and analytics | [🔗](https://leetcode.com/problems/design-hit-counter/) |
| **Serialize and Deserialize Binary Tree** | #297 | 🔴 Hard | Data Serialization | Distributed data formats | [🔗](https://leetcode.com/problems/serialize-and-deserialize-binary-tree/) |
| **Insert Delete GetRandom O(1)** | #380 | 🟠 Medium | Hash Map, Array, Random Access | Database indexing patterns | [🔗](https://leetcode.com/problems/insert-delete-getrandom-o1/) |

### Problem Set Statistics

| Category | Count | Easy | Medium | Hard | Focus Areas |
|----------|-------|------|--------|------|-------------|
| **System Design** | 8 | 0 | 5 | 3 | Caching, APIs, Data Structures |
| **Concurrency** | 4 | 1 | 3 | 0 | Parallelism, Synchronization |
| **Data Engineering** | 6 | 0 | 4 | 2 | SQL, Window Functions, Analytics |
| **Algorithms** | 8 | 0 | 4 | 4 | DP, Graphs, String Processing |
| **Total** | **26** | **1** | **16** | **9** | **Comprehensive Coverage** |

---

## System Design & Engineering

### Mini-Project: High-Performance LRU Cache

**Location**: `src/core/cpp/containers/lru_cache/include/lru_cache.h`

```cpp
#ifndef ALGORITHMIC_ENGINEERING_LRU_CACHE_H
#define ALGORITHMIC_ENGINEERING_LRU_CACHE_H

#include <unordered_map>
#include <list>
#include <mutex>

namespace core {
    
template <typename K, typename V>
class LRUCache {
public:
    explicit LRUCache(size_t capacity);
    
    // Core API
    bool get(const K& key, V& value);
    void put(const K& key, const V& value);
    
    // Observability
    size_t size() const;
    double hit_rate() const;

private:
    void evict();
    
    size_t capacity_;
    std::list<std::pair<K, V>> items_;
    std::unordered_map<K, typename std::list<std::pair<K, V>>::iterator> cache_map_;
    
    std::atomic<size_t> hits_{0};
    std::atomic<size_t> misses_{0};
    mutable std::mutex mutex_;
};

} // namespace core

#endif
```

### System Design: DataCody Agent

**Problem:** Design an intelligent agent ("DataCody") that can profile datasets, suggest quality checks, and recommend suitable ML models.

**Key Discussion Points:**
1.  **Service Architecture:** Microservices vs Monolith. API design (REST/gRPC).
2.  **Data Ingestion & Profiling:** Handling large datasets with Spark for distributed profiling.
3.  **Metadata Storage:** PostgreSQL for structured metadata, Neo4j for data lineage.
4.  **Model Recommendation Engine:** ML service that takes dataset stats and suggests model types.
5.  **Pipeline Integration:** CI/CD pipeline triggers via webhooks.

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


## Progress & Metrics

*   **`progress/solved_log.csv`:** Auto-generated progress tracking
    ```csv
    date,problem_id,title,difficulty,language,time_taken_minutes,notes
    2024-11-26,146,LRU Cache,Hard,C++,45,Implement thread-safe version
    ```
*   **`progress/roadmap_90_days.md`:** Phased learning plan
*   **`progress/retrospective.md`:** Lessons learned and improvements

---

## Getting Started

1.  **Clone and Setup:**
    ```bash
    git clone git@github.com:ArlesZhang/LeetCode-Solutions-Interview-Prep.git
    cd LeetCode-Solutions-Interview-Prep
    ```

2.  **Solve Problems Systematically:**
    ```bash
    # Create solution file
    vim src/solutions/cpp/0001-two-sum.cpp
    
    # Write tests
    vim tests/cpp/test_solutions.cpp
    
    # Update progress
    python scripts/generate_stats.py
    ```

3.  **Run Tests:**
    ```bash
    ./scripts/run_tests.sh cpp
    ./scripts/run_tests.sh python
    ```

4.  **Commit and Push:**
    ```bash
    git add .
    git commit -m "feat: solve PROBLEM_ID with APPROACH"
    git push origin main
    ```

---

<div align="center">

**This is more than a study guide—it's the foundation of your engineering legacy. Build, learn, and iterate.**

</div>



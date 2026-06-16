# Plagiarism Checker in C++

## Overview

This project implements a robust, **two-phase plagiarism detection system** developed in C++. Leveraging core object-oriented programming principles, modern STL containers, and concurrent execution, the tool effectively identifies **global**, **paraphrased**, and **patchwork** plagiarism in both individual pairwise checks and high-volume batch submissions.

---

## Features

- **Two-Phase Verification Engine**:
  - **Phase 1 (Pairwise Matching)**: Compares two code files side-by-side using advanced algorithmic techniques:
    - **Rolling Hash (Rabin-Karp)** for rapid string matching.
    - **Dynamic Programming** to isolate longest common subsequences and matching structural blocks.
    - **2D Segment Trees** to quickly locate overlapping code segments.
  - **Phase 2 (Large-Scale Batch Processing)**: Manages extensive submission groups efficiently via:
    - Parallel execution powered by `std::thread`.
    - Thread-safe data handling controlled through `std::mutex` and `std::condition_variable`.
    - Highly optimized rolling hash checks across the thread pool.

- **Supported Plagiarism Profiles**:
  - **Global**: Full file duplication.
  - **Paraphrased**: Copied structures masked by modified variable names or reordered code blocks.
  - **Patchwork**: Fragmented code combined from multiple disparate sources.

- **Highly Optimized Data Management**:
  - Employs core STL containers—including `unordered_map`, `unordered_set`, and `queue`—to streamline task distribution, token tracking, and match tracking.

---

## Technologies Used

- **Language Standard**: C++17
- **Standard Library Modules**:
  - Containers & Utilities (`vector`, `unordered_map`, `unordered_set`, `queue`)
  - Concurrency Support (`<thread>`, `<mutex>`, `<condition_variable>`)
- **Core Algorithms**:
  - Rolling Hashing
  - Dynamic Programming (DP)
  - 2D Segment Trees

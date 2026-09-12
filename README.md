# FODEMO 

> **FinOps Data Engineering & Memory Optimization Framework**
> A lightweight, zero-dependency Python middleware designed to eliminate duplicate streams, compress sparse matrices, and index temporal logs before reaching cloud warehouses.

---

##  Problem & Overview
Ingesting raw data streams directly into cloud data warehouses (e.g., Snowflake, BigQuery) causes **Cloud Cost Sprawl** due to per-byte scan and ingestion fees. Simultaneously, raw logs crash local analyst hardware due to standard Python memory overhead

**FODEMO** sits locally between incoming log streams and downstream pipelines to drop duplicate records, compress high-dimensional sparse features, and fast-index timestamps in pure Python 3.

---

##  Key Modules & Data Structures

| Module | Data Structure | Functionality | Complexity |
| :--- | :--- | :--- | :--- |
| **Firewall** | Bloom Filter | Bitwise deduplication on byte arrays | $O(1)$ Space |
| **Compressor** | CSR Matrix | Packs sparse 2D arrays into 3 contiguous 1D arrays | >90% RAM reduction |
| **Indexer** | Skip List | Multi-layered linked lists for fast range queries | $O(\log N)$ Time |

---

##  Tech Stack
* **Language:** Pure Python 3
* **Built-in Low-Level Modules:** `array`, `ctypes`, `hashlib`, `sys`
* **Profiling:** `sys.getsizeof`, `psutil`
* **Dependencies:** None (Zero third-party footprint)

---

## Installation & Usage

```bash
# Clone repository
git clone [https://github.com/NetizenRaghav/FODEMO.git](https://github.com/NetizenRaghav/FODEMO.git)
cd FODEMO

# Run pipeline benchmark on 1M synthetic records
python benchmark.py

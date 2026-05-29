# Advanced Integration & RPA Workflows (n8n & Node.js)

This repository features production-ready automation workflows built on n8n. They demonstrate advanced API orchestration, real-time data synchronization, scheduling logic, and complex JavaScript manipulation.

## 🛠️ Core Technical Competencies Demonstrated

* **State & Loop Control:** Advanced iteration utilizing conditional batch loops (`SplitInBatches`) and sequential throttling to prevent API rate-limiting.
* **Data Transformation:** High-performance data mapping, in-memory indexing, lookup-table construction, and array manipulation via custom Node.js execution blocks.
* **Dynamic Date/Time Operations:** Sophisticated temporal scheduling, handling time zone offsets (`America/Sao_Paulo`), custom exception intervals, and dynamic date calculations.
* **Resilient Infrastructure:** Implementations with automated retry strategies, custom error catchers (`continueRegularOutput`), and real-time validation layers.

---

## 📋 Featured Workflows

### 1. Smart Multi-Appointment Aggregator & Messaging Gateway (`agende_API`)

* **Problem Solved:** A clinic system requires automated WhatsApp confirmation, but patients with multiple treatments on the same day were receiving multiple disjointed messages.
* **Technical Implementation:**
    * Implemented an automated cron trigger to crawl and resolve potential professional profiles using dynamic ID sequences.
    * Authored a JavaScript aggregation pipeline that processes appointment arrays in memory, grouping records by the patient's phone number.
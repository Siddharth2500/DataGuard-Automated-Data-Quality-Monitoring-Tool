# 🛡️ DataGuard — Automated Data Quality & Monitoring Tool  
![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg?logo=python&logoColor=white)  
![Data-Quality](https://img.shields.io/badge/Data%20Quality-Checker-FF5252?logo=data:image)  
![Monitoring](https://img.shields.io/badge/Monitoring-Tool-4CAF50?logo=monitor)  
![Reports](https://img.shields.io/badge/Reports-JSON-2196F3?logo=json)  
![CI/CD](https://img.shields.io/badge/CI/CD-Ready-2088FF?logo=githubactions)  
![Dependencies](https://img.shields.io/badge/Dependencies-None-green?logo=python)

**DataGuard** is a **Python 3** tool built to automatically evaluate datasets for key data-quality metrics (missing values, duplicates, outliers) and generate JSON reports — ideal for integrating into your data engineering pipelines.

------

## 🛠 Tech & Languages

| Layer        | Tech / Format                     | Purpose                                        |
|--------------|----------------------------------|------------------------------------------------|
| Language     | **Python 3.10+**                 | Pure standard library                          |
| Data checks  | **Pandas + custom logic**        | Missing, duplicates, outlier checks            |
| Reports      | **JSON**                         | Machine-readable summary                        |
| Execution    | **Stand-alone script / notebook**| Easy integration in Google Colab or CI/CD      |
| Logging      | **Console print + report file**  | Lightweight audit                               |

---

## 🌐 Architecture

Flow:  
1. Load dataset (CSV)  
2. Run checks: missing values, duplicates, outlier ratio  
3. Compare results against thresholds  
4. Produce `quality_report.json` with verdict PASS/FAIL  
5. Print summary for quick human review  

---

## ▶️ Run DataGuard

```bash
python dataguard.py --input data/input_data.csv --output data/quality_report.json
🧪 Example Output:

json
Copy code
{
  "timestamp": "2025-10-19T12:34:56.789Z",
  "missing_value_ratio": 0.10,
  "duplicate_record_ratio": 0.05,
  "outlier_ratio_value": 0.08,
  "status": "PASS"
}
📊 Use Cases:

Embed into Airflow / Prefect pipelines to gate data ingestion based on quality

Automatically monitor live datasets and trigger alerts if quality drops

Use as a lightweight data-quality check step before performing heavy ETL

Design Philosophy

Lightweight: no heavy dependencies

Transparent: human-readable JSON reports

Portable: works in Colab, local scripts or CI/CD environments

Extensible: add new checks easily (schema drift, null patterns, etc.)

🐳 Docker (Optional)

Build:

bash
Copy code
docker build -t dataguard:latest .
Run:

bash
Copy code
docker run --rm -v $(pwd):/data dataguard:latest python dataguard.py --input /data/data/input_data.csv
📄 License
MIT License © 2025


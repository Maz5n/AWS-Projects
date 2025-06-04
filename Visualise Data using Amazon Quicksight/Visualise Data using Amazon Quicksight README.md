---

# 📊  Data Visualization with Amazon QuickSight

In this project, I used **Amazon QuickSight** to visualize sales data by creating **interactive dashboards**, applying **filters**, and generating **reports**. The goal was to analyze regional sales trends and make **data-driven decisions efficiently**.

---

## 🔍 Project Overview

* **Platform:** Amazon QuickSight (Free 30-Day Trial)
* **Data Source:**

  * `netflix_titles.csv` – sample dataset for demonstration
  * `manifest.json` – tells QuickSight how to locate and read the data in S3
* **Storage:** Uploaded to **Amazon S3** bucket
* **Tools Used:**

  * Amazon QuickSight
  * Amazon S3
  * JSON for manifest configuration

---

## 🛠️ Steps Taken

### 1. **Preparing the Dataset**

* Uploaded `netflix_titles.csv` and `manifest.json` to Amazon S3.
* Edited the `manifest.json` file to update the file path to the **correct S3 address**, as the default path was outdated.

Example `manifest.json` snippet:

```json
{
  "fileLocations": [
    {
      "URIs": ["s3://your-bucket-name/netflix_titles.csv"]
    }
  ],
  "globalUploadSettings": {
    "format": "CSV",
    "delimiter": ",",
    "textqualifier": "\"",
    "containsHeader": "true"
  }
}
```

---

### 2. **Connecting Amazon S3 to QuickSight**

* Logged into **Amazon QuickSight Console**
* Selected **Manage Data > New Dataset**
* Chose **Amazon S3** as the data source
* Uploaded and configured the dataset using the `manifest.json` file


---

### 3. **Building the Dashboard**

* Used QuickSight's **drag-and-drop interface** to:

  * Import fields like region, sales, and product category
  * Choose appropriate visual types (e.g., bar charts, pie charts, line graphs)
  * Apply filters and sorting to analyze specific regional trends



---

### 4. **Exporting the Report**

* Exported the final dashboard and **downloaded it as a PDF report**
* Suitable for sharing with stakeholders or embedding in presentations

---

## 🎯 Project Outcome

* Successfully visualized sales performance across regions
* Improved decision-making with visual trend insights
* Gained hands-on experience with:

  * **Amazon QuickSight**
  * **S3 integration**
  * **Data mapping via manifest files**
  * **Interactive dashboard creation**

---



---


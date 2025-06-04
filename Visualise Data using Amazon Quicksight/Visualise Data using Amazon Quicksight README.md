---

# 📊 Sales Data Visualization with Amazon QuickSight

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

> *The manifest file acts like a map that tells QuickSight where the data lives and how to read it.*

---

### 3. **Building the Dashboard**

* Used QuickSight's **drag-and-drop interface** to:

  * Import fields like region, sales, and product category
  * Choose appropriate visual types (e.g., bar charts, pie charts, line graphs)
  * Apply filters and sorting to analyze specific regional trends

### 4. **Sales by Region Graph**

* Created a **bar chart** displaying **total sales by region**
* This helped visualize:

  * High-performing regions
  * Regional trends and anomalies
  * Strategic areas for growth

> *All chart titles were customized for clarity and presentation.*

---

### 5. **Exporting the Report**

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

## 📷 Screenshots (Optional)

> *(Include screenshots of your dashboard and exported PDF if available)*

---

## 📚 Resources

* [Amazon QuickSight Documentation](https://docs.aws.amazon.com/quicksight/)
* [Create and Use a Manifest File](https://docs.aws.amazon.com/quicksight/latest/user/supported-manifest-file-format.html)

---

Let me know if you'd like help creating a **sample `manifest.json`**, **QuickSight permissions policy**, or visual **dashboard layout template**.

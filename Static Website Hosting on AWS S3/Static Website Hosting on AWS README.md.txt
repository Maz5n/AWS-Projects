# 🌐 Static Website Hosting on AWS S3

In this project, I hosted a static website using **Amazon S3** by uploading basic HTML files and enabling **public access** with **ACLs (Access Control Lists)**. This involved configuring bucket settings, resolving access issues, and successfully launching the website.

---

## 🔧 Steps Taken

### 1. **Created an S3 Bucket**

* Named the bucket and selected the region: **Europe (London)**.
* Bucket creation took only a couple of minutes.

### 2. **Uploaded Website Files**

* Uploaded two files:

  * `index.html` – homepage
  * `Nextwork` – an additional page or asset

### 3. **Enabled Static Website Hosting**

* Navigated to the **Properties** tab in the S3 console
* Enabled **Static website hosting**
* Set:

  * **Index document:** `index.html`

### 4. **Made the Bucket Public Using ACL**

* Initially, the website showed a **403 Forbidden error** because the bucket was private.
* To resolve this, I:

  * Enabled **ACLs** (Access Control Lists)
  * Gave **public read access** to the files by adjusting object-level permissions

### 5. **Tested the Website**

* Clicked the **S3 static website endpoint URL**
* Confirmed the site was now publicly accessible and rendering correctly

---

## 🚀 Project Outcome

* Successfully deployed a basic static website on AWS
* Resolved public access issues by enabling and configuring ACLs
* Gained hands-on experience with:

  * S3 bucket configuration
  * Website hosting using AWS
  * Permissions and access troubleshooting

-
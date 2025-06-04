# 📧 Send Email Using Amazon SES via AWS Console

This project demonstrates how to send an email using **Amazon Simple Email Service (SES)** **entirely through the AWS Console**, without any programming or command-line tools. SES is a cloud-based email sending service designed to help you send marketing, notification, and transactional emails.

---

## 🛠️ Services Used

| Service         | Purpose                          |
| --------------- | -------------------------------- |
| **Amazon SES**  | To send and manage emails        |
| **AWS Console** | Used to configure and send email |

---

## ✅ Step-by-Step Tutorial

### 1. **Login to AWS Console**

* Go to [https://console.aws.amazon.com/](https://console.aws.amazon.com/)
* Search for **Amazon SES** and open the SES dashboard

---

### 2. **Select Your Region**

SES is region-specific. Choose a region where **SES is supported**, e.g., `US East (N. Virginia)` or `EU (Ireland)`.

---

### 3. **Verify an Email Address**

Before sending emails, SES must verify that you own the "From" email address.

* Navigate to: **SES > Verified Identities**
* Click **"Create identity"**
* Choose **Email address** and enter your email (e.g., `yourname@example.com`)
* Click **Create identity**
* Check your email inbox and **click the verification link** sent by AWS

✅ Your email will now appear as **"Verified"**

---

### 4. **Send a Test Email**

* In the SES Console, go to **"Mailbox simulator"** or **"Send test email"**
* Choose:

  * **From:** the email you just verified
  * **To:** any email (you can test with your own or use the simulator)
  * **Subject:** e.g., `Hello from Amazon SES!`
  * **Body:** your message
* Click **Send email**

✅ Your test email will be delivered (check spam/junk folder if not visible)

---

### 5. **(Optional) Move Out of Sandbox Mode**

By default, SES operates in **sandbox mode**, which restricts you to:

* Verified sender and recipient addresses
* Low sending limits

To request **production access**:

* Go to **SES > Account dashboard**
* Click **“Request production access”**
* Fill out the form with use-case details

---



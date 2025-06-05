# 📬 Asynchronous Messaging with Amazon SQS

This project demonstrates how to use **Amazon Simple Queue Service (SQS)** to set up **asynchronous messaging** between application components.
Using the **AWS Console**, I created and managed a message queue, demonstrating how messages can be sent, received, and deleted in a decoupled system.

---

## 📦 Service Used

| AWS Service     | Purpose                                                   |
| --------------- | --------------------------------------------------------- |
| **Amazon SQS**  | Cloud-based message queuing for decoupling app components |
| **AWS Console** | Used to perform all steps via UI                          |

---

## ✅ What You Will Learn

* How to create an Amazon SQS **queue**
* How to **send** a message to the queue
* How to **receive and delete** the message
* How to **delete the queue** after use

---

## 🛠️ Step-by-Step Guide

### 🔹 Step 1: Sign in to AWS Console

* Go to [https://console.aws.amazon.com/](https://console.aws.amazon.com/)
* Search for **Amazon SQS** in the Services menu

---

### 🔹 Step 2: Create a New Queue

1. Click **"Create Queue"**
2. Choose **Standard Queue** (for maximum throughput)
3. Enter a **Queue Name** (e.g., `MyTestQueue`)
4. Keep all default settings, or:

   * Enable **access policy** for easier testing
5. Click **"Create Queue"**

✅ Your SQS queue is now created.

---

### 🔹 Step 3: Send a Message

1. Open your newly created queue
2. Click on the **“Send and receive messages”** tab
3. Under **Message body**, type your test message (e.g., `"Hello from SQS!"`)
4. Click **"Send message"**

✅ The message has been successfully added to the queue.

---

### 🔹 Step 4: Receive and Delete the Message

1. Under the same tab, click **"Poll for messages"**
2. Your sent message should appear in the list
3. Click **“Message Actions” > “Delete”** to remove the message from the queue

✅ You have now received and deleted a message from the queue.

---

### 🔹 Step 5: Delete the Queue

1. Return to the **Queue list**
2. Select your queue
3. Click **"Delete"**
4. Confirm deletion

✅ The queue has been successfully removed from your AWS environment.

---

## 🎯 Why Use Amazon SQS?

* Decouple microservices or application components
* Improve system resilience and fault tolerance
* Queue messages for background processing
* Handle high traffic gracefully


---


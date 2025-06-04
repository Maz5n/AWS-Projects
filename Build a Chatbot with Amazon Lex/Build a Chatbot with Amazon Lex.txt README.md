
##Creating Banker Bot with Amazon Lex

# 💬 Banker Bot – A Smart Banking Chatbot using Amazon Lex

Banker Bot is a chatbot built using **Amazon Lex** that simulates basic banking operations for an imaginary bank. It can greet users, help them check their **account balances**, and **transfer funds** between accounts. The chatbot also handles unknown inputs with fallback responses, ensuring a natural user experience.

## 📌 Features

* ✅ **Greeting users**
* 💰 **Checking account balances**
* 🔁 **Transferring money between accounts**
* ❓ **Error handling** for unknown or unclear inputs
* 🔒 **IAM role configured** with least privilege for secure access

## 🛠️ Tech Stack

* **Amazon Lex**
* **AWS IAM** (for secure permission control)
* **AWS Lambda (optional)** – for backend logic (e.g., retrieving balance or simulating transfers)


In this project, I built a practical chatbot called Banker Bot using Amazon Lex to assist customers of an imaginary bank. Banker Bot can greet users,   help them check their account balance, and transfer money between accounts. It also handles unexpected inputs by returning error messages when it doesn't understand the user's intent.

I created Banker Bot from scratch on the Amazon Lex console. The setup took around 7 minutes. During the process, I also created an IAM role with basic permissions, following the principle of least privilege to minimize security risks. This ensures that the bot only has the access it needs to perform its tasks securely.

#To detect intent , I used the default confidence threshold of 0.40, which helps the bot decide when to trigger fallback responses if user input is unclear. This setup allows Banker Bot to respond in a steady and natural tone, improving the user experience.

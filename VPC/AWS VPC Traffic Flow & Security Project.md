# **AWS VPC Traffic Flow & Security Project**  
### *Understanding How Traffic Moves Through Your VPC*  

---

## **📌 Project Overview**  
This project demonstrates how a user's HTTP request flows through an **Amazon Virtual Private Cloud (VPC)** while interacting with key AWS networking components. It covers:  
- **VPC (Virtual Private Cloud)** – Your isolated network in AWS.  
- **Internet Gateway (IGW)** – Allows public internet traffic into the VPC.  
- **Public Subnet** – Hosts resources with public internet access.  
- **Route Tables** – Directs traffic between subnets and gateways.  
- **Network ACLs (NACLs)** – Stateless firewall rules at the subnet level.  
- **Security Groups** – Stateful firewall rules at the instance level.  
  

---

## **🔧 AWS Resources Created**  
1. **VPC** (`NextWork VPC`) – The virtual network where all resources reside.  
2. **Internet Gateway** (`NextWork IG`) – Connects the VPC to the internet.  
3. **Public Subnet** (`Public 1`) – A subnet with a route to the internet gateway.  
4. **Route Table** (`NextWork Route Table`) – Routes traffic between subnets and the internet.  
5. **Network ACL** – Controls inbound/outbound traffic at the subnet level.  
6. **Security Group** (`NextWork Security Group`) – Controls traffic to the EC2 instance.  


---

## **📡 Traffic Flow (User → Website)**  

### **1️⃣ User Sends a Request**  
- A user enters your website URL (`http://example.com`) in their browser.  
- The request travels over the internet to your **Internet Gateway (NextWork IG)**.  

### **2️⃣ Internet Gateway → VPC**  
- The **IGW** forwards the request to your **VPC (NextWork VPC)**.  

### **3️⃣ Route Table Directs Traffic**  
- The **route table (`NextWork Route Table`)** checks where to send the request.  
- Since the destination is an EC2 instance in the same VPC, it uses the **local route**.  

### **4️⃣ Network ACL (Subnet-Level Firewall)**  
- The request reaches the **public subnet (`Public 1`)**.  
- The **Network ACL** checks inbound rules:  
  - ✅ **Rule 100**: Allows `0.0.0.0/0` (all traffic).  
  - The request is permitted.  

### **5️⃣ Security Group (Instance-Level Firewall)**  
- The request reaches the **EC2 instance**.  
- The **Security Group (`NextWork Security Group`)** checks:  
  - ✅ **Inbound Rule**: Allows `HTTP (Port 80)` from `0.0.0.0/0`.  
  - The request is accepted.  

### **7️⃣ Response Sent Back to User**  
- The response follows the reverse path:  
  - **EC2 → Security Group (outbound allowed) → Subnet → Network ACL (outbound rule) → Route Table → IGW → Internet → User’s Browser**  
- The user sees the website load successfully!  

---

## **🔒 Key Security Concepts**  
| **Component**       | **Type**      | **Stateful?** | **Scope**          | **Example Rule**                     |  
|---------------------|--------------|--------------|--------------------|--------------------------------------|  
| **Security Group**  | Allow-only   | ✅ Yes       | Instance-level     | Allow HTTP (Port 80) from 0.0.0.0/0  |  
| **Network ACL**     | Allow/Deny   | ❌ No        | Subnet-level       | Allow Inbound 0.0.0.0/0 (Rule 100)  |  

- **Security Groups** are **stateful**: If a request is allowed in, the response is automatically allowed out.  
- **Network ACLs** are **stateless**: You must explicitly allow inbound *and* outbound traffic.  

---

## **🚀 Next Steps**  
To enhance this setup, consider:  
- Adding a **private subnet** for backend services (e.g., databases).  
- Implementing a **NAT Gateway** for private instances needing internet access.  
- Setting up **VPC Flow Logs** to monitor traffic.  
- Using **HTTPS (Port 443)** for secure communication.  

---

## **🎯 Conclusion**  
This project illustrates how AWS networking components work together to securely deliver web content. By understanding **VPCs, subnets, route tables, NACLs, and security groups**, you can design robust and secure cloud architectures.  

 

---  


---

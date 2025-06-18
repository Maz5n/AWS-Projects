# **AWS VPC **  

## **🌐 Overview**  
This project builds a **secure, multi-tier VPC** with:  
- **Public Subnet**: Hosts internet-facing resources (e.g., web servers).  
- **Private Subnet**: Isolates backend services (e.g., databases).  
- **Layered Security**: Uses **Security Groups (stateful)** and **NACLs (stateless)**.  

---

## **🔧 Key Components**  
| **Resource**          | **Purpose**                                                                 |
|-----------------------|----------------------------------------------------------------------------|
| **VPC** (`10.0.0.0/16`) | Isolated network for all AWS resources.                                   |
| **Internet Gateway (IGW)** | Enables public internet access for the **Public Subnet**.                 |
| **Public Subnet** (`10.0.1.0/24`) | Hosts EC2 instances with **direct internet access** via IGW.             |
| **Private Subnet** (`10.0.2.0/24`) | No internet access; secure backend (e.g., RDS, internal apps).           |
| **Route Tables**       | - **Public**: Routes `0.0.0.0/0` to IGW. <br> - **Private**: Local-only. |
| **Security Groups**    | - **Web-SG**: Allows HTTP (80) from anywhere. <br> - **Backend-SG**: Restricts SSH to Public Subnet. |
| **Network ACLs**       | Subnet-level firewall (e.g., allow HTTP inbound to Public Subnet).        |

---

## **🚦 Traffic Flow**  
### **Public Subnet (User → Web Server)**  
1. User → **IGW** → **Public Subnet** → **Web-SG** → **EC2 (HTTP Response)**.  

### **Private Subnet (Web Server → Database)**  
1. Web Server → **Private Subnet** → **Backend-SG** → **Database**.  

> 🔐 **Security Note**:  
> - Private subnet **blocks all internet traffic** by default.  
> - Use **NAT Gateway** (future upgrade) for private instances needing updates.  

---

## **🔒 Security Layers**  
| **Layer**              | **Public Subnet**       | **Private Subnet**       |
|------------------------|------------------------|-------------------------|
| **Security Group**     | Allow HTTP (80)        | Allow SSH from Public   |
| **Network ACL**        | Allow HTTP inbound     | Block all external traffic |

---

## **📌 Key Takeaways**  
✔ **Public/Private Subnets** segregate frontend/backend traffic.  
✔ **Security Groups** protect instances (stateful).  
✔ **NACLs** add subnet-wide rules (stateless).  
✔ **Private subnets** = no direct internet = more secure.  

**Next Steps?** Consider adding **NAT Gateway, VPC Peering, or VPN**.  

---  

AWS Cloud Quest: Scalable & Fault-Tolerant EC2 Web Server

📌 Project Overview
This project documents the deployment of a secure, highly available web server using Amazon Elastic Compute Cloud (EC2), completed as part of the **AWS Cloud Quest** hands-on lab. The deployment covers initial instance provisioning, cost management considerations, integrated security services, and multi-Availability Zone (AZ) architecture for fault tolerance.

---

🛠️ Step-by-Step Implementation

1. Regional Cost Awareness & AMI Selection
AWS infrastructure pricing varies significantly by region. For this deployment, the **[Insert Your Region, e.g., us-east-1]** region was selected to optimize performance and budget boundaries.

* **Amazon Machine Image (AMI) Selection:** I utilized a pre-configured AMI to standardize the OS environment. This functions as a reusable blueprint, accelerating deployments and ensuring environment consistency.

*AMI Configuration Profile:*
![AMI Selection](images/1b-ami-selection.png)

2. Computing Architecture (Instance Type Selection)
To align with the application workload requirements, I evaluated virtual hardware specs using the EC2 instance advisory guidance to avoid over-provisioning resource capacity.

*Hardware Tier Matrix:*
![Instance Advisory Advice](images/1c-instance-type.png)

3. Integrated Security & Monitoring Configurations
During configuration, I leveraged standalone, native AWS services tightly embedded within the EC2 console dashboard:
* **Network Access Control:** Structured inbound security group rules to safely expose HTTP/HTTPS traffic.
* **Storage Allocation:** Configured root Elastic Block Store (EBS) volumes with encryption properties.
* **Observability:** Enabled monitoring metrics to track instance performance.

 *EC2 UI Integrations:*
![Integrated Services Management](images/1d-integrated-services.png)

---

🚀 Deployment Results

Instance Initialization Proof
The configuration compiled successfully, and the virtual hardware passed initial AWS health checks.

🖼️ *AWS Status Validation:*
![Instance Lifecycle Creation](images/1e-instance-created.png)

### Live Web Server Validation
The Apache/Nginx web server was initialized via user data scripts and successfully served dynamic web traffic over the public internet.

🖼️ *Live Endpoint Verification:*
![Running Public Web Server](images/1f-webserver-running.png)

---

🔄 High Availability & Fault Tolerance (1G & 1H)
To prevent a single point of failure (SPOF) if an entire AWS data center goes offline, I cloned the configuration pattern:
1. Captured the active architecture configuration properties.
2. Launched a **second identical EC2 instance** into a **different Availability Zone (AZ)**.
3. This creates a multi-AZ architecture layer, ensuring our application remains online even if one zone experiences an outage.

*Fault Tolerant Multi-AZ Infrastructure:*
![Multi-AZ Redundancy Layout](images/1g-multi-az-replica.png)

Scalable & Fault-Tolerant EC2 Web Server

📌 Project Overview
This project documents the deployment of a secure, highly available web server using Amazon Elastic Compute Cloud (EC2). The deployment covers initial instance provisioning, cost management considerations, integrated security services, and multi-Availability Zone (AZ) architecture for fault tolerance.

---

🛠️ Step-by-Step Implementation

* Regional Cost Awareness & AMI Selection
AWS infrastructure pricing varies significantly by region.

1. AWS Region & EC2 Instance Launch

Before deployment, I considered the selected AWS Region, as resource availability and pricing can vary by Region. I then accessed the Amazon EC2 console and initiated the instance launch process.

![Accessing EC2](./images/1a.png)

2. Operating System & Environment Selection

I selected an Amazon Machine Image (AMI) as the foundational template for the EC2 instance. The AMI provides the operating system and preconfigured software environment required for deployment.

![Accessing EC2](./images/1b.png)

3. Computing Architecture — Instance Type Selection

To align the virtual hardware configuration with the application workload, I evaluated available EC2 instance types using AWS advisory guidance to avoid unnecessary resource allocation.

![Accessing EC2](./images/1c.png)

4. Post-Launch Deployment Verification
The EC2 compute instance was successfully initialized and provisioned. To ensure production-grade reliability, the next phase focuses on infrastructure hardening and day-2 operations:

* Resource Governance:** Establishing baseline CloudWatch billing and resource metric monitors.
* High Availability Architecture:** Preparing the network interface to receive traffic from an Elastic Load Balancer (ELB).
* Data Resilience:** Implementing automated Amazon EBS snapshot policies for point-in-time disaster recovery.


![Accessing EC2](./images/1d.png)


5. EC2 Instance Deployment

The configuration was successfully completed and the EC2 instance was launched and transitioned to a running state.

![Accessing EC2](./images/1e.png)

4. EC2 Configuration
Configured the EC2 instance using AWS services and features available within the EC2 console.
5. Instance Created
Successfully launched and created the EC2 instance.
6. Web Server Running
Successfully configured and launched a web server on the EC2 instance.
7. Horizontal scaling -  Adding an EC2 Instance
Launched an additional EC2 instance using the existing AMI.
8.Fault Tolerance
Deployed the additional instance in another Availability Zone to improve fault tolerance.

* **Amazon Machine Image (AMI) Selection:** I utilized a pre-configured AMI to standardize the OS environment. This functions as a reusable blueprint, accelerating deployments and ensuring environment consistency.

*AMI Configuration Profile:*
![AMI Selection Screen](./images/1a.png)

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

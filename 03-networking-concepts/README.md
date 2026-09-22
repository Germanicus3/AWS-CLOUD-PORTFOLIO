
 Project 3 — AWS Networking: VPC Connectivity & Traffic Control

 Project Overview

This project demonstrates the configuration of **AWS VPC networking and traffic controls** to establish secure connectivity between web, subnet, and database resources. The implementation covers route tables, Internet Gateway connectivity, security groups, and controlled communication between application and database tiers.


Implementation

1. Amazon VPC Configuration

Accessed the **Amazon VPC console** from the EC2 environment to examine and manage the networking components supporting the deployed instances.

![Opening VPC Console](images/3a.png)

2. Route Table Analysis

Inspected the associated **VPC route table** to evaluate how traffic was being directed between the subnet, the Internet, and other network destinations.

![Checking Route Table](./images/3b.png)

3. Subnet Internet Connectivity

Configured the required routing to enable resources within the subnet to communicate with the **Internet Gateway**, establishing outbound Internet connectivity.

![Subnet Internet Connectivity](./images/3c.png)

4. Instance-Level Inbound Traffic Control

Configured the instance's **security group inbound rules** to control incoming network traffic and permit the required connections to the web server.

![Instance Inbound Traffic](./images/3e.png)

5. Inter-Subnet & Network Connectivity

Reviewed the VPC routing configuration required for the subnet to communicate with **other subnets and networks**, demonstrating how route tables control traffic between network destinations.

![Subnet Network Connectivity](./images/3f.png)

6. Database Security Group — Inbound Access

Configured an inbound rule in the **database security group** to allow the database to receive authorized traffic from the web server, establishing controlled application-to-database connectivity.
<p align="center">
    <img src="images/3 issue fixed.png" width="48%" alt="Issue Fixed" />
    <img src="images/3issue pic.png" width="48%" alt="Issue Picture" />
    </p>


![Database Security Group](./images/3issue pic.png)



🏁 Project Summary & Technical Takeaways

This project demonstrates the configuration and management of **AWS VPC networking and traffic controls**, including route tables, subnet connectivity, Internet Gateway routing, security groups, and controlled communication between application and database resources.

🛠️ Core Competencies Demonstrated

* VPC Networking:** Configured and evaluated AWS networking components supporting EC2 workloads.
* Traffic Routing:** Used route tables to control traffic between subnets, networks, and the Internet.
* Network Security:** Applied security group rules to control inbound traffic at the resource level.
* Application-to-Database Connectivity:** Configured controlled communication between web and database resources.
* Cloud Network Architecture:** Demonstrated practical understanding of how VPCs, subnets, route tables, Internet Gateways, and security groups operate together.


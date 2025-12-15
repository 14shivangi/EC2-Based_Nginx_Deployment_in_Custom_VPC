
## 🏗️ Infrastructure Overview

The infrastructure created by this project includes:

- A **custom VPC**
- One **Public Subnet**
- One **Private Subnet**
- An **Internet Gateway (IGW)**
- Separate **Route Tables** for public and private subnets
- A **Security Group** allowing **HTTP (80)** and **SSH (22)**
- An **EC2 instance** with **NGINX installed automatically** using **User Data**

👉 The **EC2 instance** is launched inside the **public subnet**, making the **NGINX web server accessible over the internet**.

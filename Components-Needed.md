
# -  Components Explained

### 1. Provider Configuration (`main.tf`)
- Uses the **AWS provider**
- Region set to **ap-south-1 (Mumbai)**

---

### 2️. VPC and Networking (`vpc.tf`)
- Creates a **VPC** with CIDR block `10.0.0.0/16`
- **Public Subnet:** `10.0.2.0/24`
- **Private Subnet:** `10.0.1.0/24`
- **Internet Gateway (IGW)** attached to the VPC
- **Public Route Table** routes `0.0.0.0/0` traffic to the IGW
- **Public Subnet** associated with the public route table
- **Private Subnet** associated with a private route table (no internet access)

---

### 3️. Security Group (`security-grp.tf`)
Allows the following:
- **HTTP (Port 80)** from anywhere
- **SSH (Port 22)** from anywhere *(can be restricted to your IP)*
- **All outbound traffic**

-> This security group is attached to the **EC2 instance**.

---

### 4️. EC2 Instance with NGINX (`ec2.tf`)
- EC2 instance type: **t2.micro**
- AMI: **Amazon Linux (ap-south-1)**
- Launched in the **public subnet**
- Automatically installs and starts **NGINX** using `user_data`
- Assigned a **public IP address**

---

### 5️. Outputs (`output.tf`)
Displays:
- **EC2 public IP address**
- **NGINX access URL** (`http://<public-ip>`)

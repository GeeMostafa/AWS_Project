🎯 Objective:
To build a secure, scalable, and cost-effective infrastructure for a dynamic web application using Amazon EC2, VPC, and Amazon RDS.

🧱 Architecture Components Used:

1. Amazon VPC (Virtual Private Cloud)

Created a custom VPC with two subnets: Public Subnet: For EC2 instances and Load Balancer
Private Subnet: For Amazon RDS
Setup:
Internet Gateway (IGW) for outbound internet access
NAT Gateway to allow private subnet instances to access the internet
Route Tables to control traffic flow

2. Amazon EC2
Launched Linux EC2 instances in the public subnet
Installed a sample web application (e.g., PHP + Apache or NGINX)
Enabled Auto Scaling for handling variable load
Used Elastic Load Balancer to distribute incoming traffic

3. Amazon RDS (MySQL)
Deployed RDS in a private subnet for security
Enabled:
Multi-AZ deployment for high availability
Automatic Backups
Encryption at rest and in transit
Connected the EC2 web application to RDS securely

4. Security Groups & NACLs
Configured security groups to allow:
HTTP/HTTPS access from the internet to EC2
MySQL access only from EC2 to RDS (port 3306)
Configured NACLs for additional network-level control

⚙️ Step-by-Step Deployment Process:

1. Create the VPC and Subnets
Use the VPC Wizard or custom configuration
Allocate public and private subnets in at least two Availability Zones

2. Set Up Internet and NAT Gateways
Attach an Internet Gateway to the VPC
Launch a NAT Gateway in the public subnet for private subnet internet access

3. Launch EC2 Instances
Choose an Amazon Linux AMI or Ubuntu
Place it in a public subnet with appropriate security groups
Install and configure the web server & app

4. Set Up Amazon RDS
Choose MySQL/PostgreSQL
Deploy in a private subnet
Set the database endpoint in the web application config file

5. Configure Load Balancer and Auto Scaling
Create an Application Load Balancer (ALB)
Register EC2 instances
Set up Auto Scaling Groups with scaling policies

📈 Project Benefits:
✅ Scalable: Handles varying loads with Auto Scaling
✅ Highly Available: Multi-AZ deployment ensures minimal downtime
✅ Secure: RDS in a private subnet, controlled access via security groups
✅ Cost-Efficient: Pay only for what you use

# AWS Auto Scaling Group with Application Load Balancer (ALB)

This project demonstrates how to deploy a highly available and scalable web application architecture on AWS using an **Auto Scaling Group (ASG)** integrated with an **Application Load Balancer (ALB)**.

## 📌 Overview

The architecture ensures:
- Automatic scaling of EC2 instances based on CPU utilization.
- Load-balanced HTTP traffic across multiple Availability Zones.
- High availability, fault tolerance, and elasticity.


## 🔧 Components Used

- **Amazon EC2**: Virtual servers in Auto Scaling Group.
- **Auto Scaling Group (ASG)**: Manages EC2 instances automatically.
- **Application Load Balancer (ALB)**: Distributes incoming traffic across instances.
- **Target Group**: Registers healthy EC2 instances behind the ALB.
- **Amazon CloudWatch**: Monitors metrics and triggers scaling actions.
- **Launch Template**: Defines EC2 instance configuration.

## 🌐 VPC Configuration

- **VPC CIDR**: `10.0.0.0/16`
- **Public Subnets**: `10.0.1.0/24` (AZ1), `10.0.3.0/24` (AZ2)

## 🛠️ Implementation Steps

1. **Create Launch Template**
   - Define AMI, instance type, key pair, security group, and user data script (e.g., simple web server).

2. **Set Up Target Group**
   - Protocol: HTTP  
   - Port: 80  
   - Target type: Instance

3. **Deploy Application Load Balancer**
   - Internet-facing  
   - Listener: HTTP (Port 80)  
   - Forward traffic to the target group

4. **Configure Auto Scaling Group**
   - Attach the launch template  
   - Distribute instances across at least 2 Availability Zones  
   - Link to the previously created target group  
   - Enable health checks  
   - Add scaling policies

5. **Test Scaling Behavior**
   - Simulate CPU load using SSH and stress testing tools  
   - Observe EC2 instances scaling up/down  
   - Verify traffic routing via the ALB DNS name

## ✅ Results

- Incoming traffic was successfully routed through the ALB to EC2 instances across multiple AZs.
- CloudWatch metrics triggered scale-out and scale-in operations as expected.
- The application remained available and responsive during scaling events.


## 🧠 Skills Demonstrated

- AWS Auto Scaling  
- Application Load Balancer (ALB)  
- EC2 & Target Groups  
- CloudWatch Alarms  
- High Availability & Scalability

---

## 👨‍💻 Author

**Mohaned Mohamed**  
Glasgow, United Kingdom  
📧 m.gorashi282@gmail.com | 📞 +447417414418  
🔗 [LinkedIn Profile](https://www.linkedin.com/in/mohaned-mohamed-64674a45/)  
💻 [GitHub Profile](https://github.com/Mohaned282)

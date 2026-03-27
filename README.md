#  Hybrid Infrastructure Monitoring using AWS CloudWatch

Implemented hybrid monitoring by integrating an on-prem VM with AWS CloudWatch using CloudWatch Agent. Created dashboards and alarms, enabling centralized visibility and real-time alerts via SNS for both cloud and on-prem infrastructure.

---

##  Project Overview

This project demonstrates a **Hybrid Monitoring Architecture** where an on-premise server (VM) is integrated with AWS CloudWatch for centralized monitoring and alerting.

The system collects metrics from:

*  AWS EC2 instance
*  On-Premise VM

and displays them in a **single CloudWatch dashboard** with alerting via SNS.

---

##  Architecture


On-Prem VM → CloudWatch Agent → AWS CloudWatch
↓
EC2 Instance → CloudWatch Metrics → Dashboard + Alarm → SNS Email Alert


<img width="864" height="510" alt="architechture" src="https://github.com/user-attachments/assets/767033ec-ddd6-4e47-817c-ff6c5f76b68d" />


---

##  Technologies Used

* AWS CloudWatch
* AWS EC2
* AWS SNS
* IAM
* Ubuntu (VM)
* CloudWatch Agent

---

##  Project Setup Steps

###  1. On-Prem VM Setup

* Created Ubuntu VM using VirtualBox
* Installed CloudWatch Agent

![VM Setup](img/vm-installation.png)
![VM Setup 2](img/vm-cw-agent.png)

---

###  2. EC2 Instance Setup

* Launched EC2 instance (Ubuntu)
* Attached IAM Role with CloudWatch permissions

![EC2 Setup](img/ec2-1.png)
![EC2 Setup 2](img/ec2-2.png)

---

###  3. CloudWatch Agent Configuration

* Configured agent on both EC2 and VM
* Collected metrics:
  * CPU
  * Memory
  * Disk

![Config File](img/config.png)


---

###  4. Agent Running Verification

* Started CloudWatch agent
* Verified service status

![Agent Running](img/cw-agent-active.png)

---

###  5. Metrics Verification

* Verified metrics in CloudWatch
* EC2 metrics → CPUUtilization
* VM metrics → mem_used_percent

![Metrics](img/hybrid-monitoring-dashboard-%20details.png)

---

###  6. Dashboard Creation

* Created CloudWatch Dashboard:
  * EC2 CPU
  * VM Memory
  * VM Disk

![Dashboard](img/cw-dashboard.png)

---

###  7. SNS Notification Setup

* Created SNS Topic
* Subscribed email for alerts

![SNS Setup](img/sns-topic-details.png)
![SNS Setup 2](img/sns-confirmation.jpeg)

---

###  8. Alarm Configuration

* Created alarm:
  * EC2 CPU > 70%
  * VM Memory > 70%

![Alarm Setup](img/sns-create.png)

---

###  9. Testing (Stress Load)

* Generated load using stress command
* Verified:
  * Metric spike
  * Alarm triggered
  * Email received

![Stress Test](img/cpu-alert.png)
![Stress Test 2](img/cpu-alert.jpeg)

---

##  Final Outcome

* Centralized monitoring of hybrid infrastructure
* Real-time metric visualization
* Automated alerting system
* Successfully validated monitoring using stress testing

---

##  Key Learnings

* Hybrid cloud monitoring architecture
* CloudWatch Agent configuration
* Custom metrics collection
* Dashboard and alert setup
* Troubleshooting real-world issues

---

##  Conclusion

This project successfully demonstrates how to integrate on-premise infrastructure with AWS monitoring services to achieve centralized visibility and proactive alerting.

---

##  Author

**Megha Patil**

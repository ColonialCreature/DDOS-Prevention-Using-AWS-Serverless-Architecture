# 🛡️ DDoS Prevention System using AWS Serverless Architecture

A cloud-native defense system against frequency-based DDoS attacks using AWS Lambda, API Gateway, DynamoDB, CloudWatch, and SNS. This project leverages a **serverless architecture** to detect and mitigate malicious HTTP request patterns in real-time, ensuring uptime and security for web services.

---

## 📘 Project Overview

- 📡 Prevents DDoS attacks by tracking HTTP request frequency
- 🧠 Uses three AWS Lambda functions: `Filter Lambda`, `Connection Lambda`, and `Alarm Lambda`
- 📊 Dynamically monitors traffic using CloudWatch alarms
- ⚠️ Blocks malicious IPs and sends alerts via AWS SNS
- ☁️ Fully serverless → auto-scalable, cost-effective, and low-maintenance

---

## 💡 Key Features

- AWS API Gateway for secure request entry
- Filter and Connection Lambdas for traffic handling
- Raw and Denial List tables in DynamoDB to track and blacklist requests
- CloudWatch monitoring and Alarm Lambda for detecting high-frequency patterns
- Email alerts for administrators via AWS SNS

---

## 🧰 Tech Stack

| Tool | Description |
|------|-------------|
| Python (Boto3, JSON) | Backend logic and AWS SDK integration |
| AWS Lambda | Serverless compute for filtering and detection |
| AWS DynamoDB | NoSQL storage for request logs and denial list |
| AWS API Gateway | Entry point for all HTTP requests |
| AWS CloudWatch | Monitoring and alarm triggering |
| AWS SNS | Sends email alerts to admins |
| AWS CloudFormation | Infrastructure as code (optional) |

---

## 🧪 System Workflow

1. **Normal Traffic**  
   - Requests flow through API Gateway → Filter Lambda → Connection Lambda → Web Server  
   - Request logs are stored in DynamoDB's Raw Table

2. **Suspicious/Attacker Traffic**  
   - High-frequency requests trigger CloudWatch alarm  
   - Alarm Lambda scans Raw Table, identifies IPs  
   - Malicious IPs added to Denial List → blocked on next request  
   - Admins are notified via email using SNS

---

## 🧩 Challenges Faced

- Handling Lambda cold starts during sudden traffic
- Avoiding false positives while filtering legitimate traffic
- Designing an efficient and non-intrusive alert system
- Maintaining performance while keeping AWS cost low

---

## 📄 Research Publication

This project is documented in the following research paper:

**"DDoS Prevention System using AWS Serverless Architecture"**  
_Aryan Deshmukh, Anamay Brahme, Asad Vathare, Chanakya Patil_  
Published: November 2023, Vishwakarma University, Pune

📖 [Read the full paper](https://doi.org/10.36948/ijfmr.2023.v05i06.9563)

---

## 🔭 Future Scope

- ✅ **Approval List**: Allow whitelisted users to bypass the denial mechanism
- ✅ **Advanced Filtering**: Use request metadata like paths/parameters for more precise detection
- 🔄 **AWS WAF / Shield Integration** for multi-layered protection

---

## 👤 Authors

**Aryan Deshmukh** | [LinkedIn](https://www.linkedin.com/in/aryan-deshmukh-0531321b6) | [GitHub](https://github.com/ColonialCreature)  
**Chanakya Patil**, **Anamay Brahme**, **Asad Vathare**  
Under the guidance of *Prof. Noshir Z. Tarapore* — Vishwakarma University

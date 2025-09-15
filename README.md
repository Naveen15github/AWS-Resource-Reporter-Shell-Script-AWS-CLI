# ⚡ AWS Resource Reporter Shell Script (AWS CLI)  
**Automate. Monitor. Optimize. Cloud at your Fingertips.**

---

## 🚀 What is This Project?

Welcome to the **AWS Resource Reporter Shell Script** – your one-click solution for real-time AWS resource monitoring.  
This project leverages the **power of shell scripting** and the **AWS CLI** to automate the visibility of critical AWS resources for any cloud engineer, DevOps team, or curious learner.

---

## 🌟 Why Does It Matter?


Modern cloud environments demand **speed**, **efficiency**, and **governance**.  
Manually checking AWS resources is tedious, error-prone, and simply not scalable.  
This script:
- 🕒 **Saves You Time:** Instant audits with a single command.
- 📊 **Improves Governance:** Spot anomalies and unused resources fast.
- 💰 **Optimizes Cost:** Identify what you’re actually running and paying for.
- 🛡️ **Secures Access:** Know your IAM users – always.

---

## 🛠️ Features

- **S3 Buckets:** See all storage buckets at a glance.
- **EC2 Instances:** List running, stopped, terminated instances with details.
- **Lambda Functions:** Instantly discover your deployed serverless code.
- **IAM Users:** Quick inventory of all AWS users for security checks.

---

## 📦 Prerequisites

1. **AWS CLI Installed**  
   ![Install the AWS CLI](https://github.com/Naveen15github/AWS-Resource-Reporter-Shell-Script-AWS-CLI/blob/64a097745ddc64cdce8a24118cfb1800711d3385/Screenshot%202025-09-16%20002803.png)
2. **AWS Credentials Configured**  
   ```bash
   aws configure
   ```
3. **A Unix Shell Environment**  
   - Linux, macOS, or Windows with WSL/Git Bash.

---

## 🏗️ Installation


```bash
git clone https://github.com/Naveen15github/AWS-Resource-Reporter-Shell-Script-AWS-CLI.git
cd AWS-Resource-Reporter-Shell-Script-AWS-CLI
chmod +x aws-resource-report.sh
```

---

## ▶️ How to Use

Run the script:
```bash
./aws-resource-report.sh
```

**Example Output:**

![Example Terminal Output](https://github.com/Naveen15github/AWS-Resource-Reporter-Shell-Script-AWS-CLI/blob/64a097745ddc64cdce8a24118cfb1800711d3385/Screenshot%20(41).png)
![Example Terminal Output](https://github.com/Naveen15github/AWS-Resource-Reporter-Shell-Script-AWS-CLI/blob/64a097745ddc64cdce8a24118cfb1800711d3385/Screenshot%20(42).png)
![Example Terminal Output](https://github.com/Naveen15github/AWS-Resource-Reporter-Shell-Script-AWS-CLI/blob/64a097745ddc64cdce8a24118cfb1800711d3385/Screenshot%20(43).png)

```
================ AWS S3 Buckets ================
bucket-1
bucket-2

================ EC2 Instances ================
InstanceId    State      Type
i-01234abcd   running    t2.micro

================ Lambda Functions ================
MyFunction
AnotherFunction

================ IAM Users ================
admin
dev-user
```

---

## 🧠 How It Works

![Architecture Diagram](https://github.com/Naveen15github/AWS-Resource-Reporter-Shell-Script-AWS-CLI/blob/64a097745ddc64cdce8a24118cfb1800711d3385/IMG_4892.PNG)

```bash
#!/bin/bash

echo "================ AWS S3 Buckets ================"
aws s3 ls

echo "================ EC2 Instances ================"
aws ec2 describe-instances --query 'Reservations[*].Instances[*].[InstanceId,State.Name,InstanceType]' --output table

echo "================ Lambda Functions ================"
aws lambda list-functions --query 'Functions[*].FunctionName' --output table

echo "================ IAM Users ================"
aws iam list-users --query 'Users[*].UserName' --output table
```

---

## 💡 Advanced: Make It Your Own

- Add monitoring for RDS, CloudWatch, Elastic Beanstalk, or Billing.
- Schedule with `cron` for regular reporting.
- Pipe output to Slack, email, or your favorite dashboard.
- Build alerting for anomalies or unauthorized changes.

---

## 🏆 What You’ll Learn

- **Cloud Automation** in real-world scenarios.
- **Shell Scripting** with practical AWS integration.
- **DevOps Best Practices** for visibility and governance.
- **AWS CLI Mastery:** Powerful queries and output formatting.

---

## ❓ FAQ & Troubleshooting

- **No AWS CLI?**  
  [Install it here.](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
- **Permission Denied?**  
  Run: `chmod +x aws-resource-report.sh`
- **Access Issues?**  
  Make sure your AWS user has read permissions for S3, EC2, Lambda, and IAM.

---

## 🙌 Contributing

Want to extend this script? Fork it, improve it, and submit a PR!  
Ideas: Multi-account support, resource tagging reports, cost dashboards, or integration with monitoring tools.

---

## 📬 Contact & Showcase

**Made by [Naveen15github](https://github.com/Naveen15github)**  
Connect, share feedback, or showcase your extensions!

---

## 📝 License

MIT License – open for all cloud builders!

---

**Unleash the power of automation. Make your cloud smarter. 🚀**

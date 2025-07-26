# EC2-Website-Hosting-with-S3-Synced-HTML


# 🌐 EC2 Website Hosting with S3-Synced HTML

This project demonstrates how to host a custom website on an **Amazon EC2 instance** using HTML content pulled from an **S3 bucket** via the **AWS CLI**. The web server is powered by Apache on Amazon Linux 2.

🔗 **Live Site**: [http://54.198.202.198](http://54.198.202.198)

---

## 🚀 Services Used

- **Amazon EC2** – Virtual machine running the web server
- **Amazon S3** – Storage bucket holding the HTML content
- **AWS CLI** – Used to pull files from S3 to EC2
- **Apache Web Server** – Serves the HTML page
- **IAM** – Configured to allow access to S3 from EC2

---

## 🧱 Architecture

1. EC2 instance is launched using Amazon Linux 2.
2. Apache (`httpd`) is installed and configured.
3. HTML file is stored in an S3 bucket: `roushan-cloud-website1/index.html`.
4. AWS CLI is used on the EC2 instance to pull the file:
   ```bash
   sudo aws s3 cp s3://roushan-cloud-website1/index.html /var/www/html/index.html






   Visitors can access the webpage via the EC2 public IP.

📂 Folder Structure
css
Copy
Edit
/var/www/html/
└── index.html    ← HTML file synced from S3
🧑‍💻 Commands Summary
bash
Copy
Edit
# Inside EC2
sudo yum update -y
sudo yum install httpd awscli -y
sudo systemctl start httpd
sudo systemctl enable httpd

# AWS CLI setup (one-time)
aws configure  # Add Access Key, Secret, Region

# Sync content from S3
sudo aws s3 cp s3://roushan-cloud-website1/index.html /var/www/html/index.html

# Restart Apache if needed
sudo systemctl restart httpd
🖼 Screenshot
<img width="1300" height="908" alt="image" src="https://github.com/user-attachments/assets/1ceb1205-8b45-4b51-9bb4-1ea72e4ebb7f" />

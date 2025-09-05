

# 🌐 Serverless Translation System on AWS

A serverless, automated language translation pipeline built using **AWS Lambda**, **Amazon Translate**, **S3**, and **Terraform**. This project demonstrates how to design and deploy an Infrastructure-as-Code (IaC) solution for real-time or batch text translation.

---

## 🚀 Project Overview

This system allows users to upload a JSON file containing:

* **Text** – the content to translate
* **Source Language** – input language code
* **Target Language** – output language code

When uploaded to an **S3 Request Bucket**, the file automatically triggers a **Lambda function** that calls **Amazon Translate**. The translated output is then stored in an **S3 Response Bucket** for retrieval.

✅ **Serverless** – no servers to manage
✅ **Scalable** – works with real-time or batch requests
✅ **Cost-Effective** – pay only for what you use

---

## 🛠️ Architecture

**Core AWS Components:**

* **Amazon S3** – request & response buckets
* **AWS Lambda** – orchestrates translation workflow
* **Amazon Translate** – performs the translation
* **CloudWatch** – logs and monitoring
* **Terraform** – Infrastructure-as-Code

**Workflow:**

1. Upload request JSON → S3 Request Bucket
2. Event triggers Lambda function
3. Lambda calls **Amazon Translate**
4. Translation stored in S3 Response Bucket

---

## 📂 Project Structure

```bash
.
├── main.tf            # Terraform configuration for AWS resources
├── variables.tf       # Input variables for Terraform
├── outputs.tf         # Terraform outputs
├── lambda/            # Lambda function source code
│   └── index.py
└── README.md          # Project documentation
```

---

## ⚙️ Deployment Steps

### 1. Clone the repo

```bash
git clone https://github.com/Manel4Cloud/Language-convertor-using-Lambda.git
cd Language-convertot-using-lambda
```

### 2. Initialize Terraform

```bash
terraform init
```

### 3. Deploy Infrastructure

```bash
terraform apply
```

### 4. Package & Deploy Lambda

```bash
cd lambda
zip function.zip index.py
cd ..
terraform apply -auto-approve
```

---

## 🧪 Testing the System

1. Create a JSON request file:

```json
{
  "text": "Hello, is this Emmanuel?",
  "sourceLang": "en",
  "targetLang": "fr"
}
```

2. Upload it to the **Request Bucket**:

   * AWS CLI:

     ```bash
     aws s3 cp request.json s3://your-request-bucket/
     ```
3. Check the **Response Bucket** for the translated output.

---

## 🐞 Debugging Notes

* Initial issues: Lambda printed translations only to console.
* Fix: Updated Lambda to write results directly to **Response Bucket**.
* Final Result: End-to-end automation works successfully! 🎉

---

## 📸 Demo

* Upload → Trigger → Translate → Store
* End-to-end AWS pipeline confirmed working ✅

---

## 📚 Conclusion

This project demonstrates how **Terraform**, **AWS Lambda**, and **Amazon Translate** can be combined to build a fully automated, serverless translation system.
It highlights cloud-native design principles: scalability, automation, and cost efficiency.

---

## 👨‍💻 Author

**Emmanuel Gyau**
📧 Email: [emmanuelgyau0011@gmail.com](mailto:emmanuelgyau0011@gmail.com)
📱 Phone: +233 534268933



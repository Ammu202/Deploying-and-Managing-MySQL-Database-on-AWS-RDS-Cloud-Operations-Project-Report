# Deploying-and-Managing-MySQL-Database-on-AWS-RDS-Cloud-Operations-Project-Report
# Deploying MySQL Database on AWS RDS

This project demonstrates how to deploy, configure, and operate a MySQL database on Amazon RDS using AWS Free Tier. It covers cloud provisioning, database administration, security configuration, monitoring, and SQL operations.

---

## 🚀 Project Overview
The goal of this project is to create a managed MySQL database instance on AWS RDS, connect to it using MySQL Workbench, run SQL queries, and monitor performance using AWS CloudWatch.

---

## 🛠 Technologies Used
- **AWS RDS (MySQL)**
- **AWS CloudWatch**
- **VPC Security Groups**
- **MySQL Workbench**
- **SQL**
- **AWS IAM & Console**

---

## 📌 Features
- Deployment of MySQL DB instance on AWS RDS  
- Public access configuration with secure IP restrictions  
- Automated backups enabled  
- CloudWatch monitoring for CPU, storage, connections, IOPS  
- CRUD operations on cloud database  
- Real-world cloud operations experience  

---

---

## 📋 Steps Performed

### 1️⃣ Create RDS Instance
- MySQL engine  
- Free tier template  
- `db.t3.micro` instance  
- 20GB gp2 storage  
- Public access enabled  
- Automatic backups enabled  

### 2️⃣ Configure Security Group
- Allowed inbound MySQL (3306)
- Source: **My IP** for secure access

### 3️⃣ Connect via MySQL Workbench
- Used RDS endpoint
- Performed SQL operations

### 4️⃣ Run SQL Commands

#### Create Table:
```sql
CREATE TABLE students (
 id INT AUTO_INCREMENT PRIMARY KEY,
 name VARCHAR(100),
 age INT,
 department VARCHAR(50)
);
INSERT INTO students (name, age, department)
VALUES ('Ammu', 21, 'Engineering'),
       ('Rahul', 22, 'IT'),
       ('Neha', 20, 'CS');
SELECT * FROM students;

## 🗺️ Architecture Diagram

                ┌────────────────────────────┐
                │  MySQL Workbench (Client)  │
                │  Local Machine (Developer) │
                └──────────────┬─────────────┘
                               │
                               │ SQL queries over port 3306
                               ▼
                    ┌────────────────────────────┐
                    │     AWS RDS (MySQL DB)     │
                    │  - Automated Backups        │
                    │  - Storage Monitoring       │
                    │  - Parameter Groups         │
                    └──────────────┬─────────────┘
                               │
                               │ Metrics & Logs
                               ▼
                     ┌──────────────────────────┐
                     │     AWS CloudWatch       │
                     │ - CPU Utilization        │
                     │ - DB Connections         │
                     │ - Free Storage Space     │
                     └──────────────────────────┘




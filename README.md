# Create-and-connect-to-a-cloud-database-instance
Learn how cloud databases work by creating a managed SQL database instance, connecting to it and performing basic SQL operations. Gain hands-on experience in database provisioning, connectivity, CRUD operations in a cloud environment.

# Task 5: Create and Connect to a Cloud Database Instance ☁️

## 🛠 Tools
- **Cloud Providers (Free Tier):**  
  - AWS RDS (Free Tier)
  - 
- **Local Tools:**  
  - MySQL Workbench  

## 📦 Deliverables
- Screenshot of cloud database instance running  
- Screenshot of successful connection  
- SQL commands used (text or screenshot)  
- Short note explaining your process and learning  

## 🧭 Step-by-Step Guide

### 1️⃣ Create a Cloud Database Instance
- Log in to your cloud console → **Databases → Create Instance**  
- Choose **MySQL**
- Configure:
  - Region: nearest to you: pacific mumbai
  - Tier: Free or smallest available  
  - Set username & password  
- Wait for provisioning  

### 2️⃣ Configure Access
- Enable **public IP access** (or use Cloud Shell)  
- Add your local machine’s IP to authorized networks  
- Note the **connection string / endpoint**  

### 3️⃣ Connect to Database
- **Cloud Shell:**  
  ```bash
  gcloud sql connect mydb-instance --user=root
  4. *Create Database & Table*  
   ```sql
   CREATE DATABASE intern_demo;
   USE intern_demo;
   CREATE TABLE students (
     id INT AUTO_INCREMENT PRIMARY KEY,
     name VARCHAR(50),
     domain VARCHAR(30),
     score INT
   );

5.Insert and query data
INSERT INTO students (name, domain, score)
VALUES ('Aarav', 'Cloud', 95), ('Diya', 'DevOps', 89);
SELECT * FROM students;

6. Optional : Remote Access via Python
   import mysql.connector
conn = mysql.connector.connect(
    host="your-cloud-sql-ip",
    user="root",
    password="yourpassword",
    database="intern_demo"
)
cursor = conn.cursor()
cursor.execute("SELECT * FROM students")
print(cursor.fetchall())

7. Clean up.
  

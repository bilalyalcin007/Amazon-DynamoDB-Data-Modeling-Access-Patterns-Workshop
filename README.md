# Amazon DynamoDB Data Modeling & Access Patterns Workshop

## 📖 Project Overview
This project demonstrates hands-on experience with **Amazon DynamoDB**, focusing on **data modeling, access patterns, query optimization, and scalability best practices**.

The use case simulates a **forum-style application**, where multiple DynamoDB tables are designed to support different access patterns efficiently. The project highlights how design decisions impact **performance, cost, and query efficiency** in NoSQL systems.

---

## 🎯 What I Practiced in This Project
- Designing DynamoDB tables based on access patterns  
- Using **GetItem, Query, and Scan** operations  
- Understanding **Scan vs Query performance and cost**  
- Handling **reserved keywords** in DynamoDB expressions  
- Creating and querying **Global Secondary Indexes (GSIs)**  
- Comparing **RCU consumption** across access patterns  
- Managing data via **AWS CLI and AWS Console**  
- Enabling **Point-in-Time Recovery (PITR)** for data protection  

---

## 🏗️ Architecture Overview
![Architecture Diagram](screenshots/1-architecture.png)

---

## 🧩 DynamoDB Tables
![DynamoDB Tables Created](screenshots/3-resources_created.png)

---

## 🔍 Access Patterns & Queries

### 1️⃣ Reading Items with GetItem
![GetItem API](screenshots/7-GetItem_API.png)
![Read Single Item](screenshots/8-read_single_item.png)
![Consistent vs Eventually Consistent Reads](screenshots/9-consistent_read_and_eventually_read.png)

---

### 2️⃣ Querying Item Collections
![Query Item Collections](screenshots/10-reading_item_collections_using_query.png)

---

### 3️⃣ Scan Operations with Filter Expressions
![Scan Forum Table](screenshots/12-scan_forum_table.png)
![Filter Expressions](screenshots/11-reading_item_using_filter_expressions.png)

---

### 4️⃣ Reserved Keyword Handling
❌ Reserved keyword error (`Views`)
![Reserved Word Error](screenshots/13-dynamodb_reserved_word_error.png)

✅ Fixed using `ExpressionAttributeNames`
![Reserved Word Fixed](screenshots/14-reserved_word_error_fixed.png)

---

### 5️⃣ Insert, Update, and Delete Operations
![Insert and Update Items](screenshots/15-insert_and_update_items.png)
![Deleting Data](screenshots/16-deleting_data.png)

---

## 🚀 Global Secondary Index (GSI)

### Why a GSI?
Scan operations were inefficient when querying replies by user.  
A **Global Secondary Index (GSI)** was created to support a new access pattern without redesigning the base table.

![GSI Concept](screenshots/17-global_secondary_indexes.png)
![GSI Explanation](screenshots/20-GSI_note.png)

---

### Creating the GSI (CLI & Console)
![Create GSI (CLI)](screenshots/21-create_gsi.png)
![Create GSI (Console)](screenshots/30-create_GSI_console.png)
![GSI Status](screenshots/22-status_of_GSI.png)

---

### Querying Data Using the GSI
![Query Reply Table](screenshots/18-query_reply_table_1.png)
![Query Reply Table (More Results)](screenshots/19-query_reply_table_2.png)
![Query on GSI](screenshots/23-query_on_GSI.png)
![Query Result on GSI](screenshots/24-query_scan_result_on_GSI.png)

🚫 **GetItem is not supported on GSIs**
![GetItem on GSI Error](screenshots/25-getitem_on_GSI.png)

---

## 🔐 Data Protection & Backups

### Point-in-Time Recovery (PITR)
PITR was enabled to protect against accidental deletes or overwrites.

![Backup Settings](screenshots/34-backup.png)
![Backup Settings Updated](screenshots/35-backup_2.png)
![PITR Enabled](screenshots/36-backup_3.png)

---

## 🧠 Key Learnings
- DynamoDB design starts with **access patterns**, not schema  
- **Scan operations are expensive** and should be avoided at scale  
- GSIs enable efficient querying without table redesign  
- Reserved keywords must be handled explicitly  
- Monitoring **RCUs** is critical for cost optimization  

---

## 🛠️ Tools & Technologies
- Amazon DynamoDB  
- AWS CLI  
- AWS Management Console  
- NoSQL Data Modeling  

---

## ✅ Project Status
✔ Completed  
✔ Tested via AWS CLI and Console  
✔ Portfolio-ready

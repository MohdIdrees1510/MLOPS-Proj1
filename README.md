## 🚗 MLOps Project — Vehicle Insurance Data Pipeline
Welcome to this MLOps project, designed to demonstrate a robust pipeline for managing vehicle insurance data. This walkthrough showcases the tools, techniques, services, and automation strategies used to build and deploy a real-world machine learning pipeline.

Whether you're a recruiter, engineer, or enthusiast — this guide highlights every step from setup to cloud deployment!

## 📁 Project Setup and Structure
🛠️ Step 1: Project Template
Start by executing template.py to generate the initial folder structure and placeholder files.

### 🪴 Step 2: Package Management
Configure local package imports using setup.py and pyproject.toml.

### 💡 Tip: Refer to crashcourse.txt for a quick guide on these files.

### 🧪 Step 3: Virtual Environment and Dependencies
Create a virtual environment and install required dependencies:
bash
conda create -n vehicle python=3.10 -y
conda activate vehicle
pip install -r requirements.txt

### ✅ Verify installed packages:

bash
pip list

## 📊 MongoDB Setup and Data Management

### 🍃 **Step 4: MongoDB Atlas Configuration**  
- Sign up at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)  
- Create a new project and deploy a free M0 cluster  
- Set up a DB user with username/password  
- Allow access from all IPs: `0.0.0.0/0`  
- Copy the Python connection string and replace `<password>`

### 📤 **Step 5: Pushing Data to MongoDB**  
- Create a `notebook/` folder and add your dataset  
- Create `mongoDB_demo.ipynb` and push data to MongoDB  
- Verify data in MongoDB Atlas → **Database** → **Browse Collections**

## 📝 Logging, Exception Handling, and EDA

### 🛠️ **Step 6: Set Up Logging and Exception Handling**  
- Create `logger.py` and `exception.py`  
- Test them using `demo.py`

### 📈 **Step 7: EDA and Feature Engineering**  
- Perform exploratory data analysis and feature engineering in the notebook

## 📥 Data Ingestion

### 🔌 **Step 8: Data Ingestion Pipeline**  
Define MongoDB connection logic in:

- `configuration.mongo_db_connections.py`

Implement ingestion logic in:

- `data_access/proj1_data.py`  
- `components/data_ingestion.py`

Update configs in:

- `entity/config_entity.py`  
- `entity/artifact_entity.py`

Run `demo.py` after setting the MongoDB URL.

## 🌐 Setting Environment Variables

### 🧭 **Step 9: Export MongoDB URL**  

#### Bash

```bash
export MONGODB_URL="mongodb+srv://<username>:<password>@cluster.mongodb.net/"
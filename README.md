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

### 🧭 Export MongoDB URL**  

#### Bash
export MONGODB_URL="mongodb+srv://<username>:<password>@cluster.mongodb.net/"

🪟 On Windows, you can also set environment variables via system settings.

## 🔍 Data Validation, Transformation & Model Training
### ✅ Step 9: Data Validation
Define schema in config/schema.yaml.

Implement validation logic in utils/main_utils.py.

### 🔄 Step 10: Data Transformation
Add transformation logic in components.data_transformation.py.

Create estimator.py in the entity/ folder.

### 🧠 Step 11: Model Training
Implement training logic in components.model_trainer.py.

Extend estimator.py with model training classes.

☁️ AWS Setup for Model Evaluation & Deployment

### 🔐 Step 12: AWS Setup
Log in to AWS Console.

Create IAM user (firstproj) with AdministratorAccess.

Generate access keys and download the CSV.

Set AWS Credentials
Bash
bash
export AWS_ACCESS_KEY_ID="YOUR_AWS_ACCESS_KEY_ID"
export AWS_SECRET_ACCESS_KEY="YOUR_AWS_SECRET_ACCESS_KEY"
PowerShell
powershell
$env:AWS_ACCESS_KEY_ID="YOUR_AWS_ACCESS_KEY_ID"
$env:AWS_SECRET_ACCESS_KEY="YOUR_AWS_SECRET_ACCESS_KEY"
Add credentials and region to constants/__init__.py.

### 🪣 Step 13: Model Evaluation and Pushing to S3
Create S3 bucket: my-model-mlopsproj in us-east-1.

Implement push/pull logic in:

src/aws_storage/

entity/s3_estimator.py

## 🚀 Model Evaluation, Model Pusher, and Prediction Pipeline
### 📊 Step 14: Model Evaluation & Model Pusher
Implement evaluation logic and model deployment components.

### 🌐 Step 15: Prediction Pipeline & Web App
Create prediction pipeline and build app.py using FastAPI.

Add static/ and templates/ directories for UI.

## 🔄 CI/CD Setup with Docker, GitHub Actions, and AWS
### 🐳 Step 16: Docker and GitHub Actions
Create Dockerfile and .dockerignore.

## Set up GitHub Actions workflow in .github/workflows/aws.yaml.

### 🔐 GitHub Secrets
Add the following secrets:

AWS_ACCESS_KEY_ID

AWS_SECRET_ACCESS_KEY

AWS_DEFAULT_REGION

ECR_REPO

### 🖥️ Step 17: AWS EC2 and ECR
Launch EC2 instance (Ubuntu 24.04, T2 Medium).

Create ECR repository: vehicleproj.

Install Docker on EC2:

bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
Connect EC2 as a self-hosted GitHub runner.

### 🧪 Step 18: Final Steps
Open port 5080 in EC2 Security Groups.

Access the deployed app at:

http://<your_ec2_public_ip>:5080
Trigger model training via /training route.

## 🛠️ Additional Resources
### 📘 Crash Course: See crashcourse.txt for setup.py and pyproject.toml tips.

### 🔐 GitHub Secrets: Secure your CI/CD pipeline with encrypted secrets.

### 🎯 Project Workflow Summary
Data Ingestion ➔ Data Validation ➔ Data Transformation
Model Training ➔ Model Evaluation ➔ Model Deployment
CI/CD Automation with GitHub Actions, Docker, AWS EC2, and ECR

## 💬 Connect
If you found this project helpful or have questions, feel free to reach out or explore the repo!

Let me know if you'd like this saved as a Markdown file or want help adding visuals, architecture diagrams, or Swagger docs to make it even more impressive!

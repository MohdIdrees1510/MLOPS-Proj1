Vehicle Insurance Default Prediction (MLOps Project)
markdown
# 🚗 Vehicle Insurance Default Prediction — End-to-End MLOps Project

This project demonstrates a complete MLOps workflow for predicting vehicle insurance defaults. It covers everything from local development and data ingestion to cloud deployment and CI/CD automation using Docker, AWS, MongoDB Atlas, and GitHub Actions.

---

## 📦 Project Setup

### 1️⃣ Project Initialization

- Run `template.py` to scaffold the project directory structure.

### 2️⃣ Package Management

- Use `setup.py` and `pyproject.toml` to define and import local packages.
- Refer to `crashcourse.txt` for details on configuring these files.

### 3️⃣ Virtual Environment Setup

```bash
conda create -n vehicle python=3.10 -y
conda activate vehicle
pip install -r requirements.txt
Add required modules to requirements.txt.

Confirm installation with:

bash
pip list
🍃 MongoDB Atlas Integration
4️⃣ Cluster & Database Setup
Sign up at MongoDB Atlas.

Create a project → Create cluster → Select M0 tier → Deploy.

Create DB user with username/password.

Add IP access: 0.0.0.0/0 (open access).

Get connection string (Python driver ≥ 3.6) and replace <password>.

5️⃣ Data Upload
Create notebook/ folder and add dataset.

Create mongoDB_demo.ipynb and push data to MongoDB.

Verify upload via MongoDB Atlas → Database → Browse Collections.

🧾 Logging & Exception Handling
6️⃣ Setup
Create logger.py and exception.py.

Test both using demo.py.

7️⃣ EDA & Feature Engineering
Add exploratory analysis and feature engineering notebooks to notebook/.

📥 Data Ingestion Pipeline
8️⃣ Configuration
Define constants in constants/__init__.py.

Setup MongoDB connection in configuration/mongo_db_connections.py.

Create data_access/proj1_data.py to fetch and transform data.

Define config and artifact classes in:

entity/config_entity.py

entity/artifact_entity.py

Implement ingestion logic in components/data_ingestion.py.

Integrate into training pipeline and run via demo.py.

9️⃣ MongoDB URL Setup
Bash
bash
export MONGODB_URL="mongodb+srv://<username>:<password>@cluster.mongodb.net/"
echo $MONGODB_URL
PowerShell
powershell
$env:MONGODB_URL = "mongodb+srv://<username>:<password>@cluster.mongodb.net/"
echo $env:MONGODB_URL
Windows GUI
Add environment variable:

Name: MONGODB_URL

Value: <your_connection_string>

Add artifact/ to .gitignore.

✅ Data Validation, Transformation & Model Training
🔍 Data Validation
Complete utils/main_utils.py and config/schema.yaml.

Implement validation logic similar to ingestion pipeline.

🔄 Data Transformation
Add transformation logic and estimator.py to entity/.

🧠 Model Trainer
Extend estimator.py with training logic.

Implement trainer component and integrate into pipeline.

☁️ AWS Setup for Model Evaluation & Pushing
🔐 IAM & Access Keys
Create IAM user (firstproj) with AdministratorAccess.

Generate access keys and download CSV.

🌍 Environment Variables
Bash
bash
export AWS_ACCESS_KEY_ID="your_key"
export AWS_SECRET_ACCESS_KEY="your_secret"
PowerShell
powershell
$env:AWS_ACCESS_KEY_ID="your_key"
$env:AWS_SECRET_ACCESS_KEY="your_secret"
🧾 Configuration
Add keys and region to constants/__init__.py.

Setup configuration/aws_connection.py.

Create S3 bucket: my-model-mlopsproj in us-east-1.

📁 S3 Integration
Add aws_storage/ module for push/pull logic.

Create entity/s3_estimator.py for S3 operations.

📊 Model Evaluation & Pusher
Implement evaluation logic with threshold comparison.

Push accepted models to S3 via ModelPusher.

🌐 Web App & Prediction Pipeline
🧱 Setup
Create prediction pipeline.

Build app.py using FastAPI.

Add static/ and templates/ directories.

🔄 CI/CD with GitHub Actions & AWS EC2
🐳 Docker Setup
Create Dockerfile and .dockerignore.

🧪 GitHub Actions
Add workflow file: .github/workflows/aws.yaml.

🖥️ EC2 Setup
Launch EC2 (Ubuntu 24.04, T2 Medium).

Create key pair (proj1key), allow HTTP/HTTPS.

Connect via EC2 Instance Connect.

🐳 Install Docker on EC2
bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
🤖 GitHub Self-Hosted Runner
Configure runner on EC2 using GitHub instructions.

Verify runner status as "idle".

🔐 GitHub Secrets
Add the following secrets:

AWS_ACCESS_KEY_ID

AWS_SECRET_ACCESS_KEY

AWS_DEFAULT_REGION

ECR_REPO

🧪 Trigger CI/CD
Push code to GitHub to trigger pipeline.

🌍 EC2 App Hosting
🔓 Open Port
EC2 → Security Groups → Inbound Rules → Add:

Type: Custom TCP

Port: 5080

Source: 0.0.0.0/0

🚀 Launch App
Visit: http://<your_ec2_public_ip>:5080

Train model via /training route.

🙋‍♂️ Author
Mohd Idrees 🔗 GitHub Profile

📜 License
This project is licensed under the MIT License.

🤝 Contributing
Pull requests are welcome! Feel free to fork the repo and enhance the pipeline or deployment strategy.


---

Let me know if you'd like this saved as a Markdown file or want help generating visuals, architecture diagrams, or Swagger documentation for your FastAPI app.
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

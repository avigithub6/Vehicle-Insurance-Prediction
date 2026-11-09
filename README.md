# MLOps Project – Vehicle Insurance Data Pipeline

## Project Overview

This project demonstrates an end-to-end MLOps pipeline for vehicle insurance data. It covers the complete machine learning process, from data collection and preprocessing to model training, evaluation, and deployment.

The project uses Python, MongoDB Atlas, AWS, Docker, and GitHub Actions to build and deploy a machine learning application.

## 📁 Project Setup

### Step 1: Create Project Structure
- Run the `template.py` file to create the required folders and files.
  
### Step 2: Package Management
- Configure `setup.py` and `pyproject.toml` to manage local Python packages.
- Refer to `crashcourse.txt` for more information.

### Step 3: Create Virtual Environment

```bash
conda create -n vehicle python=3.10 -y
conda activate vehicle
pip install -r requirements.txt
```

Check installed packages:

```bash
pip list
```

## 📊 MongoDB Setup

### Step 4: Configure MongoDB Atlas
1. Create an account on [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
2. Create a new project and an M0 free cluster.
3. Create a database username and password.
4. Configure network access.
5. Copy the Python connection string and add your database password.

### Step 5: Upload Dataset to MongoDB
1. Create a `notebook` folder.
2. Add the dataset and create `mongoDB_demo.ipynb`.
3. Use the notebook to upload the dataset to MongoDB.
4. Check the uploaded data in MongoDB Atlas under Browse Collections.

## 📝 Logging, Exception Handling and EDA

### Step 6: Logging and Exception Handling
- Create separate modules for logging and exception handling.
- Test them using `demo.py`.

### Step 7: Exploratory Data Analysis
- Perform EDA and feature engineering using Jupyter notebooks.
- Understand the dataset and prepare features for model training.

## 📥 Data Ingestion

### Step 8: Create Data Ingestion Pipeline
- Set up MongoDB connection functions in `configuration.mongo_db_connections.py`.
- Create data ingestion logic in `data_access` and `components.data_ingestion.py`.
- Update `entity/config_entity.py` and `entity/artifact_entity.py`.

Set the MongoDB connection string as an environment variable:

**PowerShell:**
```powershell
$env:MONGODB_URL = "your_mongodb_connection_string"
```

Run `demo.py` to test the data ingestion pipeline.

## 🔍 Data Validation and Transformation

### Step 9: Data Validation
- Define the dataset structure in `config.schema.yaml`.
- Implement data validation functions in `utils.main_utils.py`.

### Step 10: Data Transformation
- Create data preprocessing and transformation logic in `components.data_transformation.py`.
- Define the estimator in `entity/estimator.py`.

### Step 11: Model Training
- Implement model training in `components.model_trainer.py`.
- Train machine learning models using the prepared dataset.

## ☁️ AWS Setup

### Step 12: Configure AWS
1. Create an AWS account and configure an IAM user.
2. Set up AWS credentials as environment variables.
3. Create an S3 bucket for storing model files.
4. Configure AWS settings in `constants/__init__.py`.

### Step 13: Model Storage
- Implement model upload and download functionality in `src.aws_storage`.
- Create `entity/s3_estimator.py`.
- Store trained models in the AWS S3 bucket.

## 🚀 Model Evaluation and Prediction

### Step 14: Model Evaluation and Model Pusher
- Compare the trained model with the existing production model.
- Implement model evaluation and model deployment components.
- Create a prediction pipeline to generate predictions.
- Develop `app.py` to connect the prediction pipeline with the web application.

### Step 15: Web Application
- Create `static` and `template` folders.
- Add the required files for the web interface.

## 🔄 Docker and CI/CD Deployment

### Step 16: Docker Setup
- Create a `Dockerfile` to containerize the application.
- Add `.dockerignore` to exclude unnecessary files.
- Configure GitHub Actions for automated deployment.
- Add the required AWS credentials and ECR details as GitHub repository secrets.

### Step 17: AWS EC2 and ECR
1. Create an EC2 instance.
2. Install Docker on the EC2 machine.
3. Configure the EC2 instance as a self-hosted GitHub Actions runner.
4. Connect the deployment workflow with AWS ECR.

### Step 18: Run the Application
- Configure port `5080` in the EC2 security group.
- Access the deployed application using:

```text
http://<public_ip>:5080
```

## 🛠️ Technologies Used

- Python
- Pandas and NumPy
- Scikit-learn
- MongoDB Atlas
- AWS S3, EC2, ECR
- Docker
- Flask
- GitHub Actions
- YAML
- Git and GitHub

## 🎯 Project Workflow

1. Data Ingestion
2. Data Validation
3. Data Transformation
4. Model Training
5. Model Evaluation
6. Model Deployment
7. CI/CD Automation

## 📚 Learning Outcomes

- Understanding the complete MLOps workflow.
- Working with MongoDB Atlas for data storage.
- Building modular machine learning pipelines.
- Managing trained models using AWS S3.
- Deploying applications using Docker and AWS.
- Automating deployment with GitHub Actions.

## 🤝 Connect

Feel free to explore this project, share feedback, or connect with me for discussions about Machine Learning, Data Science, and MLOps.
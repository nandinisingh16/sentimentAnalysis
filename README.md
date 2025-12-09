# **YouTube Sentiment Analysis - Complete MLOps Project**

##  **Project Overview**

**YouTube Sentiment Insights** is an end-to-end Machine Learning Operations (MLOps) project that analyzes YouTube video comments to provide sentiment insights. The system combines machine learning, cloud infrastructure, and web technologies to deliver real-time sentiment analysis through a Chrome extension.

### **Key Features**
-  **Real-time sentiment analysis** of YouTube comments
-  **Interactive visualizations** (pie charts, word clouds, trend graphs)
-  **Production-ready MLOps pipeline** with DVC and MLflow
-  **Scalable Flask API** with AWS deployment
-  **Chrome extension** for seamless user experience

---

##  **Architecture**

### **System Architecture Diagram**
```
┌─────────────────────────────────────────────────────────────┐
│                    Chrome Extension                          │
│  ┌─────────────┐  ┌─────────────┐  ┌──────────────────┐    │
│  │  YouTube    │  │  Sentiment  │  │   Visualizations │    │
│  │   Data API  │  │   Analysis  │  │   (Charts, etc.) │    │
│  └─────────────┘  └─────────────┘  └──────────────────┘    │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                    Flask API (AWS EC2)                       │
│  ┌─────────────┐  ┌─────────────┐  ┌──────────────────┐    │
│  │   ML Model  │  │   MLflow    │  │   Visualization  │    │
│  │  (LightGBM) │  │   Tracking  │  │     Endpoints    │    │
│  └─────────────┘  └─────────────┘  └──────────────────┘    │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                 MLflow Server (AWS EC2)                     │
│  ┌─────────────┐  ┌─────────────┐  ┌──────────────────┐    │
│  │ Experiment  │  │  Model      │  │   Artifact       │    │
│  │  Tracking   │  │  Registry   │  │   Storage (S3)   │    │
│  └─────────────┘  └─────────────┘  └──────────────────┘    │
└─────────────────────────────────────────────────────────────┘
```

### **Data Flow**
1. **User** clicks Chrome extension on YouTube video
2. **Extension** extracts video ID and fetches comments via YouTube API
3. **Comments** are sent to Flask API for sentiment analysis
4. **ML Model** processes comments and returns predictions
5. **Results** are displayed with visualizations in the extension
6. **All experiments** are tracked in MLflow for reproducibility

---
---

## 🖼️ **Visual Showcase**

### **1. Automated CI/CD Pipeline**
End-to-end automation from code to deployment:

<img width="1331" height="443" alt="CI/CD Pipeline" src="https://github.com/user-attachments/assets/e5bc827b-3dbb-4ec3-af0c-92a435a81ac9" />


### **2. Chrome Extension in Action**
The extension provides real-time sentiment analysis directly on YouTube videos with beautiful visualizations:

<img width="323" height="617" alt="Chrome Plugin Result" src="https://github.com/user-attachments/assets/740368c6-1a98-4822-9b5b-9012a5fb14b6" />

### **3. MLflow Model Registry & Experiments**
Comprehensive model tracking and management:

<img width="1041" height="267" alt="Model Outputs" src="https://github.com/user-attachments/assets/f522508b-9b5f-45fe-bd71-2e0e0496a074" />

<img width="1207" height="308" alt="Model Experiments" src="https://github.com/user-attachments/assets/45f25121-6d66-4047-a204-9093eb6161f2" />

<img width="1153" height="308" alt="Model Comparisons" src="https://github.com/user-attachments/assets/f740f2eb-bba9-4d1a-a1ad-28ce9a80f862" />



### **4. Flask API Server**
Production-ready REST API serving sentiment predictions:

<img width="731" height="615" alt="Server API Output" src="https://github.com/user-attachments/assets/49eaba4b-72e1-42ff-88aa-f27a6f6ff285" />



---


##  **Project Structure**

```
youtube-sentiment-analysis/
├── data/                           # Data directory (DVC tracked)
│   ├── raw/                        # Raw data from ingestion
│   └── interim/                    # Processed data
├── models/                         # Trained models
│   ├── lgbm_model.pkl             # LightGBM model
│   └── tfidf_vectorizer.pkl       # TF-IDF vectorizer
├── src/                           # Source code
│   ├── data/                      # Data processing
│   │   ├── data_ingestion.py
│   │   └── data_preprocessing.py
│   ├── model/                     # Model development
│   │   ├── model_building.py
│   │   ├── model_evaluation.py
│   │   └── register_model.py
│   └── api/                       # Flask API
│       └── app.py
├── chrome-extension/              # Chrome extension files
│   ├── manifest.json
│   ├── popup.html
│   ├── popup.js
│   └── icons/
├── mlflow/                        # MLflow server configuration
│   └── run_server.sh
├── aws/                           # AWS deployment scripts
│   ├── ec2-setup.sh
│   └── deploy.sh
├── dvc.yaml                       # DVC pipeline configuration
├── params.yaml                    # Project parameters
├── requirements.txt               # Python dependencies
├── setup.py                       # Package configuration
├── README.md                      # This file
└── .gitignore                     # Git ignore rules
```

---

## **Technology Stack**

### **Machine Learning & Data Science**
- **Python 3.9+** - Primary programming language
- **Scikit-learn** - Machine learning algorithms and utilities
- **LightGBM** - Gradient boosting framework for model training
- **NLTK** - Natural language processing for text preprocessing
- **Pandas & NumPy** - Data manipulation and numerical computing
- **Optuna** - Hyperparameter optimization framework

### **MLOps & DevOps**
- **MLflow** - Experiment tracking and model registry
- **DVC (Data Version Control)** - Data pipeline and versioning
- **Docker** - Containerization
- **Git** - Version control

### **Backend & API**
- **Flask** - Web framework for REST API
- **Gunicorn** - WSGI HTTP server for production
- **Nginx** - Web server and reverse proxy (optional)

### **Frontend & Extension**
- **HTML/CSS/JavaScript** - Chrome extension frontend
- **YouTube Data API v3** - Official API for comment fetching
- **Chrome Extension APIs** - Browser extension functionality

### **Cloud Infrastructure (AWS)**
- **EC2** - Virtual servers for API and MLflow
- **S3** - Object storage for MLflow artifacts
- **ELB (Elastic Load Balancer)** - Load balancing for API
- **Security Groups** - Network security

### **Visualization**
- **Matplotlib & Seaborn** - Chart generation
- **WordCloud** - Word cloud visualization
- **Plotly** (optional) - Interactive charts

---

##  **Installation & Setup**

### **Prerequisites**
- Python 3.9+
- Git
- Chrome Browser
- AWS Account (for deployment)
- YouTube Data API Key

### **1. Local Development Setup**

```bash
# Clone the repository
git clone https://github.com/yourusername/youtube-sentiment-analysis.git
cd youtube-sentiment-analysis

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Initialize DVC
dvc init

# Set up MLflow tracking URI
export MLFLOW_TRACKING_URI=http://localhost:5000
```

### **2. MLflow Server Setup**

```bash
# Start MLflow server locally
mlflow server \
  --backend-store-uri sqlite:///mlflow.db \
  --default-artifact-root ./mlruns \
  --host 0.0.0.0 \
  --port 5000
```

### **3. Run the Complete Pipeline**

```bash
# Execute the DVC pipeline
dvc repro

# Or run individual stages
dvc repro data_ingestion
dvc repro data_preprocessing
dvc repro model_building
dvc repro model_evaluation
dvc repro model_registration
```

### **4. Start Flask API**

```bash
# Run the Flask API locally
cd src/api
python app.py

# API will be available at http://localhost:5000
```

### **5. Chrome Extension Setup**

1. Open Chrome and go to `chrome://extensions/`
2. Enable "Developer mode" (toggle in top right)
3. Click "Load unpacked"
4. Select the `chrome-extension/` directory
5. The extension icon will appear in your toolbar

### **6. Get YouTube API Key**

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select existing one
3. Enable "YouTube Data API v3"
4. Create credentials (API Key)
5. Copy the API key and update it in `popup.js`

---

##  **Model Development Pipeline**

### **Data Pipeline**
```
Raw YouTube Comments → Data Ingestion → Data Preprocessing → Feature Engineering → Model Training
```

### **1. Data Ingestion**
- **Input**: YouTube video URLs
- **Process**: Fetches comments using YouTube Data API
- **Output**: `data/raw/train.csv`, `data/raw/test.csv`
- **Parameters**: `test_size` (default: 0.2)

### **2. Data Preprocessing**
- **Steps**:
  1. Lowercase conversion
  2. Remove special characters and URLs
  3. Stopword removal (keeping sentiment words)
  4. Lemmatization using WordNet
- **Output**: `data/interim/train_processed.csv`

### **3. Feature Engineering**
- **TF-IDF Vectorization** with n-grams (1-3)
- **Max Features**: Configurable (default: 10000)
- **Output**: Sparse feature matrices

### **4. Model Training**
- **Algorithm**: LightGBM (Gradient Boosting)
- **Hyperparameters**:
  - `n_estimators`: 367
  - `learning_rate`: 0.09
  - `max_depth`: 20
  - `max_features`: 1000
- **Output**: `lgbm_model.pkl`, `tfidf_vectorizer.pkl`

### **5. Model Evaluation**
- **Metrics**: Accuracy, Precision, Recall, F1-Score
- **Confusion Matrix**: Visual analysis
- **MLflow Tracking**: All parameters and metrics logged

### **6. Model Registration**
- **Registry**: MLflow Model Registry
- **Stage**: Staging → Production
- **Versioning**: Automatic version increments



##  **Deployment**

### **AWS EC2 Deployment**

#### **1. Launch EC2 Instance**
```bash
# Create EC2 instance (Ubuntu 20.04)
# Security Groups: Open ports 22 (SSH), 5000 (MLflow), 8080 (API)

# Connect to instance
ssh -i your-key.pem ubuntu@your-ec2-public-ip
```

#### **2. Setup MLflow Server**
```bash
# Install dependencies
sudo apt update
sudo apt install python3-pip python3-venv

# Create directory
mkdir mlflow-server
cd mlflow-server

# Create virtual environment
python3 -m venv venv
source venv/bin/activate

# Install MLflow and AWS dependencies
pip install mlflow boto3 awscli

# Configure AWS credentials
aws configure

# Start MLflow server
mlflow server \
  --host 0.0.0.0 \
  --port 5000 \
  --backend-store-uri sqlite:///mlflow.db \
  --default-artifact-root s3://your-bucket-name/mlflow-artifacts/
```

#### **3. Deploy Flask API**
```bash
# Clone repository
git clone https://github.com/yourusername/youtube-sentiment-analysis.git
cd youtube-sentiment-analysis

# Install dependencies
pip install -r requirements.txt

# Set environment variables
export MLFLOW_TRACKING_URI=http://your-mlflow-server-ip:5000
export AWS_ACCESS_KEY_ID=your-access-key
export AWS_SECRET_ACCESS_KEY=your-secret-key

# Run with Gunicorn (production)
gunicorn --workers 4 --bind 0.0.0.0:8080 src.api.app:app
```

#### **4. Configure Nginx (Optional)**
```nginx
# /etc/nginx/sites-available/youtube-sentiment
server {
    listen 80;
    server_name your-domain.com;

    location / {
        proxy_pass http://localhost:8080;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}
```

#### **5. Setup Load Balancer (AWS ELB)**
1. Create Application Load Balancer
2. Configure target group pointing to EC2 instances
3. Set up health checks on `/health` endpoint
4. Configure SSL certificate (HTTPS)

---

##  **Model Performance**

### **Baseline Results**
| Model | Accuracy | Precision | Recall | F1-Score | Training Time |
|-------|----------|-----------|--------|----------|---------------|
| Random Forest | 64.8% | 0.73 | 0.65 | 0.57 | ~3 minutes |
| XGBoost (Optimized) | 68.2% | 0.75 | 0.68 | 0.61 | ~5 minutes |
| **LightGBM (Production)** | **70.1%** | **0.77** | **0.70** | **0.64** | **~2 minutes** |

### **Class-wise Performance (LightGBM)**
| Sentiment | Precision | Recall | F1-Score | Support |
|-----------|-----------|--------|----------|---------|
| Negative (-1) | 0.85 | 0.55 | 0.67 | 1650 |
| Neutral (0) | 0.67 | 0.82 | 0.74 | 2555 |
| Positive (1) | 0.65 | 0.84 | 0.73 | 3154 |

### **Confusion Matrix**
```
              Predicted
              -1    0    1
Actual  -1   907   512  231
        0    301  2094  160
        1    228   504 2422
```
---
## **CI/CD Pipeline**

### **GitHub Actions Workflow**
```yaml
# .github/workflows/ci-cd.yml
name: CI/CD Pipeline

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Set up Python
        uses: actions/setup-python@v2
      - name: Install dependencies
        run: pip install -r requirements.txt
      - name: Run tests
        run: pytest tests/ -v

  train-model:
    needs: test
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Train model
        run: dvc repro
      - name: Push DVC changes
        run: dvc push

  deploy:
    needs: train-model
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'
    steps:
      - uses: actions/checkout@v2
      - name: Deploy to AWS
        run: ./aws/deploy.sh
```

---

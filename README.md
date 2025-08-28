# YouTube Comment Sentiment Analysis 🎥📊

A comprehensive machine learning project that analyzes the sentiment of YouTube comments using Natural Language Processing (NLP) techniques. The project includes a Flask web application for real-time sentiment analysis and visualization, complete with MLflow experiment tracking and Docker deployment capabilities.

![Python](https://img.shields.io/badge/python-v3.8+-blue.svg)
![Flask](https://img.shields.io/badge/flask-v2.0+-green.svg)
![MLflow](https://img.shields.io/badge/mlflow-v2.0+-orange.svg)
![Docker](https://img.shields.io/badge/docker-supported-blue.svg)

## 🚀 Features

- **Sentiment Analysis**: Classify YouTube comments as positive, negative, or neutral
- **Real-time Processing**: Flask API for live sentiment analysis
- **Data Visualization**: Generate word clouds and sentiment distribution charts
- **ML Pipeline**: Complete data preprocessing, model training, and evaluation pipeline
- **Experiment Tracking**: MLflow integration for model versioning and tracking
- **Containerization**: Docker support for easy deployment
- **Model Performance**: Confusion matrix and performance metrics visualization
- **DVC Integration**: Data Version Control for reproducible data science workflows

## 🛠️ Tech Stack

- **Backend**: Python, Flask, MLflow
- **Machine Learning**: scikit-learn, NLTK, pandas, numpy
- **Visualization**: matplotlib, wordcloud
- **Containerization**: Docker
- **Data Management**: DVC (Data Version Control)
- **Environment**: Virtual environment with comprehensive dependencies

## 📦 Installation

### Prerequisites
- Python 3.8+
- pip
- Docker (optional, for containerized deployment)

### Setup

1. **Clone the repository**
```bash
git clone git@github.com:Pavanachowdary/youtube-comment-sentiment-analysis.git
cd youtube-comment-sentiment-analysis
```

2. **Create and activate virtual environment**
```bash
python -m venv myenv
source myenv/bin/activate  # On Windows: myenv\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Install the package in development mode**
```bash
pip install -e .
```

## 🚀 Quick Start

### Running the Flask Application

```bash
cd flask_app
python app.py
```

The application will be available at `http://localhost:5000`

### API Endpoints

- `POST /predict` - Analyze sentiment of a single comment
- `GET /health` - Health check endpoint
- `POST /batch_predict` - Analyze multiple comments at once
- `GET /wordcloud` - Generate word cloud visualization

### Example API Usage

```python
import requests

# Single comment prediction
response = requests.post('http://localhost:5000/predict', 
                        json={'comment': 'This video is amazing!'})
print(response.json())
```

## 🧪 Model Training

### Training Pipeline

1. **Data Preprocessing**
```bash
python src/data/make_dataset.py
```

2. **Feature Engineering**
```bash
python src/features/build_features.py
```

3. **Model Training**
```bash
python src/models/train_model.py
```

4. **Model Evaluation**
```bash
python src/models/predict_model.py
```

### MLflow Tracking

Start MLflow UI to track experiments:
```bash
mlflow ui
```

Access the MLflow dashboard at `http://localhost:5000` to view experiment results, model metrics, and artifacts.

## 🐳 Docker Deployment

### Build and Run with Docker

```bash
# Build the Docker image
docker build -t yt-sentiment-analysis .

# Run the container
docker run -p 5000:5000 yt-sentiment-analysis
```

### Using Docker Compose (if available)

```bash
docker-compose up
```

## 📊 Data Pipeline

The project follows a structured data science workflow:

1. **Raw Data**: YouTube comments dataset
2. **Data Preprocessing**: Text cleaning, tokenization, stopword removal
3. **Feature Engineering**: TF-IDF vectorization, sentiment labeling
4. **Model Training**: Multiple algorithms comparison (Logistic Regression, SVM, etc.)
5. **Model Evaluation**: Performance metrics and confusion matrix
6. **Model Deployment**: Flask API with trained model

## 📁 Project Structure

```
├── LICENSE
├── Makefile              <- Makefile with commands like `make data` or `make train`
├── README.md             <- The top-level README for developers using this project
├── requirements.txt      <- The requirements file for reproducing the analysis environment
├── setup.py             <- Makes project pip installable (pip install -e .)
├── Dockerfile           <- Docker configuration for containerized deployment
├── dvc.yaml             <- DVC pipeline configuration
├── params.yaml          <- Parameters for model training and evaluation
├── appspec.yml          <- AWS CodeDeploy application specification
├── tox.ini              <- Tox file with settings for running tox
│
├── data/                <- Data directory (managed by DVC)
│   ├── external         <- Data from third party sources
│   ├── interim          <- Intermediate data that has been transformed
│   ├── processed        <- The final, canonical data sets for modeling
│   └── raw              <- The original, immutable data dump
│
├── docs/                <- Sphinx documentation
│   ├── commands.rst
│   ├── conf.py
│   ├── getting-started.rst
│   └── index.rst
│
├── flask_app/           <- Flask web application
│   ├── app.py           <- Main Flask application with API endpoints
│   └── requirements.txt <- Flask app specific requirements
│
├── models/              <- Trained and serialized models, model predictions, summaries
│
├── notebooks/           <- Jupyter notebooks for data exploration and analysis
│
├── references/          <- Data dictionaries, manuals, and explanatory materials
│
├── reports/             <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures/         <- Generated graphics and figures to be used in reporting
│
├── scripts/             <- Utility scripts
│   ├── mlflow_test.py
│   ├── promote_model.py
│   ├── test_flask_api.py
│   ├── test_load_model.py
│   ├── test_model_performance.py
│   └── test_model_signature.py
│
└── src/                 <- Source code for use in this project
    ├── __init__.py      <- Makes src a Python module
    ├── data/            <- Scripts to download or generate data
    ├── features/        <- Scripts to turn raw data into features for modeling
    ├── models/          <- Scripts to train models and make predictions
    └── visualization/   <- Scripts to create exploratory and results oriented visualizations
```

## 🧪 Testing

Run tests to ensure everything is working correctly:

```bash
# Test environment setup
python test_environment.py

# Test Flask API
python scripts/test_flask_api.py

# Test model loading and performance
python scripts/test_load_model.py
python scripts/test_model_performance.py
```

## 📈 Model Performance

The project includes comprehensive model evaluation:

- **Accuracy Metrics**: Precision, Recall, F1-Score
- **Confusion Matrix**: Visual representation of model performance
- **Cross-validation**: Robust model validation
- **Feature Importance**: Understanding key sentiment indicators

## 🔧 Configuration

Key configuration files:

- `params.yaml`: Model parameters and hyperparameters
- `dvc.yaml`: Data pipeline configuration
- `requirements.txt`: Python dependencies
- `Dockerfile`: Container configuration

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Pavana Nettem**

## 🙏 Acknowledgments

- Built using the [Cookiecutter Data Science](https://drivendata.github.io/cookiecutter-data-science/) project template
- Thanks to the open-source community for the amazing tools and libraries
- YouTube API for data access capabilities

## 🚀 Deployment

The project includes configuration for various deployment platforms:

- **AWS CodeDeploy**: Using `appspec.yml`
- **Docker**: Containerized deployment
- **Local Development**: Flask development server

## 🔮 Future Enhancements

- [ ] Real-time YouTube comment streaming
- [ ] Multi-language sentiment analysis
- [ ] Chrome extension integration
- [ ] Advanced visualization dashboard
- [ ] Model performance monitoring
- [ ] A/B testing framework for model comparison

---

⭐ **Star this repository if you found it helpful!**

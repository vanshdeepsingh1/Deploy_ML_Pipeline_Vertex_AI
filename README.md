# Movie Review Sentiment Analysis with Vertex AI MLOps Pipeline  

## **Overview**  
This project implements an end-to-end MLOps pipeline on Google Cloud's Vertex AI to perform sentiment analysis on movie reviews. The solution leverages AutoML capabilities and custom machine learning models, integrating various cloud services for data ingestion, model training, and deployment.  

## **Features**  
- **Dataset:** Fetches IMDb movie review dataset via Stanford API and Kaggle.  
- **Modeling:**  
  - Builds a machine learning model using Gradient Descent with XGBoost.  
  - Explores AutoML capabilities for comparison with the custom model.  
- **Containerization:** Application containerized using Cloud Build with a `cloudbuild.yaml` file.  
- **Deployment:**  
  - Stores container image in Google Artifact Registry.  
  - Deploys a Vertex AI pipeline using the containerized model.  
- **Environment:** Utilizes Vertex AI Workbench and Jupyter Notebook for development.  

## **Technologies Used**  
- **Programming Language:** Python  
- **Libraries/Frameworks:** TensorFlow, XGBoost  
- **Cloud Services:**  
  - Vertex AI (AutoML, Workbench, Pipeline)  
  - Cloud Build (containerization)  
  - Artifact Registry (image storage)  
- **Dataset Sources:**  
  - IMDb dataset via [Stanford API](https://ai.stanford.edu/~amaas/data/sentiment/)  
  - Kaggle  

## **Pipeline Workflow**  
1. **Dataset Ingestion:**  
   - Fetches IMDb movie reviews and processes the data for sentiment analysis.  

2. **Model Development:**  
   - Implements a Gradient Descent-based XGBoost model.  
   - Trains and evaluates the model using Vertex AI Workbench.  
   - Compares performance with AutoML-generated models.  

3. **Containerization and Deployment:**  
   - Defines build steps in a `cloudbuild.yaml` file.  
   - Builds and pushes the container to Google Artifact Registry.  
   - Deploys the model pipeline on Vertex AI using the containerized image.  

4. **Execution:**  
   - Runs end-to-end machine learning workflows with Vertex AI pipelines.  

## **Repository Structure**  
```
.
├── notebooks/                # Jupyter notebooks for model development  
├── cloudbuild.yaml           # Cloud Build configuration  
├── Dockerfile                # Containerization instructions  
├── src/                      # Source code for data preprocessing and modeling  
│   ├── data_ingestion.py  
│   ├── model_training.py  
│   ├── automl_pipeline.py  
├── README.md                 # Project documentation  
```

## **Setup and Deployment**  

### **Prerequisites**  
- Google Cloud Project with Vertex AI, Artifact Registry, and Cloud Build enabled.  
- Kaggle account and API key for dataset access.  
- Python (>=3.7), with libraries: TensorFlow, XGBoost, pandas, scikit-learn.  

### **Steps to Run the Project**  

1. **Clone the Repository:**  
   ```bash  
   git clone <repository-url>  
   cd <repository-directory>  
   ```  

2. **Setup Environment:**  
   ```bash  
   pip install -r requirements.txt  
   ```  

3. **Prepare Dataset:**  
   - Fetch the dataset using the scripts in `src/data_ingestion.py`.  

4. **Model Training:**  
   - Train the model locally or in Vertex AI Workbench using `notebooks/model_training.ipynb`.  

5. **Containerize the Application:**  
   - Use `cloudbuild.yaml` to build and push the Docker image:  
     ```bash  
     gcloud builds submit --config cloudbuild.yaml  
     ```  

6. **Deploy Vertex AI Pipeline:**  
   - Execute the pipeline deployment script in `src/automl_pipeline.py`.  

7. **Monitor and Evaluate:**  
   - Monitor the deployed model in Vertex AI dashboard.  
   - Analyze and compare AutoML and custom model performance.  

## **Contributions**  
Feel free to fork the repository and raise a pull request for any improvements or feature additions.  

## **License**  
This project is licensed under the MIT License.  

---  

This README is designed to guide users and collaborators through the project. Let me know if you’d like to modify or expand any section!

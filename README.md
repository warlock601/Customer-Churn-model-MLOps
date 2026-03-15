# Customer-Churn-model-MLOps
<img width="600" height="650" src="https://github.com/warlock601/Customer-Churn-model-MLOps/blob/main/End-to-End-MLOps-Project.jpg">
This repository demonstrates a Customer-Churn-prediction model automated by MLOps engineer using kubernetes, DVC, ArgoCD, Github-Actions, KServe. Churn refers to the rate at which customers stop subscribing to a service or employees leave a company. Churn models are used to predict and based on that prediction the company/org implement some tactics to retain customers/employees.

## What Does This Model Do?

**Real-World Example:**

Imagine you run a telecom company with thousands of customers. Some customers are happy and stay for years, while others leave (churn) after a few months. This model predicts which customers are likely to leave.

**Example Customer:**
- **Sarah** is 45 years old
- Been a customer for 24 months
- Pays $79.99/month
- Total spent: $1,920
- Called customer support 3 times this month

**Model Prediction:**
```json
{
  "churn": 1,
  "churn_probability": 0.73
}
```

**Translation:** Sarah has a **73% chance of canceling her subscription**. Why? She's calling support frequently (unhappy) and paying relatively high fees. Your business can now:
- Offer her a discount
- Reach out with personalized support
- Prevent losing her before she leaves

**The model looks at patterns** like:
- High monthly charges → More likely to churn
- More support calls → Customer is frustrated
- Low tenure → Haven't built loyalty yet

This helps businesses **save customers proactively** instead of reacting after they've already left!

### MLOps Workflow
Once the model is ready (Model is prepared using Dataset and Algo), ML engineers come into picture, they take this model and develop API for the model. Typically ML engineers use FastAPI, Flask. Once the API is ready, ML engg also work on Performance enhancements and scaling of the model. Once the model and its API is ready, management asks the development team to prepare UI or bind the API to the existing UI of the company/org. Now the support engineers (here support engg are the ones that will be using this model for Churn Prediction/like customers) go to a particular page of the website, they provide the info such as Age, tenure, Month, Year etc and once this info is provided, HTML page forwards that request to the API.This way they get the response back on the UI.

</br>
MLOps engineers then start automating the manual manual activities and also automate the deployment process. MLOps engg will introduce DVC, KServe, Kubernetes, Github-Actions, ArgoCD for the model.

## Project Structure

```
churn-model/
├── generate_data.py          # Generate synthetic churn dataset
├── train.py                   # Train the model
├── api.py                     # FastAPI inference server
├── requirements.txt           # Python dependencies
├── Dockerfile                 # Container image
├── .dvc/config               # DVC configuration
├── models/
│   └── churn_model.pkl.dvc   # DVC metadata for model
├── k8s/
│   ├── deployment.yaml       # Kubernetes deployment
│   └── inference.yaml        # KServe inference service
├── .github/workflows/
│   └── mlops-pipeline.yaml   # GitHub Actions CI/CD
└── argocd/
    └── application.yaml      # ArgoCD application
```

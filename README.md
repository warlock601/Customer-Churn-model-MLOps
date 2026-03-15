# Customer-Churn-model-MLOps

A repository for Customer-Churn-model using DVC, ArgoCD, Github-Actions, KServe

### Use-Case
Let's take an example of telecom industry like Airtel, they provide services to million of users. Previously the competetion was less but now users easily switch b/w telecom provders based on their likings. This is difficult for the telecom providers so they want to make it easy for their support. These telecom providers want their support to analyze who are their potential customers who are willing to leave the telecom provider so they have to predict. </br>
</br>
Churn refers to the rate at which customers stop subscribing to a service or employees leave a company. Churn models are used to predict and based on that prediction the company/org implement some tactics to retain customers/employees.
</br>
</br>
Once the model is ready (Model is prepared using Dataset and Algo), ML engineers come into picture, they take this model and develop API for the model. Typically ML engineers use FastAPI, Flask. Once the API is ready, ML engg also work on Performance enhancements and scaling of the model. Once the model and its API is ready, management asks the development team to prepare UI or bind the API to the existing UI of the company/org. Now the support engineers (here support engg are the ones that will be using this model for Churn Prediction/like customers) go to a particular page of the website, they provide the info such as Age, tenure, Month, Year etc and once this info is provided, HTML page forwards that request to the API.This way they get the response back on the UI.

</br>
MLOps engineers then start automating the manual manual activities and also automate the deployment process. MLOps engg will introduce DVC, KServe, Kubernetes, Github-Actions, ArgoCD for the model.

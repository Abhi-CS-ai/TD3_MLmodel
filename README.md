Overview
This repository contains the implementation of a workshop focused on data redundancy and distributed computing concepts. The project is divided into two main sections:

Distributed Computing Exercise : Demonstrates the creation of a distributed prediction system using predictive models trained on the Iris dataset.
E-commerce API : Implements a simple e-commerce platform with products, orders, and cart management functionalities (as described in the original workshop).
This README focuses on the Iris dataset and the predictive models used in the distributed computing exercise.

Dataset
The Iris dataset is a well-known dataset in the field of machine learning and statistics. It contains measurements of 150 iris flowers from three species: Setosa, Versicolor, and Virginica. Each sample has four features:

Sepal length
Sepal width
Petal length
Petal width
The goal is to predict the species of an iris flower based on these features.

Predictive Models
Four predictive models were developed for this project, each using a different algorithm or approach. These models are stored as separate files in the models/ directory.

Model Files
Logistic Regression
Logistic Regression
logistic_model.pkl
Decision Tree
Decision Tree
decision_tree_model.pkl
Random Forest
Random Forest
random_forest_model.pkl
Support Vector Machine
SVM
svm_model.pkl

Each model was trained on the Iris dataset and evaluated for accuracy and performance.

Evaluation Metrics
The models were evaluated using the following metrics:

Accuracy : Percentage of correctly classified samples.
Precision : Ability of the model to identify positive samples.
Recall : Ability of the model to find all relevant cases.
F1-Score : Harmonic mean of precision and recall.
Logistic Regression
96.67
0.97
0.96
0.96
Decision Tree
94.74
0.95
0.94
0.94
Random Forest
97.37
0.98
0.97
0.97
Support Vector Machine
95.65
0.96
0.95
0.95

Distributed Prediction System
Consensus Prediction
To create a distributed prediction system, the outputs of the four models are averaged to generate a consensus prediction. This ensures that the final prediction leverages the strengths of all models.

Steps:
Load the four models (logistic_model.pkl, decision_tree_model.pkl, random_forest_model.pkl, svm_model.pkl).
Use each model to make predictions on input data.
Average the predictions to generate a consensus output.
Proof-of-Stake Consensus Mechanism
A proof-of-stake mechanism with slashing penalties is implemented to ensure the reliability of contributions from the models. Each model must make an initial deposit (e.g., 1000 units) upon registration.

Key Features:
Weighting System : Adjust weights (ranging from 0 to 1) based on the accuracy of individual models relative to the group consensus.
Slashing Protocol : Penalize models for consistently inaccurate predictions by reducing their deposit.
Merit-Based System : Promote accurate models and discourage dishonest or unreliable contributions.
Prerequisites
Before running the application, ensure you have the following installed:

Python : Version 3.8 or higher.
Libraries :
scikit-learn: For training and evaluating models.
flask: For creating APIs.
joblib: For saving and loading models.
Database : Optional for storing model balances (e.g., JSON-based DB).
Install dependencies using:

bash
Copy
1
pip install scikit-learn flask joblib
Getting Started
Clone the repository:
bash
Copy
1
2
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
Train and save the models (if not already done):
bash
Copy
1
python train_models.py
Start the API server:
bash
Copy
1
python app.py
Access the API at http://localhost:5000 .
Test the /predict endpoint by sending a POST request with input data:
json
Copy
1
2
3
4
5
6
⌄
{
    "sepal_length": 5.1,
    "sepal_width": 3.5,
    "petal_length": 1.4,
    "petal_width": 0.2
}
Contributing
Contributions are welcome! Please follow these guidelines:

Fork the repository.
Create a new branch for your feature or bug fix.
Commit your changes and push to your fork.
Submit a pull request detailing your changes.

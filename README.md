# ANN-churn-prediction
Customer Churn Prediction using Artificial Neural Networks (ANN)
Project Overview

Customer churn is one of the most important business challenges for subscription-based companies. Acquiring new customers is often more expensive than retaining existing ones, making early identification of at-risk customers critical.

In this project, I built a deep learning model using an Artificial Neural Network (ANN) to predict whether a bank customer is likely to leave the company. The solution includes data preprocessing, feature engineering, model training, performance monitoring with TensorBoard, and model serialization for deployment.

Business Problem

Banks lose significant revenue when customers close their accounts and move to competitors.

The objective of this project is to:

Predict customer churn before it happens
Identify customers with a high probability of leaving
Enable proactive retention strategies
Reduce customer acquisition costs
Improve customer lifetime value

Target Variable:

Exited
1 = Customer left the bank
0 = Customer stayed
Dataset

The project uses the Churn Modelling Dataset, which contains customer demographic, financial, and account-related information.

Features Used
Feature	Description
CreditScore	Customer credit score
Geography	Customer country
Gender	Male/Female
Age	Customer age
Tenure	Years with the bank
Balance	Account balance
NumOfProducts	Number of bank products
HasCrCard	Has credit card
IsActiveMember	Active member status
EstimatedSalary	Estimated salary
Removed Columns

The following columns were removed because they do not provide predictive value:

RowNumber
CustomerId
Surname
Project Workflow
1. Data Preprocessing
Feature Cleaning
Removed irrelevant identifiers
Checked data quality
Prepared features for modeling
Encoding Categorical Variables

Gender

Label Encoding
Male/Female converted into numerical values

Geography

One-Hot Encoding
Created separate binary columns for each country

Example:

Geography_France	Geography_Germany	Geography_Spain
1	0	0
2. Train-Test Split

Dataset split into:

80% Training Data
20% Testing Data

This ensures model performance is evaluated on unseen customers.

3. Feature Scaling

Applied:

StandardScaler()

Scaling is essential because neural networks perform best when features have similar numerical ranges.

4. Model Development

Built a fully connected Artificial Neural Network using TensorFlow/Keras.

Architecture
Input Layer
      │
      ▼
Dense (64 neurons, ReLU)
      │
      ▼
Dense (32 neurons, ReLU)
      │
      ▼
Dense (1 neuron, Sigmoid)
Why This Architecture?
ReLU activation helps learn complex patterns efficiently
Multiple hidden layers increase learning capacity
Sigmoid activation outputs churn probability between 0 and 1
Training Strategy
Optimizer
Adam

Learning Rate:

0.01
Loss Function
Binary Crossentropy
Evaluation Metric
Accuracy
Preventing Overfitting
Early Stopping

Implemented Early Stopping with:

monitor='val_loss'
patience=10
restore_best_weights=True

Benefits:

Stops training when validation performance stops improving
Prevents overfitting
Reduces unnecessary computation
TensorBoard Monitoring

Used TensorBoard to visualize:

Training loss
Validation loss
Training accuracy
Validation accuracy
Model learning behavior
Model Persistence

Saved preprocessing objects for future inference:

label_encoder_gender.pkl
onehot_encoder_geo.pkl
scaler.pkl

Saved trained model:

model.h5

This enables deployment without retraining.

Technologies Used
Python
Pandas
NumPy
Scikit-Learn
TensorFlow
Keras
TensorBoard
Pickle
Project Structure
├── ANN_Churn_Prediction.ipynb
├── model.h5
├── scaler.pkl
├── label_encoder_gender.pkl
├── onehot_encoder_geo.pkl
├── logs/
│   └── fit/
└── README.md
Key Learnings

Through this project, I gained hands-on experience with:

Data preprocessing for deep learning
Feature encoding techniques
Feature scaling best practices
Neural network architecture design
TensorFlow/Keras workflows
Early stopping and regularization concepts
TensorBoard experiment tracking
Model serialization for deployment
Impact

This project demonstrates the ability to:

Solve a real-world customer retention problem
Build end-to-end machine learning pipelines
Apply deep learning to structured/tabular data
Prepare models for production deployment
Use industry-standard ML and MLOps practices

For organizations, models like this can help prioritize retention campaigns, reduce churn, and improve long-term customer profitability.

Author
Franck Fossi
Machine Learning Engineer focused on building practical AI solutions and continuously improving through hands-on projects, experimentation, and deployment-oriented workflows.

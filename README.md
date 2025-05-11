Anomaly-Detection-in-Financial-Transactions
Goal: To Identify Anomalous(Fraud) credit-card transactions with lowest possible False Positive Rate

Worked on a highly imbalanced dataset with 30 PCA-transformed features and a class ratio of 1000:17.
Applied Supervised Classification Algorithms on the dataset split using stratified random sampling, among which the Random Forest Classifier gave a higher Recall score of 0.78.
Improved the Recall score to 0.82 with the Isolation Forest model trained in an unsupervised setting.
Designed a Deep Auto-Encoder Neural Network model which achieved the best recall score of 0.85 with only a 6.5% False Positive Rate on the fraudulent class.

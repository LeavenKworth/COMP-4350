This project uses the K-Nearest Neighbors (KNN) algorithm to predict gender based on head circumference and height features.


K = 1 -> Test Accuracy = 0.76
K = 2 -> Test Accuracy = 0.64
K = 3 -> Test Accuracy = 0.70
K = 4 -> Test Accuracy = 0.56
K = 5 -> Test Accuracy = 0.58
K = 6 -> Test Accuracy = 0.56
K = 7 -> Test Accuracy = 0.60
K = 8 -> Test Accuracy = 0.56
K = 9 -> Test Accuracy = 0.54
K = 10 -> Test Accuracy = 0.60
K = 11 -> Test Accuracy = 0.62
K = 12 -> Test Accuracy = 0.52
K = 13 -> Test Accuracy = 0.54
K = 14 -> Test Accuracy = 0.50
K = 15 -> Test Accuracy = 0.52

<img width="348" height="427" alt="Ekran görüntüsü 2026-02-05 095542" src="https://github.com/user-attachments/assets/8912d8e4-8b79-4a17-ab2c-48608ff099af" />



Different K values ranging from 1 to 15 are evaluated. The highest classification accuracy is achieved when **K = 1**, and this value is selected as the optimal number of neighbors for the model.

Misclassified samples are further analyzed to identify patterns and derive a simple rule-based improvement, providing an intuitive transition toward Decision Tree models.

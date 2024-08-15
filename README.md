# Deep-Learning-Challenge
Module 21 Challenge

![images](https://github.com/user-attachments/assets/5535266a-c034-40eb-9c25-6edf823c7106)


# Report on the Neural Network Model: 

## Overview of the analysis: Explain the purpose of this analysis.
The purpose of this analysis is to develop a neural network model to select applicants for funding with the best chance of success in their ventures. The goal is to optimize the model's performance in accurately predicting whether an application will be successful based on the provided data. Various attempts were made to refine the model by adjusting its architecture, training regimen, and data preprocessing steps to achieve the best possible performance.

# Results:

## Data Preprocessing

Data Preprocessing

- Target Variables:

    - The target variable for the model is the "IS_SUCCESSFUL" column, which indicates whether a funding application was successful.

- Feature Variables:

    - The features used for the model include various columns that that capture metadata about each organization, such as:
      - "EIN"
      - "NAME"
      - "APPLICATION_TYPE"
      - "AFFILIATION"
      - "CLASSIFICATION"
      - "USE_CASE"
      - "ORGANIZATION"
      - "STATUS"
      - "INCOME_AMT"
      - "SPECIAL_CONSIDERATIONS"
      - "ASK_AMT"

- Variables to Remove:

  - The Employer Identification Number "EIN" and "NAME" columns were initially removed. However, in the final attempt, the "NAME" column was reintroduced and used to train the model.


## Compiling, Training, and Evaluating the Model

### Original Model:

- Architecture: 2 hidden layers and 1 output layer
- Training: 50 epochs
- Performance:
    - Accuracy: 0.7296
    - Loss: 0.5582
- Evaluation: The original model achieved an accuracy of 0.7296 with a loss of 0.5582. While the initial results were reasonable, further optimization was required to improve performance.

### Attempt 1:

- Changes: Increased the number of epochs from 50 to 100, keeping the layers the same.
- Performance:
    - Accuracy: 0.7293
    - Loss: 0.5643
- Evaluation: In this attempt, increasing the number of epochs led to a slight decrease in accuracy (0.7293) and an increase in loss (0.5643). This suggests that simply extending training time without other adjustments may cause overfitting.

### Attempt 2:

- Changes: Added more hidden layers (4 hidden layers in total) and increased the number of epochs from 50 to 100.
- Performance:
    - Accuracy: 0.7303
    - Loss: 0.5873
- Evaluation: Adding more layers and training for more epochs resulted in a minor increase in accuracy (0.7303), but also a higher loss (0.5873). The model may have become too complex, leading to overfitting reduced the improvement of accuracy.

### Attempt 3:

- Changes: Used Keras Tuner to optimize the model structure, allowing it to automatically select the best architecture.
- Performance:
    - Accuracy: 0.7340
    - Loss: 0.5572
- Evaluation: The Keras Tuner helped improve accuracy to 0.7340 with a slightly better loss of 0.5572. This indicates that tuning the model architecture can yield better results than manual adjustments.

### 4th and Final Attempt:

- Changes: Reintroduced the "NAME" column and adjusted the input data to eliminate any variables or outliers that could confuse the model. Returned to the original 2 hidden layers, 1 output layer, and 50 epochs.
- Performance:
    - Accuracy: 0.7876
    - Loss: 0.4623
- Evaluation: The final attempt resulted in a significant improvement in accuracy (0.7876) and a reduction in loss (0.4623). This indicates that the adjustments made to the input data, including reintroducing the "NAME" column, were crucial in achieving the target performance.

## Were you able to achieve the target model performance?
Yes, I was able to finally achieve the target model performance by adjusting the input data, including keeping the name column,  and optimizing the model with the origional architecture of 2 hidden layers, 1 output layer and training the model with 50 epochs. 

## What steps did you take in your attempts to increase model performance?
- Extended Training: I increased the number of epochs to give the model more time to learn, though this led to overfitting.
- Architectural Changes: I added more hidden layers to increase the model's capacity, but found that this did not produce favorable results. 
- Keras Tuner: I optimized the model by using the Keras Tuner inable to find a better model architecture, and finally saw improvement.
- Data Re-Evaluation: I readjusted the input data to include useful columns, like "NAME" and removed outliers, which ultimately led to the best model performance.

## Summary: 
The overall results of the deep learning model showed that careful tuning of both the model architecture and the input data was necessary to achieve optimal performance. Through various attempts, including increasing the number of epochs, adding more layers, and using hyperparameter tuning, the model's accuracy improved from 0.7296 to 0.7876.

### Recommendation:
For further improvement, I would recommend running the Keras Tuner again while re-evaluating the data to include useful columns such as the "NAME" column and removing outliers. This could further enhance the model's performance. Additionally, I would consider exploring other machine learning models that might be better suited for handling this type of dataset, potentially leading to a more accurate and robust deep learning architecture.  

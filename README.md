# Detecting COVID-19 in X-ray images with Keras

## Disclaimer
Due to very limited dataset(25 positive images) **the model is not meant to be a reliable COVID-19 diagnosis system, nor has it been professionally or academically vetted.** 

### Dataset 
* 25 Positive images were obtained from [the following rep](https://github.com/ieee8023/covid-chestxray-dataset)
* 25 negative images (healthy patients) were obtained from [Kaggle’s Chest X-Ray Images (Pneumonia) dataset](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia) 

So now we have a balanced dataset. But the number of images are still very less. So data augmentation was applied. (refer to the colab notebook)

### Architecture
Fine-Tuned VGG16 architecture.
![model](https://user-images.githubusercontent.com/31489611/77352066-9a3bf800-6d64-11ea-84d5-8669d3f45a52.png)

### Directory structure
```
├── Dataset
│   ├── covid [25 entries]
│   └── normal [25 entries]
├── Covid-19.ipynb
├── Results
├── model.png
```

### Results and conclusion
```
                  precision    recall  f1-score   support

       covid       0.83      1.00      0.91         5
      normal       1.00      0.80      0.89         5

    accuracy                           0.90        10
   macro avg       0.92      0.90      0.90        10
weighted avg       0.92      0.90      0.90        10
```

* Accuracy - 90%
* Recall(True Positive Rate) - 1. 
This means our model correctly classifies all the positive cases.
* Specificity (True negative rate)- 0.8
This means only 80% were correctly identified as healthy out of all the healthy patients.

# Fraudulent-Click-Prediction-in-Online-Advertising
For companies that advertise online, click fraud can happen at an overwhelming volume, resulting in misleading click data and wasted money. 
We build an algorithm that predicts whether a user will download an app after clicking a mobile app ad.

## Dataset
- **Size**: 1441685 rows x 7 columns
- **Attributes**:
  - ‘ip’: 	ip address of click
  - ‘app’: 	app id for marketing
  - ‘device’: 	device type of user mobile phone
  - ‘os’: 	os version of user mobile phone         
  - ‘channel’: 	channel id of ad publisher
  - ‘is_attributed’: indicates if the app was downloaded. (Target)
- **Source**: [Kaggle competition (TalkingData Ad Tracking Fraud Detection Challenge)](https://www.kaggle.com/competitions/talkingdata-adtracking-fraud-detection)
- **Class imbalance**: 99.65% : 0.35% (0 : 1)

## Imbalance Learning Strategy Employed
- **Under Sampling**: Only a very small part of the **is_attributed** data have 1 value (0.35%). This means that the training dataset is highly imbalanced . Usually either we undersample the records with **is_attributed** = 0 or oversample records with **is_attributed** = 1. Because is a large dataset, it is a good option to do undersampling of records with **is_attributed** = 0.
- **LightGBM**: Classifier used to handle class imbalances.

## Metrics
- F1-score
- Area under ROC curve


![ga4](https://www.google-analytics.com/collect?v=2&tid=G-6VDTYWLKX6&cid=1&en=page_view&sid=1&dl=statmike%2Fvertex-ai-mlops%2F03+-+BigQuery+ML+%28BQML%29&dt=readme.md)

# 03 - BigQuery ML (BQML)
Machine Learning with SQL using [BigQuery ML (BQML)](https://cloud.google.com/bigquery-ml/docs/introduction).

**Prerequisites**
- [00 - Setup.ipynb](../00%20-%20Setup/00%20-%20Environment%20Setup.ipynb)
- [01 - BigQuery - Table Data Source.ipynb](../01%20-%20Data%20Sources/01%20-%20BigQuery%20-%20Table%20Data%20Source.ipynb)

## This series of notebooks will introduce BigQuery ML (BQML) with a focus on classification methods.
- [03 - Introduction to BigQuery ML (BQML)](03%20-%20Introduction%20to%20BigQuery%20ML%20(BQML).ipynb)
- [03a - BQML Logistic Regression](03a%20-%20BQML%20Logistic%20Regression.ipynb)
- [03b - BQML Boosted Trees](03b%20-%20BQML%20Boosted%20Trees.ipynb)
- [03c - BQML Random Forest](03c%20-%20BQML%20Random%20Forest.ipynb)
- [03d - BQML Deep Neural Network (DNN)](03d%20-%20BQML%20Deep%20Neural%20Network%20(DNN).ipynb)
- [03e - BQML Wide-And-Deep Networks](03e%20-%20BQML%20Wide-And-Deep%20Networks.ipynb)
- [03f - BQML Logistic Regression With Hyperparameter Tuning](03f%20-%20BQML%20Logistic%20Regression%20With%20Hyperparameter%20Tuning.ipynb)
- [03g - BQML - PCA with Anomaly Detection](03g%20-%20BQML%20-%20PCA%20with%20Anomaly%20Detection.ipynb)
- [03h - BQML k-means with Anomaly Detection](03h%20-%20BQML%20k-means%20with%20Anomaly%20Detection.ipynb)
- [03i - BQML Autoencoder with Anomaly Detection](03i%20-%20BQML%20Autoencoder%20with%20Anomaly%20Detection.ipynb)
- [03Tools - Predictions](03Tools%20-%20Predictions.ipynb)
- [03Tools - Pipelines Example 1](03Tools%20-%20Pipelines%20Example%201.ipynb)
- [03Tools - Pipelines Example 2](03Tools%20-%20Pipelines%20Example%202.ipynb)
- [03Tools - Pipelines Example 3](03Tools%20-%20Pipelines%20Example%203.ipynb)
- [BQML Feature Engineering](BQML%20Feature%20Engineering.ipynb)
- [BQML Cross-validation Example](BQML%20Cross-validation%20Example.ipynb)
- [BQML Ensemble Example](BQML%20Ensemble%20Example.ipynb)

**Notes:**
- Each of the notebooks=experiments `03a` through `03i` create a model in BigQuery with BQML and register the model in Vertex AI Model Registry.  Rerunning the notebook will create a new model version in the Vertex AI Model Registry.  All versions of the model persist in BigQuery and a timestamp is used to maintain naming uniqueness in BigQuery.
    - This recent integration between BQML models and Vertex AI Model Registry will result in an update to this work.
- `03Tools - Prediction` allows you to specify any experiment in this series and it will upload the latest version of the model to a Vertex AI Endpoint and demonstrate requesting predictions with Python, REST, and the GCLOUD CLI.
- Each of the `03Tools Pipelines ...` notebooks demonstrate an ML Workflow using BQML models with Vertex AI Pipelines
    - `Example 1`: Deploy The Best Model To An Endpoint
    - `Example 2`: Conditionally Update Endpoint
    - `Example 3`: Retraining Tournament

## Additional BQML techniques are explored throughout this repository:
- [AutoML](../02%20-%20Vertex%20AI%20AutoML)/
    - [BQML AutoML](../02%20-%20Vertex%20AI%20AutoML/BQML%20AutoML.ipynb)
- [Applied Forecasting](../Applied%20Forecasting/readme.md)/
    - [1 - BigQuery Time Series Forecasting Data Review and Preparation](../Applied%20Forecasting/1%20-%20BigQuery%20Time%20Series%20Forecasting%20Data%20Review%20and%20Preparation.ipynb)
    - [2 - BQML Univariate Forecasting with ARIMA+](../Applied%20Forecasting/2%20-%20BQML%20Univariate%20Forecasting%20with%20ARIMA+.ipynb)
    - [BQML Multivariate Forecasting with ARIMA+ XREG](../Applied%20Forecasting/BQML%20Multivariate%20Forecasting%20with%20ARIMA+%20XREG.ipynb)
    - [8 - Vertex AI Pipelines - Forecasting Tournament - BQML + AutoML + Prophet](../Applied%20Forecasting/8%20-%20Vertex%20AI%20Pipelines%20-%20Forecasting%20Tournament%20-%20BQML%20+%20AutoML%20+%20Prophet.ipynb)

---
ToDo:
- [X] add prereq to readme
- [X] Update references to Service Account and check for permissions - reference the 00 notebooks new section for correct setup
- [X] Hyperlinks to prediction notebook in each of 03a-03f
- [X] export model: GCS and Vertex AI Model Registry use series_experiment naming convention and storage locations
- [X] fix references to data in GCS in the Tools - Predictions notebook: bucket/series/experiment
- [X] add unsupervised anomaly detection using fraud data (maybe in applied section)
    - [X] PCA
        - [X] Export and Register in Vertex AI Model Registry
        - [X] Test Predictions
    - [X] K-Means
        - [X] Export and Register in Vertex AI Model Registry
        - [X] Test Predictions
    - [X] Autoencoder
        - [X] Export and Register in Vertex AI Model Registry
        - [X] Test Predictions
- [X] Update Pass
    - [X] 03 notebook add calculation of count and % for fraud (Class = 1) in each split - incrementally build logic over the methods presented
    - [X] add data review section to beginning of each model_type
    - [X] add custom metrics section with sklearn at end
    - [X] For each section of each notebook include a link to the BQML doc page for the ML. function used
    - [X] Link back to the 01 notebook when mentioned within the training section of each notebook
    - [X] Add a method description in the notebook overview
        - High: Classification, Supervised, Unsupervised 
        - Low: The method
    - [X] Move Predictions into the individual notebooks, sharing endpoint for series
- [IP] unstructured methods in 03g, 03h, 03i, try to reproduce anomaly_detection methods
    - [ ] update 03i ML.DETECT_ANOMALIES to use TRAIN_FRAUD_PCT like 03g an d03h
    - [ ] add graphics for kmeans (PCA then Scatterplot - or pairwise plot with color gradiant)
- [X] Feature Engineering Notebook (from DEV)
- [ ] Example to Create
    - [X] Cross Validation
    - [X] Ensemble Models - stacking
- [ ] Next Update Pass
    - [ ] correct language for 'This Run' sections print statment: with > will
    - [ ] add colab link and code - update bq client to set project for colab use
    - [ ] add code to lookup existing model to each notebook so it can be run without retraining
    - [ ] rename experiment in 03g, h, i to match notebook name
    - [ ] 03h kmeans add silhouette plot
    - [ ] add experiment tracking
    - [ ] directly register BQML models in Vertex AI [link](https://cloud.google.com/bigquery-ml/docs/managing-models-vertex)
    - [ ] create an example of ML.PREDICT for patial dependence plot
- [X] Add condition to evaluation component in 03Tools Pipeline Ex2 that returns auPRC =0 when no model is on the endpoint
- [ ] update pipeline examples
    - [ ] pipelines 1 and 2 break if models form 03g, 03h, or 03i are deployed - unsupervised methods
    - [ ] New version of pipeline 1 that uses experiment tracking - call it 1b
    - [X] update pipeline 2 - same flow but updated to match the series
    - [ ] create pipeline 3
- [ ] Predictions
    - [ ] Online Predictions notebooks like 05
    - [ ] Batch Predictions In Vertex
    - [ ] Cloud Run
    - [ ] Local
    - [ ] DataFlow
- [ ] Monitoring: online and batch in vertex
- [ ] LIT
- [ ] WIT
- [ ] Custom Explainability in Vertex
    - [ ] Feature Based
    - [ ] Example Based


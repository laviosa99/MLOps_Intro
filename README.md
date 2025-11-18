# MLOps Fundamentals**

- Machine learning is not just about building a model
    - the ML code is just 20% of the code you have to write and it’s a small part of the business problem
    
    ![image.png](attachment:746a3bbd-aecc-422b-b9c9-180382d0ae80:image.png)
    
- ML in production
    - what we think it looks like:
        - data collection —> training model —> deployment in production
    - what it actually looks like:
        - data collection —> training model —> deployment in production —> data collection —> ….
        - it’s a loop in production environment!
        - ex: changing your model to a dif method, ML algorithm changes, training on new data that continuously arrives → want to be able to update because it’s a never ending process
- **MLOps:** a set of practices that aims to deploy and maintain machine learning models in production reliably and efficiently
    - the extension of the DevOps methodology to include ML and DS assets as first class citizens within the DevOps ecology

- Usually the trouble begins after deployment
    - accounting for latency
        - 53% of visits are abandoned if a mobile site takes longer than 3 seconds to load
        - latency is one of the biggest problems in engineering
        - models take long time to run (longer than 3 seconds) → what to do?
    - painfully slow
        - what percentage of DS time is spent deploying ML models?
            - 36% of DS said quarter to half of their time spent on this
            - very slow!

- Model-centric vs Data-centric
    - model-centric: hold the data fixed and iteratively improve the code/model (typical method)
    - data-centric: hold the model fixed and iteratively improve the data

- What is the business problem we are trying to solve?
    - the cost of wrong predictions
        - ex: forecast retails —> risk of overstock (waste of resources) or understock (missed opportunities and unsatisfied customers)
        - breaking down the sales forecasting process
            - decompose the sales forecasting process into its component tasks, such as data gathering, historical sales analysis, market trend analysis, and actual forecasting
        - estimating the ROI of AI/ML implementation
            - the ROI could be estimated by comparing the potential increase in sales and decrease in wasted resources due to improved forecasts
        - prioritizing implementation
- **Machine Learning Canvas:** a tool with ten blocks that helps us structure and plan our ML application development
    1. Value Proposition
        1. define the problem, importance, end-user(s)
        2. Geoffrey Moore’s Value Positioning Statement Template
    2. Data Sources
        1. Identifying potential sources of data including internal databases, APIs, open databases, purchasing databases
    3. Prediction Task
        1. what is the ML task? supervised or unsupervised? anomaly detection? classification, regression, or ranking? 
        2. thinking about input, output, and the degree of model complexity
    4. Feature Engineering 
        1. working with domain experts to extract features from raw data sources 
    5. Offline Evaluation
        1. setting up metrics to evaluate system performance pre-deployment
        2. understanding prediction errors and cost of predictions
    6. Decisions
        1. using prediction to make decisions: how will the end-user interact with our predictions? 
        2. possible hidden costs, including human intervention
    7. Making predictions
        1. determining when and how predictions should be made
        2. evaluating computational complexity and the role of humans in the prediction making
    8. Collecting Data
        1. collecting new data for model re-training and preventing model decay
        2. cost considerations for data collection and the role of humans in data labeling
    9. Building Models
        1. deciding frequency of model re-training and associated hidden costs
        2. planning for changing in tech stack and scaling
    10. Live Evaluation & Monitoring
        1. setting up metrics to track system performance post-deployment
        2. understanding the correlation between model metrics and business metrics 
- When not to implement AI/ML?
    - identifying situation where AI/ML may not be necessary bc cost is very high

**Workflow of Machine Learning-based Software Development**

- Three main artifacts in ML-based software: Data, ML Model, and Code
- Three main phases: Data Engineering, ML Model Engineering, and Code Engineering

- Data Engineering
    - basics:
        - Data acquisition and data preparation
        - most resource and time-consuming phase
        - prevent propagation of data errors to the next phase
    - pipeline:
        - data ingestion: collection of data from different sources
        - exploration and validation: understanding data content and structure
        - data wrangling: formatting and cleaning the data
        - data labeling: assigning categories to data points
        - data splitting: division of data into training, validation, and test datasets
- Model Engineering
    - basics:
        - core of the ML workflow: writing and execeuting ML algorithms
        - obtaining the ML model
    - pipeline:
        - Model training: applying ML algorithms on training data
        - model evaluation: validating the model pre-deployment
        - model testing: final acceptance test using test dataset
        - model packaging: exporting model into a consumable format for business application
- Model Deployment
    - pipeline:
        - model serving: addressing the ML model in a productio environment
        - model performance monitoring: observing performance on live, unseen data
        - model performance logging: recording every inference request

- ZenML follows a pipeline-based approach to organize machine learning workflows
    - promotes efficiency, repeatability, and collaboration in projects
    - pipeline: high-level workflow that organizes a series of tasks (steps) required to create a final product
        - each step may involve data prep, feature engineering, model training, model eval, and model deployment
        - each step depends on the outputs of the previous ones

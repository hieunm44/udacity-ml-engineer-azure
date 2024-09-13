# Project Overview
## How it works
You will be using both the `hyperdrive` and `automl` API from `azureml` to build this project. You can choose the model you want to train, and the data you want to use. However, the data you use needs to be external and not available in the Azure's ecosystem. For instance, you can use the [Heart Failure Prediction](https://www.kaggle.com/andrewmvd/heart-failure-clinical-data) dataset from Kaggle to build a classification model.

## Project Workflow
To complete this project, you will have to perform these overall tasks, in the order given below:
![](https://video.udacity-data.com/topher/2020/October/5f7b6ec6_capstone-diagram/capstone-diagram.png)
We will go over these tasks in more detail in the later pages. After you have deployed the model and tested the web service, you will need to submit a README file with details about the data, the model, its performance, and how you deployed it. Finally, make sure that you check the project rubrics to make sure that your project has all the requirements the reviewer will be looking for in your submission.


# Step 1: Project Setup
By the end of this task, you should have your workspace set up and your data accessible in your workspace.

You can use the lab(opens in a new tab) provided by Udacity or your own Azure account to complete the project.

If you plan to use the lab provided to you, the capstone GitHub repo address and files are downloaded and put on the desktop for your convenience.

__Note__: You will have a maximum of 10 chances to load and work in the lab. You will not be able to access the lab after 10 trials. Please load the lab wisely. Be careful with your configuration if you use the lab provided to you. Your experiment will timeout after a certain amount of time! All your work saved locally in the lab will be lost once it times out. Always SAVE your work in Github!!!


# Step 2: Model Training and Deployment
At the end of this task, you will have finished training models on your dataset and deployed the best model.

__Note__: Be careful with your configuration if you use the lab provided to you. Your experiment will timeout after 2 hours! All your work saved locally in the lab will be lost once it times out. Always SAVE your work in Github!!!

### Train a model using Automated ML
The `automl.ipynb` file contains a starter code to help you train a model using Automated ML. The file contains some TODOs that you need to finish.
### Train a model with HyperDrive
The `hyperparameter_tuning.ipynb` file contains some starter codes to help you train a model and perform hyperparameter tuning using HyperDrive.

The type of model you use is not important. You can use ML models through Scikit-learn or Deep Learning models like ANNs and CNNs through Keras, TensorFlow, or PyTorch for this part of the project.
### Model Deployment
After you have trained your models. You will have to deploy your best model as a webservice and test the model endpoint


# Step 3: Complete the README
By the end of this task, you will have a detailed and professional README file of your completed project.

Note: Be careful with your configuration if you use the lab provided to you. Your experiment will timeout after 2 hours! All your work saved locally in the lab will be lost once it times out. Always SAVE your work in Github!!!
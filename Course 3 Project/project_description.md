# Project Overview
In this project, you will continue to work with the [Bank Marketing dataset](https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv). You will use Azure to configure a cloud-based machine learning production model, deploy it, and consume it. You will also create, publish, and consume a pipeline. In the end, you will demonstrate all of your work by creating a README file and a screencast video.

## Project main steps
In this project, you will following the below steps:
1. Authentication
2. Automated ML Experiment
3. Deploy the best model
4. Enable logging
5. Swagger Documentation
6. Consume model endpoints
7. Create and publish a pipeline
8. Documentation
![](https://video.udacity-data.com/topher/2020/September/5f611a94_screen-shot-2020-09-15-at-12.36.11-pm/screen-shot-2020-09-15-at-12.36.11-pm.png)

## Project submissions
At the end of the project, you will submit a README file that describes the main components of the project and a screencast that shows the entire process of the working ML application.


# Step 1: Authentication
NOTE: If you are using your own Azure account, please complete this step. If you are using the lab Udacity provided to you, you can skip this step since you are not authorized to create a security principal. You will NOT be graded on this item and skipping this step will NOT affect other steps in the project.

In this step, you will need to install the Azure Machine Learning Extension which allows you to interact with Azure Machine Learning Studio, part of the `az` command. After having the Azure machine Learning Extension, you will create a `Service Principal` account and associate it with your specific workspace. You will also be instructed to take screenshots to document your work.

## Install and login
Please complete the following if you use your own account
* Install `az` and enable it in the terminal
* `az login` has succeeded
* Install the Azure Machine Learning extension
* Create the Service Principal (SP) and allow the SP access to your specific workspace
* Take a screenshot showing that a __Service Principal__ has been created
* `az ml workspace share` completed without errors
* Take a screenshot showing that the `az ml workspace share` command has been run successfully, with no errors or tracebacks.


# Step 2: Automated ML Experiment
At this point, security is enabled and authentication is completed. In this step, you will create an experiment using Automated ML, configure a compute cluster, and use that cluster to run the experiment.

Note: Be careful with your configuration if you use the lab provided to you. Your experiment will timeout after a certain amount of time! All your work saved locally in the lab will be lost once it times out. Always SAVE your work in Github!!!

You will use the same Bankmarketing dataset with course 1.

Copy the link to a new browser window to download the data: \
https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv

Upload the `bankmarketing_train.csv` to Azure Machine Learning Studio so that it can be used when training the model.

### Create and run Auto ML Experiment
Please complete the following: \
Note: the goal of these steps is not to create a great model but to provide you a model so you can deploy it and consume it. So don't be too harsh on yourself in creating a highly accurate model.
* Create a New Automated ML run
* Select and upload the Bankmarketing dataset
* Create a new Automated ML experiment
* Configure a new compute cluster. Select `Standard_D3_v2`  for the Virtual Machine Size and select 1 as the number of minimum nodes.
* Run the experiment using `Classification`, ensure `Explain best model` is checked. On Exit criterion, reduce the default (3 hours) to 1 and reduce the `Concurrency` from default to 5 (this number should always be less than the number of the compute cluster)  \
 Note: This process takes about 15 minutes and it runs about 5 minutes per iteration


# Step 3: Deploy the Best Model
After the experiment run completes, a summary of all the models and their metrics are shown, including explanations. The Best Model will be shown in the Details tab. In the Models tab, it will come up first (at the top). Make sure you select the best model for deployment.

Deploying the Best Model will allow to interact with the HTTP API service and interact with the model by sending data over POST requests.
* Select the best model for deployment
* Deploy the model and enable "Authentication"
* Deploy the model using Azure Container Instance (ACI)


# Step 4: Enable Logging
Now that the Best Model is deployed, enable Application Insights and retrieve logs. Although this is configurable at deploy time with a check-box, it is useful to be able to run code that will enable it for you.
* Ensure `az`  is installed, as well as the Python SDK for Azure
* Create a new virtual environment with Python3
* Write and run code to enable Application Insights
* Use the provided code `logs.py` to view the logs
* Take a screenshot showing that "Application Insights" is enabled in the Details tab of the endpoint.
* Take a screenshot showing logs by running the provided `logs.py` script


# Step 5: Swagger Documentation
In this step, you will consume the deployed model using Swagger.

Azure provides a [Swagger JSON file](https://swagger.io/) for deployed models. Head to the Endpoints section, and find your deployed model there, it should be the first one on the list.

A few things you need to pay attention to:
1. `swagger.sh` will download the latest Swagger container, and it will run it on port 80. If you don't have permissions for port 80 on your computer, update the script to a higher number (above 9000 is a good idea).
2. `serve.py` will start a Python server on port `8000`. This script needs to be right next to the downloaded `swagger.json` file. NOTE: this will not work if `swagger.json` is not on the same directory.

Please complete the following:
* Download the swagger.json file
* Run the `swagger.sh` and `serve.py`
* Interact with the swagger instance running with the documentation for the HTTP API of the model.
* Display the contents of the API for the model
* Take a screenshot showing that swagger runs on localhost showing the HTTP API methods and responses for the model


# Step 6: Consume Model Endpoints
Once the model is deployed, use the `endpoint.py` script provided to interact with the trained model. In this step, you need to run the script, modifying both the `scoring_uri` and the key to match the `key` for your service and the URI that was generated after deployment.

Hint: This URI can be found in the Details tab, above the Swagger URI.
### Model endpoints
* Modifying both the `scoring_uri` and the `key` to match the key for your service and the URI that was generated after deployment
* Execute the `endpoint.py` file, the output should be similar to the following: `{"result": ["yes", "no"]}`
* Take a screenshot showing that the `endpoint.py` script runs against the API producing JSON output from the model.

The following is an optional step to benchmark the endpoint using Apache bench. You will not be graded on it but I encourage you to try it out.
### Benchmark
* Make sure you have the Apache Benchmark command-line tool installed and available in your path
* In the `endpoint.py`, replace the key and URI again
* Run `endpoint.py`. A data.json file should appear
* Run the `benchmark.sh` file. The output should look similar to the text below
* Take a screenshot showing that Apache Benchmark (ab) runs against the HTTP API using authentication keys to retrieve performance results


# Step 7: Create, Publish and Consume a Pipeline
For this part of the project, you will use the Jupyter Notebook provided in the starter files. You must make sure to update the notebook to have the same keys, URI, dataset, cluster, and model names already created. The notebook has several notes that look similar to this:
```python
# NOTE: update these to match your existing experiment name
experiment_name = 'ml-experiment-1'
``` 
This is an indication to make updates or change the code on your own.
### Complete the Jupyter Notebook
* Upload the Jupyter Notebook `aml-pipelines-with-automated-machine-learning-step.ipynb` to the Azure ML studio
* Update all the variables that are noted to match your environment
* Make sure a `config.json` has been downloaded and is available in the current working directory
* Run through the cells
* Verify the pipeline has been created and shows in Azure ML studio, in the Pipelines section
* Verify that the pipeline has been scheduled to run or is running


# Step 8: Documentation
### Screencast
In this project, you need to record a screencast that shows the entire process of the working ML application.
### Screencast content requirement
A screencast is a useful way to share your project with others. In this project, you need to record a screencast that shows the entire process of the working ML application.
### README
An important part of your project submissions is a README file that describes the project and documents the main steps. Please use the README.md template provided to you as a start. 
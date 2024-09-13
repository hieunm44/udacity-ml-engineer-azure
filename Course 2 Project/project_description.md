# Project Overview
In this project, you'll have the opportunity to create and optimize an ML pipeline. You'll be provided a custom-coded model—a standard Scikit-learn Logistic Regression—the hyperparameters of which you will optimize using HyperDrive. You'll also use AutoML to build and optimize a model on the same dataset, so that you can compare the results of the two methods.

You can see the main steps that you'll be taking in the diagram below:
![](https://video.udacity-data.com/topher/2020/September/5f639574_creating-and-optimizing-an-ml-pipeline/creating-and-optimizing-an-ml-pipeline.png)


# Getting Started
Getting the Starter Code
You can find all of the starter code for this project at this [Github repo](https://github.com/udacity/nd00333_AZMLND_Optimizing_a_Pipeline_in_Azure-Starter_Files).

Keep in mind that you only have 120 minutes before your virtual machine times out. If you are approaching that mark, make sure you commit your work to GitHub using the instructions on the "Check Your Work" page.
* Clone the repository on your own GitHub account, so that you can work on this copy.
* Open the "Azure Workspace" page in the classroom in a new tab or window, so that you can have the instructions open while you work.
* In the virtual machine, click "Access Lab" to start the lab.  (Note: the lab may take a few minutes to load)
* Once the virtual machine has loaded, open a browser, navigate to Github and log in.
* On your cloned GitHub repo, click the green "Code" button to download a .zip of your files.
* Double click the "Azure Portal" button and access the Azure portal using the credentials on the virtual machine desktop.
* Once logged into the Azure portal, navigate to "ml.azure.com"
* Access the Azure Machine Learning Workspace
* Navigate to the "Notebooks" page
* Click "Upload files" and upload your notebook and the `train.py`  script to Azure.


# Setting up the Training Script
As part of our pipeline, we'll need a training script. For this part of the project, we've provided starter code which is marked with `# TODO` sections where you'll need to add your code. This script will be used in the next part of the project. Explore the functionality of the provided code and modify the `train.py` script to run in your pipeline.


# HyperDrive Pipeline
In this step, we'll build our training pipeline. You'll see `### YOUR CODE HERE ###` prompts where you should add your code. Note that some of the cells have pre-filled code that you should not modify,

You'll start by getting the workspace and experiment objects running. Then, you'll build your pipeline—from creating a compute cluster, to HyperDrive, to running the `train.py` script containing the custom-coded Logistic Regression with a HyperDrive run.

Review and modify the `project.ipynb` notebook. Create a compute cluster and a HyperDriveConfig, then run your Hyperdrive experiment.
* Create a compute cluster to run the experiment on, using a `vm_size` or `Standard_D2V2` 
* Specify a parameter sampler
* Specify a policy for early stopping
* Create an estimator for the 
* Create a HyperDriveConfig
* Submit the HyperDriveConfig to run the experiment
* Use the RunDetails widget to see the progress of your run
* Use the `.get_best_run_by_primary_metric()` method of the run to select the best hyperparameters for your model
* Save the best model


# AutoML Run
Once you've completed your HyperDrive run (or while it is running!), you can set up your AutoMLConfig in the same Notebook. In this section, you'll import your data from the specified URL again, clean the data, and pass the cleaned data to an AutoMLConfig that you create.

Once you've successfully run both experiments, you can move on to creating documentation.
* Create a dataset from the provided URL using TabularDatasetFactory in the notebook
* Split data into train and test sets
* Modify the provided AutoML config
* Submit your AutoML run
* Save the best model


# Modifying the README
Now it is time to report on your results (from both of your experiments) in the form of a README.

This README should consist of a summary of your problem statement, your architectures, how the problem was solved, and the changes you would make. The repo you cloned has a starter README with more detailed prompts on what information you need to include in order for your project to meet specifications.

Optionally, you do not need to complete the README in your Azure workspace and can modify it locally on your own machine or in GitHub itself after your code has been uploaded.
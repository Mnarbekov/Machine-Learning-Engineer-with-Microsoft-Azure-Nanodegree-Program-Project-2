
# Machine Learning Engineer with Microsoft Azure – Project 2

In the Machine Learning Engineer with Microsoft Azure – Project 2, I was configuring a cloud-based machine learning production model, deploying it, and consuming the model via the endpoint.
I was using the Bank Marketing dataset (which was used in Project 1). 
I also prepared the screencast video and progress screenshots.

In this project, I have completed (or attempt to complete) the following steps:

•	Authentication

•	Automated ML Experiment

•	Deploy the best model

•	Enable logging

•	Swagger Documentation

•	Consume model endpoints

•	Create and publish a pipeline (issue with the script provided – issue raised to the support)



## Architectural Diagram
The following Architectural Diagram outlines the project key steps, please see more details for each step with screenshots in the next section. 

![Screenshot]( https://github.com/Mnarbekov/Machine-Learning-Engineer-with-Microsoft-Azure-Nanodegree-Program-Project-2/blob/main/Screenshots/00%20-%20Architectural%20Diagram.png)

## Key Steps

Step 1: Authentication Enablement
In this step, I installed the Azure Machine Learning Extension which allows to interact with Azure Machine Learning Studio. I created a Service Principal (SP) account and associated it with my workspace. 

![Screenshot]( https://github.com/Mnarbekov/Machine-Learning-Engineer-with-Microsoft-Azure-Nanodegree-Program-Project-2/blob/main/Screenshots/01%20-%20Service%20Principle%20(SP)%20creation.png)

![Screenshot]( https://github.com/Mnarbekov/Machine-Learning-Engineer-with-Microsoft-Azure-Nanodegree-Program-Project-2/blob/main/Screenshots/02%20-%20Associate%20Workspace%20and%20Group%20with%20the%20SP.png)

Step 2: Automated ML Experiment

In this step, I registered the bankmarketing dataset, configured a compute cluster, created and successfully run Automated ML experiment in the Azure Machine Learning Studio.

![Screenshot]( https://github.com/Mnarbekov/Machine-Learning-Engineer-with-Microsoft-Azure-Nanodegree-Program-Project-2/blob/main/Screenshots/03%20-%20Dataset%20Registered.png)

![Screenshot]( https://github.com/Mnarbekov/Machine-Learning-Engineer-with-Microsoft-Azure-Nanodegree-Program-Project-2/blob/main/Screenshots/04%20-%20AutoML%20Completed.png)

![Screenshot]( https://github.com/Mnarbekov/Machine-Learning-Engineer-with-Microsoft-Azure-Nanodegree-Program-Project-2/blob/main/Screenshots/05%20-%20Experiment%20completed.png)

Step 3-4: Deploy the Best Model and Enabling Logging 

I selected the best model for the deployment using Azure Container Instance (ACI) and enabled Application Insights. Deploying a model allows to interact with the HTTP API service and interact with the model by sending data over POST requests.

![Screenshot]( https://github.com/Mnarbekov/Machine-Learning-Engineer-with-Microsoft-Azure-Nanodegree-Program-Project-2/blob/main/Screenshots/06%20-%20AutoML%20Best%20Model.png)

![Screenshot]( https://github.com/Mnarbekov/Machine-Learning-Engineer-with-Microsoft-Azure-Nanodegree-Program-Project-2/blob/main/Screenshots/07%20-%20Application%20Insights%20enabled.png)

![Screenshot]( https://github.com/Mnarbekov/Machine-Learning-Engineer-with-Microsoft-Azure-Nanodegree-Program-Project-2/blob/main/Screenshots/08%20-%20Logs.png)

Step 5: Swagger Documentation

In this step, I tested Swagger documentation for my model and endpoint.
Swagger is a tool that helps build, document, and consume RESTful web services like the ones you are deploying in Azure ML Studio. It further explains what types of HTTP requests that an API can consume, like POST and GET. Azure provides a swagger.json that is used to create a web site that documents the HTTP endpoint for a deployed model.

![Screenshot]( https://github.com/Mnarbekov/Machine-Learning-Engineer-with-Microsoft-Azure-Nanodegree-Program-Project-2/blob/main/Screenshots/09%20-%20Swagger.png)

Step 6: Consume Model Endpoints

In this step, I used the endpoint.py script to interact with the trained model. I modified the scoring_uri and the key to match the key for your service and the URI that was generated after the model deployment. The script runs against the API producing JSON output from the model.

![Screenshot]( https://github.com/Mnarbekov/Machine-Learning-Engineer-with-Microsoft-Azure-Nanodegree-Program-Project-2/blob/main/Screenshots/10%20-%20Endpoint.png)

Step 7: Create, Publish and Consume a Pipeline

In this step, I used the Jupyter Notebook provided in the starter files (aml-pipelines-with-automated-machine-learning-step) to create, publish and consume a pipeline. I updated the notebook to reflect my environment keys, URI, dataset, cluster, and model names, which were created in the previous steps.

Unfortunately, there is an issue in the code provided - it generates an error at the following step:
"import pickle
with open(best_model_output._path_on_datastore, "rb" ) as f:
best_model = pickle.load(f)
best_model"
I tried to run the Jupyter Notebook code provided in step 7 in my own Azure ML environment and in the Udacity Project 2 Lab Azure ML environment (to validate that the error is not due to my environment). It generates the same error in both environments. The code provided in the project needs to be reviewed and fixed.
I raised a technical support request - https://knowledge.udacity.com/questions/812435
The technical mentor can’t provide an advice/support for more than 7 days. 
I also create a support ticket - https://udacity.zendesk.com/hc/en-us/requests/1548452
There are no response for more than 5 days.

![Screenshot](https://github.com/Mnarbekov/Machine-Learning-Engineer-with-Microsoft-Azure-Nanodegree-Program-Project-2/blob/main/Screenshots/11%20-%20Pipeline%20scrip%20error.png)




## Screen Recording

Link to a screen recording of the project in action - https://www.youtube.com/watch?v=mQES1CLgmys

Screencast agenda:
1. AutoML Experiment
2. Deployed best model
3. API request via the terminal
4. Issue with the Step 7 – Pipeline 

Machine Learning Engineer with Microsoft Azure - Project 2 step 7. There is an issue in the code provided - it generates an error.
Raised tickets to Technical Mentor and Udacity Support – more than 7 days, no reply/solution:
https://knowledge.udacity.com/questions/812435
https://udacity.zendesk.com/hc/en-us/requests/1548452


## Further improvements

Steps to improve the project in the future:
1. Additional Benchmarking step can be performed to load-test the model
2. The pipeline script needs to be updated in the starter files and successfully ran

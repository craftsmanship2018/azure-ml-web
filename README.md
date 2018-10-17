# Azure Machine Learning Part II - Web App  

## Story  
Cars R Us have invested in a new machine learning model to help them with pricing vehicles.

They have a simple web front end and a poorly trained linear regression pricing algorithm which has learnt its information from some sample car data they have.

The dealership could really use your help to get their web app into a Dev-Ops CI/CD pipeline, deploy their machine learning model and have the web app package itself up with the latest version of the model as currently it is cumbersome and fraught with difficulties when trying to do a release.

They have also realised that their model is not quite as accurate as it could be and they are certain they are losing money hand over fist.

It has also been requested a new model is trained up and deployed without adversely affecting their business.

## Technology  
Their front end is a Python Flask web application which they wish to keep, the Machine Learning model was developed using Azure Notebooks. For an AI application like this, there are always two streams of work, data scientists building machine learning models and app developers building the application and exposing it to end users to consume and test.

The overall target is to build a continuous integration pipeline for an AI application. 

## Getting Started  
* Download this Web App
* Get it running locally (Note you will need the Machine Learning model created in Part I and test data)
* In order to run locally you will need the latest version of Python installed - https://www.python.org/downloads/
* Make sure the Python path is added to system path variable so you can use it in CMD
* Install Flask, Numpy and SkLearn using the following commands in cmd:
  * py -m pip install flask
  * py -m pip install numpy
  * py -m pip install sklearn
* After cloning the repo to somewhere locally you can navigate to the 'flaskwebapp' folder in a cmd prompt and load the app using the following command:
  * python app.py
* This will start the web server, you can then navigate to your browser and use localhost:5000 to contact the app
* To invoke the ML call use the localhost:5000/score url, this will return a coefficient score for your model

## Goal  
Build a CI/CD pipeline that will build and combine this web app with the necessary model and test data and deploy it in a repeatable fashion. This process should decouple the web app developers and data scientists, to make sure that their production app is always running the latest code with the latest ML model.
* Be triggered by a source code check in
* The build process should grab the latest model and test data from the company's Blob storage area
* It should then deploy to production

## Change Scenario  
A variation to the existing architecture could be consuming the ML application as an endpoint instead of packaging it in the app.

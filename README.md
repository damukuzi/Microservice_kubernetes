
## Project Overview

In this project, I aim tooperationalize a Machine Learning Microservice API. 

I was given a pre-trained, `sklearn` model that had been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project showcases the ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

MY project goal was to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project the following was accomplished:
* Testing project code using linting
* Completing a Dockerfile to containerize this application
* Deploying the containerized application using Docker and make a prediction
* Improving the log statements in the source code for this application
* Configuring Kubernetes and create a Kubernetes cluster
* Deploying a container using Kubernetes and make a prediction
* Uploading a complete Github repo with CircleCI to indicate that your code has been tested

## Setup the Environment

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally `brew cask install docker`
* Setup and Configure Kubernetes locally
`brew cask install virtualbox`
`brew cask install minikube`
* Create Flask app in Container
`docker build --tag udacityv1app .`
* Run via kubectl
`kubectl run udacityv1app\
    --image=$dockerpath\
    --port=80 --labels app=udacityv1app`

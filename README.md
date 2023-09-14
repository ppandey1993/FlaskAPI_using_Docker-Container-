This repository is for a project i am working on "A sample Python API using Flask and Dockerize it"

Step 1: Set Up Your Development Environment
Before you start, make sure you have Python and Docker installed on your system. You'll also need a text editor or integrated development environment (IDE) for coding.

Step 2: Create a Flask App
Create a directory for your project and a Python file for your Flask application. For example, create a file named app.py.

Step 3: Create a Requirements File
Create a requirements.txt file to specify your project's dependencies. In this case, you only need Flask.

Step 4: Create a Dockerfile
Create a Dockerfile in the same directory as your Flask app. This file describes how to build your Docker image.

Step 5: Build the Docker Image
Open a terminal, navigate to your project directory, and build the Docker image using the following command:

**docker build -t flask-sample-app .**
This command tells Docker to build an image named flask-sample-app using the current directory as the build context (note the . at the end).

Step 6: Run the Docker Container
After the image is built, you can run a Docker container from it:

**docker run -p 4000:80 flask-sample-app**

This command maps port 4000 on your host machine to port 80 inside the Docker container.

Step 7: Test Your Flask API
Open a web browser or use a tool like curl to access your Flask API at **http://localhost:4000/**. You should see "Hello, World!" displayed.

Part 2 of project is **Create Kubernetes deployment scripts for above and deploy the POD in the Kubernetes cluster**

Step 1: Install and Set Up Kubernetes
Make sure you have Kubernetes installed and configured on your local development environment or on your target cluster. You can use tools like Minikube for a local development environment or set up a cluster on a cloud platform like Google Kubernetes Engine (GKE), Amazon EKS, or Azure AKS.

Step 2: Create Kubernetes Deployment YAML File - Created in the master branch of this repo, Replace your-docker-image:tag with the name and tag of the Docker image you built in the previous steps.

Step 3: Apply the Deployment to Kubernetes

**kubectl apply -f flask-app-deployment.yaml**

Step 4: Expose the Deployment
To make your Flask API accessible from outside the cluster, you need to expose it using a Kubernetes Service. Create a Kubernetes service YAML file - added in Master branch, If you're running Kubernetes locally (e.g., Minikube), you can use NodePort type instead.

**kubectl apply -f flask-app-service.yaml**

Step 5: Access Your Flask API
Depending on your Kubernetes cluster setup, you might need to wait for the external IP to be assigned to the LoadBalancer service. You can check the status using:

**kubectl get svc flask-app-service**

Once you have the external IP (or the NodePort if using Minikube), you can access your Flask API by visiting that IP or using a tool like curl.







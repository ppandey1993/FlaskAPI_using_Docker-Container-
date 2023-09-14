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


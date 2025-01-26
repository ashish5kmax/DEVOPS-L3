# Docker Hello World Application

This is a simple "Hello World" application using Docker and Python. The app runs a Python script inside a Docker container that prints "Hello, World!" to the console.

## Prerequisites

Before getting started, ensure that you have Docker installed on your machine. If Docker is not installed, you can download and install it from the official [Docker website](https://www.docker.com/products/docker-desktop).

## Steps to Run the Application

### Step 1: Create the Project Directory
Create a directory for your Docker project.

```bash
mkdir docker-hello-world
cd docker-hello-world
```

pip install flask

# app.py
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)


Create the Dockerfile

* Use an official Python runtime as a parent image
FROM python:3.8-slim

* Set the working directory in the container
WORKDIR /usr/src/app

* Copy the current directory contents into the container
COPY . .

* Install Flask inside the container
RUN pip install --no-cache-dir -r requirements.txt

* Expose port 5000 for the Flask app
EXPOSE 5000

* Run the Flask app
CMD ["python", "app.py"]

req.txt
Flask==2.0.2

docker build -t flask-hello-world .


docker run -p 5000:5000 flask-hello-world

docker build -t hello-world .

docker run hello-world

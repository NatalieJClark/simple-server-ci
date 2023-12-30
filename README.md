# Docker Simple Server

## Introduction

- I made this project for Makers Module 5 - Cloud Deployment: Containerising & Deploying
- This is a simple web server that serves a single route.
- It shows the user a `Hello, world!` message.
- It is containerised with Docker using the `Dockerfile`.
- It uses Exoframe (Maker's toy cloud hosting system) to deploy to the cloud.

## Objectives

I used this project to:
- [x] Learn to containerise a web server using Docker.
- [x] Learn to explain how containerisation helps with deployment.
- [x] Learn to deploy a container to a toy cloud hosting system.

## Setup

To set up this project:

```bash
; pipenv install
; pipenv shell
; pytest           # Run the tests
; python app.py    # Run the server
```

To containerise using Docker:

```bash
# Make sure Docker is running
# Use the Dockerfile to build the Docker image
; docker build --tag my-flask-app .

# See the image in Docker's internal database
; docker images

# Run the image as a new container
; docker run --publish 5001:5000 my-flask-app
```
To deploy with Exoframe (Maker's toy cloud hosting system):
```bash
# Install NodeJS
; brew install node

# Install exoframe
; npm install exoframe -g

# Log in to the Makers exoframe server (this uses a .pem file given to me by Makers)
; exoframe login https://exoframe.xf.mkrs.link -k path/to/key.pem
Endpoint URL updated!
Logging in to: https://exoframe.xf.mkrs.link
? Username: # use natalieclark
Successfully logged in!

# Check it works
; exoframe ls 
No deployments found on https://exoframe.xf.mkrs.link!

# Configure the app to deploy
; exoframe config -d natalieclark-simple.xf.mkrs.link --port 5000

# Deploy the app
; exoframe deploy

# We can see the container start running by looking at the logs of the ID
; exoframe logs ID # Use the ID from the output of the deploy command

# Visit the URL to see the app running
; open https://natalieclark-simple.xf.mkrs.link

# When you want to update your server with the latest code, run:
; exoframe deploy --update
```

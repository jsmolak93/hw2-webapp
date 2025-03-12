SWE645 - Homework 2 Submission

Project Overview
----------------
This project involves deploying a web application using Docker, Kubernetes, and Jenkins as part of the SWE645 coursework. The project is hosted on AWS and includes a CI/CD pipeline using Jenkins to automate the deployment process.

AWS URLs
--------
- ip address: http://23.21.181.239
- Jenkins Dashboard: http://23.21.181.239:8080
- Web Application on Kubernetes: http://23.21.181.239:31000

Files Included in Submission
----------------------------
The zipped submission contains the following files:
- Source Code: All relevant files for the web application.
- Configuration Files:
  - Dockerfile - Used to containerize the application.
  - Jenkinsfile - Defines the CI/CD pipeline.
  - deployment.yaml - Kubernetes deployment configuration.
  - service.yaml - Kubernetes service configuration.
- Documentation:
  - README.txt (this file) - Contains installation instructions and project overview.
  - Video Demonstration - A recorded video demonstrating the setup, configuration, and successful execution of the project.

Installation and Setup Instructions
-----------------------------------
1. Set Up AWS Environment:
   - Launch an EC2 instance on AWS.
   - Install Docker, Kubernetes (kubectl), and Jenkins on the instance.

2. Clone Repository:
   git clone https://github.com/jsmolak93/hw2-webapp.git

3. Build and Push Docker Image:
   docker build -t jsmolak93/hw2-webapp:latest .
   docker push jsmolak93/hw2-webapp:latest

4. Deploy to Kubernetes:
   kubectl apply -f deployment.yaml
   kubectl apply -f service.yaml

5. Set Up Jenkins Pipeline:
   - Configure Jenkins credentials for GitHub and DockerHub.
   - Create a new Pipeline job in Jenkins.
   - Use the provided Jenkinsfile to automate the deployment.

6. Verify Deployment:
   - Access the web application at http://23.21.181.239:31000.
   - Ensure the Jenkins pipeline executes successfully.

References
----------
- Docker Documentation: https://docs.docker.com/
- Kubernetes Documentation: https://kubernetes.io/docs/
- Jenkins Documentation: https://www.jenkins.io/doc/
- AWS EC2 Instance Setup Guide

Notes
-----
This documentation provides a detailed guide to setting up and running the project. I've also included a detailed word document in the attachments. The included video further demonstrates the deployment steps for reference.

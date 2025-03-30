# DevOps Calculator Project
The DevOps Calculator Project is a simple yet effective calculator application implemented in Java. This project is designed to demonstrate the full DevOps lifecycle, including automated build, testing, Docker image creation, and deployment using Jenkins and Ansible.

# Feature
- Arithmetic operations (Square root, factorial, natural log, power)
- Automated unit testing with JUnit
- Containerized deployment using Docker
- CI/CD automation with Jenkins
- Infrastructure provisioning and deployment via Ansible
- Configurable and scalable architecture


## Project Structure
- calculator.java: Contains the implementation of the calculator application.
- CalculatorTest.java: Contains unit tests for the calculator application.
- Dockerfile: Specifies the instructions to build a Docker image for the calculator application.
- pom.xml: Maven Project Object Model file containing project configuration and dependencies.
- Jenkinsfile: Jenkins Pipeline script for automating the build, test, and deployment process.
- deploy.yaml: Ansible playbook for deploying the Docker image to the target environment.

# Technologies Used
- Java (JDK 11 or later) - Core programming language
- JUnit - Unit testing framework
- Apache Maven - Build and dependency management
- Docker - Containerization
- Jenkins - Continuous Integration and Deployment (CI/CD)
- Ansible - Deployment automation

## Prerequisites
Ensure the following prerequisites are met before running the project:

- Java Development Kit (JDK)
- Apache Maven
- Docker
- Jenkins
- Ansible

# Setup Instructions
1. Clone the Repository
git clone https://github.com/satya666666/Calculatorr
cd Calculator-main
2. Build the Project
mvn clean install
3. Run Unit Tests
mvn test
4. Build and Run Docker Container
docker build -t calculator-app .
docker run -p 8080:8080 calculator-app
5. Configure Jenkins Pipeline
  1. Open Jenkins and create a new pipeline project.
  2. In the Pipeline section, select Pipeline Script from SCM.
  3. Set SCM to Git and provide the repository URL.
  4. Save and build the pipeline to trigger automated testing and deployment.
6. Deploy Using Ansible
Ensure the target server is configured and accessible via SSH, then run:
ansible-playbook deploy.yaml

# CI/CD Workflow
1. Commit Code - Push changes to the repository.
2. Build & Test - Jenkins triggers automated testing via Maven and JUnit.
3. Containerization - Docker image is built and pushed to the registry.
4. Deployment - Ansible deploys the containerized application to the target environment.

# Contributing
Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch (feature-xyz).
3. Make your changes and commit.
4. Submit a pull request.

try the webhook for  triggering & how this works or not...

again checking the webhooks
 try for webhook




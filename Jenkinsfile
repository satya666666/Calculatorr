pipeline {
    // Specifies that the pipeline can run on any available agent
    agent any

    // Defines environment variables available throughout the pipeline
    environment {
        // Name of the Docker image to be built
        DOCKER_IMAGE_NAME = 'calculator'
        // URL of the GitHub repository containing the source code
        GITHUB_REPO_URL = 'https://github.com/satya666666/Calculatorr'
    }

    // Defines the stages of the pipeline
    stages {
        // Stage 1: Checkout source code from GitHub
        stage('Checkout') {
            steps {
                script {
                    // Checkout the 'main' branch from the specified GitHub repository
                    git branch: 'main', url: "${GITHUB_REPO_URL}"
                }
            }
        }

        // Stage 2: Build and test the application using Maven
        stage('Build and test') {
            steps {
                script {
                    // Execute Maven command to clean and package the application
                    // 'clean' removes previous build artifacts
                    // 'package' builds and packages the application
                    sh 'mvn clean package'
                }
            }
        }

        // Stage 3: Build Docker image from the application
        stage('Build Docker Image') {
            steps {
                script {
                    // Build Docker image using the specified name
                    // '.' indicates the Dockerfile is in the current directory
                    docker.build("${DOCKER_IMAGE_NAME}", '.')
                }
            }
        }

        // Stage 4: Push Docker image to Docker Hub
        stage('Push Docker Images') {
            steps {
                script {
                    // Configure Docker registry credentials
                    // Empty string as first parameter uses default registry (Docker Hub)
                    // 'DockerHub' refers to credentials ID stored in Jenkins
                    docker.withRegistry('', 'DockerHub') {
                        // Tag the built image with repository name and 'latest' tag
                        sh 'docker tag calculator satya582/calculator:latest'
                        // Push the tagged image to Docker Hub
                        sh 'docker push satya582/calculator'
                    }
                }
            }
        }

        // Stage 5: Deploy using Ansible
        stage('Run Ansible playbook') {
            steps {
                script {
                    // Execute Ansible playbook for deployment
                    // 'deploy.yaml' should contain the deployment configuration
                    ansiblePlaybook(
                        playbook: 'deploy.yaml'
                    )
                }
            }
        }
    }
}
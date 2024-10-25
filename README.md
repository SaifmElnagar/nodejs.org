---

# Node.js Kubernetes Deployment with Jenkins and ArgoCD

This project automates the deployment of a Node.js application to a local Kubernetes cluster using a CI/CD pipeline with Jenkins, Docker, and ArgoCD.

## Project Overview

The project deploys a Node.js application from a GitHub repository to a Kubernetes cluster running on Minikube. Using ArgoCD for continuous delivery, we automate the entire process with a Jenkins pipeline to streamline the build, test, and deployment phases.

### Prerequisites

- **Virtual Machines (VMs)**:
  - **Jenkins VM**: Hosts Jenkins and Docker.
  - **Minikube VM**: Hosts Minikube, kubectl, and ArgoCD.
- **Accounts**:
  - GitHub account
  - Docker Hub account

### Project Steps

#### 1. Jenkins Setup and Dockerization

1. **Fork the Repository**: Fork the [Node.js GitHub repository](https://github.com/nodejs/nodejs.org.git) to your GitHub account.
2. **Clone the Repository**: Clone the forked repository on your Jenkins VM.
3. **Build and Test Application Locally**: Ensure Node.js (version 18) is installed, and run unit tests.

![Screenshot from 2024-10-25 15-59-36](https://github.com/user-attachments/assets/f94b5e16-3b3f-48f9-84f6-0a0ff1c91cb3)

4. **Create Dockerfile**: Dockerize the application and push the Dockerfile to your GitHub repository.
5. **Set Up Jenkins Pipeline**: Automate the build and deployment in Jenkins. The pipeline stages include:
    - *Checkout code*
    - *Install dependencies*
    - *Run unit testing*
    - *Dockerize*
    - *Push Docker image to Docker Hub*

#### 2. Kubernetes Deployment

1. **Setup Minikube and ArgoCD**: Install Minikube and kubectl on the second VM and set up ArgoCD for automated deployments.
2. **Create Deployment Config**: Write a `deployment.yaml` file for Kubernetes configuration and push it to the GitHub repository.

## Pipeline Stages in Jenkins

```groovy
pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                // Add checkout commands here
            }
        }
        stage('Install Dependencies') {
            steps {
                // Add dependency installation commands here
            }
        }
        stage('Run Unit Testing') {
            steps {
                // Add testing commands here
            }
        }
        stage('Dockerize') {
            steps {
                // Add Docker build commands here
            }
        }
        stage('Push Docker Image') {
            steps {
                // Add Docker push commands here
            }
        }
    }
}
```

## Getting Started

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/nodejs.org.git
   ```
2. **Run the Jenkins Pipeline**: Execute the Jenkinsfile to deploy the app.

## License

This project is open-source, licensed under the [MIT License](LICENSE).

---


## Jenkins Pipeline 

![Screenshot from 2024-10-25 17-06-18](https://github.com/user-attachments/assets/c8cb2dc4-6276-415e-9381-2fc18a935c6d)

![Screenshot from 2024-10-25 17-7-16](https://github.com/user-attachments/assets/20744aac-8354-4439-b169-84aa6d8908e7)

![Screenshot from 2024-10-25 17-7-56](https://github.com/user-attachments/assets/34eae66a-70cb-4cab-9be4-aa6807b9ac3e)

![Screenshot from 2024-10-25 17-9-16](https://github.com/user-attachments/assets/34d922a6-e15e-4595-9e11-97f25829bc56)

![Screenshot from 2024-10-25 17-38-57](https://github.com/user-attachments/assets/a829f5fb-27c7-4597-86a0-867596af8b5d)



## Argo-cd 

![Screenshot from 2024-10-25 17-28-52](https://github.com/user-attachments/assets/b08a036e-8516-4dc5-abc7-14f8db65773a)

  
## Docker-Hub
![Screenshot from 2024-10-25 17-26-16](https://github.com/user-attachments/assets/f93fe22f-2546-45c0-992a-62d5a4bfbe22)






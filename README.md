# Reddit Clone App on Kubernetes

This project demonstrates how to deploy a Reddit clone app on Kubernetes and expose it to the world using Minikube as the cluster.

## Architecture Diagram
![Architecture Diagram](https://github.com/user-attachments/assets/cfd4b014-4171-46c5-ae8d-53dc44f32d8b)

## Prerequisites
Before you begin, you should have the following tools installed on your local machine:

- Docker
- Minikube cluster (Running)
- kubectl
- Git

## Installation
Follow these steps to install and run the Reddit clone app on your local machine:

1. **Clone the repository to your local machine**:
    ```sh
    git clone https://github.com/RaiAbhisekh192005/Reddit-Clone-Deployment.git
    ```

2. **Navigate to the project directory**:
    ```sh
    cd Reddit-Clone-Deployment
    ```

3. **Build the Docker image for the Reddit clone app**:
    ```sh
    docker build -t reddit-clone-app .
    ```

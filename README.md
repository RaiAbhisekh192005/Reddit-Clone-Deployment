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

## Steps

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

4. **Start Minikube (if not already started)**:
    ```sh
    minikube start
    ```

5. **Deploy the app to Kubernetes**:
    ```sh
    kubectl apply -f deployment.yaml
    ```

6. **Deploy the Service for deployment to Kubernetes**:
    ```sh
    kubectl apply -f service.yaml
    ```

7. **Enable Ingress in Minikube**:
    ```sh
    minikube addons enable ingress
    ```

8. **Expose the app as a Kubernetes service**:
    ```sh
    kubectl expose deployment reddit-deployment --type=NodePort --port=5000
    ```

9. **Create an Ingress resource**:
    ```sh
    kubectl apply -f ingress.yaml
    ```

10. **Verify that the application is running**:
    ```sh
    kubectl get pods
    kubectl get services
    kubectl get ingress
    ```

11. **Get the Minikube IP address**:
    ```sh
    minikube ip
    ```

12. **Add an entry to your `/etc/hosts` file**:
    - Edit the `/etc/hosts` file and add the following line (replace `MINIKUBE_IP` with the IP address from the previous step):
    ```sh
    MINIKUBE_IP  reddit-clone.local
    ```

13. **Access the application**:
    - Open a web browser and navigate to `http://reddit-clone.local`.

14. **(Optional) Clean up resources**:
    - To delete the deployment and services, run:
    ```sh
    kubectl delete -f deployment.yaml
    kubectl delete -f service.yaml
    kubectl delete -f ingress.yaml
    ```

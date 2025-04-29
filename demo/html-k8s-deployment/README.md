# HTML Kubernetes Deployment

This project demonstrates how to deploy a simple HTML application in a Kubernetes environment. Below are the instructions for building the Docker image, deploying it to Kubernetes, and accessing the application.

## Project Structure

```
html-k8s-deployment
├── k8s
│   ├── deployment.yaml
│   ├── service.yaml
│   └── ingress.yaml
├── src
│   └── index.html
├── Dockerfile
├── .dockerignore
└── README.md
```

## Prerequisites

- Docker installed on your machine
- Kubernetes cluster (e.g., Minikube, GKE, EKS, AKS)
- kubectl command-line tool installed and configured

## Building the Docker Image

1. Navigate to the project directory:
   ```
   cd html-k8s-deployment
   ```

2. Build the Docker image:
   ```
   docker build -t html-k8s-app .
   ```

## Deploying to Kubernetes

1. Apply the deployment configuration:
   ```
   kubectl apply -f k8s/deployment.yaml
   ```

2. Apply the service configuration:
   ```
   kubectl apply -f k8s/service.yaml
   ```

3. Apply the ingress configuration (if applicable):
   ```
   kubectl apply -f k8s/ingress.yaml
   ```

## Accessing the Application

- If using a `NodePort` service, you can access the application using:
  ```
  http://<NodeIP>:<NodePort>
  ```

- If using an ingress, access the application using the specified hostname.

## Cleanup

To delete the deployed resources, run:
```
kubectl delete -f k8s/deployment.yaml
kubectl delete -f k8s/service.yaml
kubectl delete -f k8s/ingress.yaml
``` 

## License

This project is licensed under the MIT License.
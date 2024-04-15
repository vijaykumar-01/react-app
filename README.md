# Deploying a React App in MicroK8s

This guide provides step-by-step instructions for deploying a React app in a MicroK8s cluster.

## Prerequisites

- MicroK8s installed and running on your system.
- Docker installed on your system.
- React app code.

## Steps

1. **Build Docker Image:**

   Build a Docker image for your React app using the provided Dockerfile.

   ```bash
   docker build -t your-image-name:tag .
   ```

2. **Push Docker Image:**

   If you want to deploy your Docker image to a remote repository, push the image to the repository.

   ```bash
   docker push your-image-name:tag
   ```

3. **Deploy to MicroK8s:**

   Apply the Kubernetes manifest file (`react-manifest.yaml`) to deploy your application to MicroK8s.

   ```bash
   kubectl apply -f react-manifest.yaml
   ```

4. **Verify Deployment:**

   Check the status of your deployment:

   ```bash
   kubectl get pods
   kubectl get svc
   kubectl get ing
   ```

5. **Access the Application:**

   Since we have not hosted a domain, we'll use NodePort to expose the application. 

   Get the Node IP:

   ```bash
   kubectl get nodes -o wide
   ```

   Take the Node IP and the allocated NodePort and browse it:

   ```
   https://<Node-IP>:<Node-Port>
   ```

   Now you can access the application via a browser.

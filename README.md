# Kubernetes Crash Course

Tutorial followed from TechWorld with Nana's YouTube Channel

## mongo-config.yaml
Refer to Kubernetes Documentation on configMap files to generate the format

## mongo-secret.yaml
Refer to Kubernetes Documentation on secret config files to generate the format
-   Use the terminal to encode the user and password in base64, not in plaintext

## mongo.yaml
Refer to Kubernetes Documentation on deployment to generate the format

# Final Step for App: Deploying all resources to Minikube cluster
Ensure that Minikube is running
-   ConfigMap and Secret must exist before deployment
    -   use <code>kubectl apply -f mongo-config.yaml</code> command (for app config)
    -   use <code>kubectl apply -f mongo-secret.yaml</code> command (for app secret)
    -   use <code>kubectl apply -f mongo.yaml</code> command (for service and deployment)
    -   use <code>kubectl apply -f mongo-webapp.yaml</code> command (deploys the web application)
-   using the <code>kubectl get pod</code> to get the pod/ components/ resources
    - using <code>kubectl get all</code> displays all components created in the cluster (pods, services and deployments)
    - note that configMap and secret will not appear (use <code>kubectl get configmap</code> and <code>kubectl get secret</code>)
    - use <code>kubectl get svc</code> to validate browser accessibility of app
    - use <code>kubectl get node</code>, then <code>kubectl get node -o wide</code> to get IP address
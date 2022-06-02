NGINX PHP 7 K8S Deployment
--------------------------

What is this?
=============
A simple template for starting a PHP 7 application served by NGINX, using
 Kubernetes (K8S) deployment object. This also works with Minikube, to aid in
 learning how to use K8S on a local machine.

How does it work?
=================

### Locally via Minikube
1. Start [Minikube](https://github.com/kubernetes/minikube):

    ```bash
    $ minikube start
    Starting local Kubernetes cluster...
    Kubectl is now configured to use the cluster.
    ```

2. Create a K8S service:

    ```bash
    $ kubectl create -f resources/kubernetes/services/local-service.yaml
    service "local-service" created
    ```
    
3. Create a K8S deployment:

    ```bash
    $ kubectl create -f resources/kubernetes/deployments/local-deployment.yaml
    deployment "local-deployment" created
    ```
4. Get the URL for the NGINX service that will serve your PHP 7 app:

    ```bash
    $ minikube service nginx-service --url
    ```
    Note, you may see this message until the pods are ready:
    > Waiting, endpoint for service is not ready yet...


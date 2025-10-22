Kubernetes NGINX Deployment with ClusterIP and Ingress
Tasks Performed

Use the previous deployment

Reused the existing deployment configuration from the previous assignment.

Deploy an NGINX deployment of 3 replicas

Created a Deployment manifest for NGINX with 3 replicas.

YAML snippet:

Create an NGINX service of type ClusterIP

Exposed the NGINX deployment internally using a ClusterIP service.

YAML snippet:

Create an Ingress service

Configured ingress to route traffic to the NGINX service.

Example YAML (NGINX Ingress Controller assumed to be installed):
Verification Steps

Check deployment and replicas

kubectl get deployments
kubectl get pods


Check ClusterIP service

kubectl get svc


Check ingress routing

Access the service using the hostname configured in the ingress (nginx.example.com) after updating /etc/hosts or DNS.

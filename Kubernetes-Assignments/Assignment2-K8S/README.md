Kubernetes NGINX NodePort Service Assignment
Tasks Performed

Use Previous Deployment

Utilized the existing NGINX deployment created in the previous assignment.

Deployment has 3 replicas running on the cluster.

Create a NodePort Service

Exposed the NGINX deployment using a NodePort service.

YAML file used (nginx-nodeport.yaml):

Applied the service:

kubectl apply -f nginx-nodeport.yaml


Verify NodePort Service

Checked the service details:

kubectl get svc


Output shows nginx-nodeport with NodePort 30001.

Accessed the service on a browser using:

http://<Node-IP>:30001


Verified that the NGINX default page is accessible.

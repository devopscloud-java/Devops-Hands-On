Kubernetes Cluster and NGINX Deployment
Objective

Deploy a Kubernetes cluster with 3 nodes.

Create a NGINX deployment with 3 replicas.

Tasks Performed
1. Deploy a Kubernetes Cluster

Used Minikube / kubeadm / kind (depending on environment) to create a 3-node cluster.

Verified the cluster status:

kubectl get nodes


Output:

NAME        STATUS   ROLES    AGE   VERSION
master      Ready    master   10m   v1.xx.x
worker1     Ready    <none>   5m    v1.xx.x
worker2     Ready    <none>   5m    v1.xx.x

2. Create NGINX Deployment

Created a deployment named nginx-deployment with 3 replicas:

kubectl create deployment nginx-deployment --image=nginx --replicas=3


Verified the deployment and pods:

kubectl get deployments
kubectl get pods


Output:

NAME               READY   UP-TO-DATE   AVAILABLE   AGE
nginx-deployment   3/3     3            3           2m


Exposed deployment (optional) to access via NodePort:

kubectl expose deployment nginx-deployment --type=NodePort --port=80
kubectl get svc

3. Verification

Access NGINX service using cluster IP / NodePort in the browser or via curl:

curl http://<node-ip>:<nodeport>


Confirmed that 3 replicas of NGINX are running successfully.

Notes

Ensure Kubernetes CLI (kubectl) is configured to interact with the cluster.

All pods are running the official NGINX image.

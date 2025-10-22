Kubernetes Deployment Update - README
Task Overview

The objective of this task is to update an existing Kubernetes deployment by increasing the number of replicas from the previous configuration to 5.

Steps Performed

Used the Previous Deployment

Identified the existing deployment (e.g., nginx-deployment).

Checked the current configuration using:

kubectl get deployments
kubectl describe deployment <deployment-name>


Updated Replicas to 5

Scaled the deployment to 5 replicas using one of the following methods:

Method 1: Using kubectl scale

kubectl scale deployment <deployment-name> --replicas=5


Method 2: Editing Deployment YAML

kubectl edit deployment <deployment-name>


Changed the value under spec.replicas to 5.

Saved and exited the editor.

Verified the Update

kubectl get deployments
kubectl get pods


Confirmed that 5 pods are now running for the deployment.

Notes

Ensure the cluster has sufficient resources to run the additional pods.

Existing services will automatically handle traffic to the new pods.


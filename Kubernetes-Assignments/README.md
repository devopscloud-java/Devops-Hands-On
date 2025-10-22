Kubernetes Assignments README
Overview

This directory contains all the Kubernetes assignments completed as part of the learning/training program. Each assignment demonstrates key Kubernetes concepts including deployments, services, ingress, scaling, and container management.

Prerequisites

Kubernetes cluster (Minikube, kind, or cloud-based cluster)

kubectl installed

Helm (for advanced assignments)

Docker (for container images)

How to Run

Clone the repository:

git clone <repo-url>
cd kubernetes-assignments


Apply the YAML files for the required assignment:

kubectl apply -f <assignment-folder>/


Verify the deployment and services:

kubectl get pods
kubectl get svc
kubectl get ingress

Notes

All assignments are tested on a local Minikube cluster.

Services are configured according to assignment requirements (ClusterIP, NodePort, or LoadBalancer).

Ingress is configured using default NGINX ingress controller.

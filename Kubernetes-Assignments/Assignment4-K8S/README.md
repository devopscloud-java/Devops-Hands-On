
Kubernetes Service Update: Change Service Type to ClusterIP
Tasks Performed

Used the previous deployment

Existing deployment from the prior assignment was used as-is.

Changed the service type to ClusterIP

Edited the service YAML file to set the type as ClusterIP.

Applied the updated service to the cluster.

Commands Used
# Apply previous deployment if not already applied
kubectl apply -f <previous-deployment-file>.yaml

# Edit the service to change type to ClusterIP
kubectl edit svc <service-name>
# OR update via YAML
kubectl apply -f <updated-service-file>.yaml

# Verify the service type
kubectl get svc

Verification
Run kubectl get svc to ensure the service type shows as ClusterIP.

ClusterIP services are accessible only within the cluster, not from external nodes.
Run kubectl get svc to ensure the service type shows as ClusterIP.

ClusterIP services are accessible only within the cluster, not from external nodes.

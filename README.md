# task5


TASK 5: Build a Kubernetes Cluster Locally with Minikube

Steps:

1. Install Minikube & Start Cluster:
   minikube start

2. Deploy application:
   kubectl apply -f deployment.yaml

3. Expose application:
   kubectl apply -f service.yaml

4. Verify pods and services:
   kubectl get pods
   kubectl get svc

5. Scale deployment:
   kubectl scale deployment myapp-deployment --replicas=3

6. Check logs and details:
   kubectl describe pod <pod-name>
   kubectl logs <pod-name>

7. Access App:
   minikube service myapp-service --url

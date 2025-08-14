How to deploy the app to k8s:
  kubectl delete pod {pod names} - delete all old pods. 
  kubectl apply -f deployment.yml - use the deployment manifest.
  kubectl apply -f hpa.yml - use the HorizontalPodAutoscaler manifest.
  
Choice of resource requests and limits:
  requests:
    memory: "64Mi"
    cpu: "250m"
  limits:
    memory: "128Mi"
    cpu: "500m"

Choice of HPA configuration:
  CPU Utilization: 50
  Memory Utilization: 50

Strategy configuration:
 Default configuration.
  RollingUpdate:
      maxUnavailable: 1
      maxSurge: 1

How to access the app after deployment:
  https://localhost:30008
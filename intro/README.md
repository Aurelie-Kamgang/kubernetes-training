## Deploying the application with a pod and deployments
### prerequisite:
- install k8s
### Instructions:
1. Deploy with a pod
- apply: `kubectl apply -f pod.yaml`
- verification:
    1. `kubectl get pods`
    2. make our app accessible by exposing it on the pod 8080: `kubectl port-forward simple-webapp-color 8080:8080 --address 0.0.0.0`
 
 2. Deploy with a deployment:
 - apply: `kubectl apply -f nginx-deployment.yaml`
 - test:
       - `kubectl get deployments`
       - `kubectl get pods`
       - `kubectl get resplicasets -o wide`
- make our app accessible by exposing it on the pod 8080:
`exposé mon application: kubectl port-forward simple-webapp-color 8080:8080 --address 0.0.0.0

#network-kubernetes

- creation of two pods that do loadbalance through the nodeport service.
- Prerequisites: install k8s

1. apply: `kubectl apply -f namespace.yml`
verify: `kubectl get namespace`

2. apply: `kubectl apply -f pod-red.yml -n production`
verify: `kubectl get pods -n production`

3. apply: `kubectl apply -f pod-blue.yml -n production`
verify: `kubectl get pods -n production`

4. apply: `kubectl apply -f service-nodeport-web.yml -n production`
verify: `kubectl get svc -n production`
`kubectl describe svc name_service -n production

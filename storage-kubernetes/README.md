# Storage-kubernetes

- Deploy mysql with volume storage and then pv and pvc storage
- prerequisites: Install k8s
### Volume storage
Instructions:
1. Create the directory where the volume will be mounted locally:
`mkdir /data-volume`
2. Apply:
`kubectl apply -f myqsl-volume.yml`
3. Verify: `kubectl get pod`
				 `kubectl describe pod name_pod`
				 `ls /data-volume`
4. Delete the pod: `kubectl delete pod name_pod`
5. Check if the data is still present despite the pod being deleted:`ls /data-volume`

### PV and PVC storage
Instructions:
1. Apply pv.yml  to consume the storage: `kubectl apply -f pv.yml`
2. Verify: `kubectl get pv`
				`kubectl describe pv name_pod`
3. Apply pvc.yml  to consume the pv: `kubectl apply -f pvc.yml`
4. Verify: `kubectl get pvc`
				`kubectl describe pvc name_pod`
5. Apply mysql-pv.yml to consume pvc: `kubectl apply -f mysql-pv.yml`
6. Verify: `kubectl get pods`
				`kubectl describe name_pod`

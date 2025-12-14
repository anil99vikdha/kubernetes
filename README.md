# Kubernetes Documentation

kubernetes official documentation - https://kubernetes.io/docs/home/

minikube document - https://kubernetes.io/docs/tutorials/hello-minikube/


## Imperative commands 
`kubectl run nginx --image=nginx --restart=Never`

`kubectl run webserver-pod \
      --image nginx:1.14.2 \
      --restart=Never \
      --labels=app=webserver,environment=production \
      --annotations description="This pod runs the nginx web server"`

### To get complete details of a pod
`kubectl describe pod webserver-pod`

### To get the details of this pod in yaml format
`kubectl get pod webserver-pod -o yaml`

### To run a pod and remove after exiting
`kubectl run -i --tty testpod \
     --image=busybox \
     --rm --restart=Never -- sh`

## Declarative approach and generate yaml. 

`kubectl run webserver-pod --image=nginx --dry-run=client -o yaml > pod.yaml`

## Running a multi container port
`kubectl run multi-container-pod \
     --image nginx \
     --dry-run=client -o yaml > multi-container-pod.yaml`

`kubectl logs -f multi-container-pod -c `
`kubectl logs -f multi-container-pod -c webserver`
`kubectl logs -f multi-container-pod -c log-reader`

### log into container
`kubectl exec -it multi-container-pod -c webserver -- sh`
`kubectl exec -it multi-container-pod -c log-reader -- sh`

### port forwat to access webserver
`kubectl port-forward multi-container-pod 8080:80 &`

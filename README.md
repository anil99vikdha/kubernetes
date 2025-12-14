# Kubernetes Documentation

kubernetes official documentation - https://kubernetes.io/docs/home/

minikube document - https://kubernetes.io/docs/tutorials/hello-minikube/


## Imperative commands 
kubectl run nginx --image=nginx --restart=Never

`kubectl run webserver-pod \
      --image nginx:1.14.2 \
      --restart=Never \
      --labels=app=webserver,environment=production \
      --annotations description="This pod runs the nginx web server"`

`kubectl describe pod webserver-pod`
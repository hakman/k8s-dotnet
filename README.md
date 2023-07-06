```
docker build -t hello:v1 .
kubectl cluster-info
kubectl api-resources
kubectl config view
kubectl create deployment hello --image hello:v1 --port 80
kubectl create service loadbalancer hello --tcp 80:80
kubectl describe service hello
kubectl describe endpoints hello
kubectl port-forward service/hello 8080:80
```

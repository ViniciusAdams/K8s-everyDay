Day 9:




Day 10:
What are namespaces?
It divides and separetes cluster into diferent namespaces, for example the kubesystem is a namespace created by default by kubernetes during its creation
Different permission can be assigned to each one of these namespaces
For example you can create differen namespaces for a test and a prod namespace a ngix pod that lives inside of prod can communicate with a redis that lives inside of the same namespace.

These are default namespaces
NAME                 STATUS   AGE
default              Active   23d
kube-node-lease      Active   23d
kube-public          Active   23d
kube-system          Active   23d
local-path-storage   Active   23d

And for example if you would like to check what is running inside of a specific namespace you can run

kubectl get all --namespace=kube -system or
kubectl get all -n kube-system

this can be used to create a namespace

apiVersion: v1 
kind: Namespace
metadata:
  name: demo

and if you wish to delete it you can run kubectl delete ns/demo

in order to create a deployment inside of a namespace 

kubectl create deploy nginx-demo --image=nginx -n demo

and in order to get it kubectl get deploy -n demo

In order to acess deploymenyts in another namespaces that can be done using the ipadreess but in order to access a service that must be done using a FQDN
# make sure you have a kubenrnte tool ready to work with 
# for this project i choose minkune a single node cluster but for minkube to work there must be docker deskstop running on ur system

# create a prpject folder 
 argocd-deployment-kubenrnetes
 
# start your minkube by running the command below
minikube start

# the command above get ur single node cluster ready coipled with the kubernetes cli interface call kubectl

# now run the command below

minikube status

minikube
type: Control Plane
host: Running
kubelet: Running
apiserver: Running
kubeconfig: Configured

# Forward Ports
k get services -n argocd
kubectl port-forward service/argocd-server -n argocd 8080:443
Forwarding from 127.0.0.1:8080 -> 8080


#use below to get the argo cd ui
127.0.0.1:8080






# Get Credentials
#The usernemae is admin but use the below to get the passowrd

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d


## or another method

kubectl -n argocd get secret argocd-initial-admin-secret -o yaml
apiVersion: v1
data:
  password: SklsN0llczB4SUJXYlVKag==
kind: Secret
metadata:
  creationTimestamp: "2024-10-17T10:06:09Z"
  name: argocd-initial-admin-secret
  namespace: argocd
  resourceVersion: "1330639"
  uid: 0fa80383-d1f3-4048-973c-9cf833a6af38
type: Opaque


# Now decode the password by running this command below

echo SklsN0llczB4SUJXYlVKag== | base64 -d 

JIl7Ies0xIBWbUJj%  



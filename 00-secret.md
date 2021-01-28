To create the secret:


kubectl create secret generic -n cluster-1 root-ca --from-file=./ssl/certs/ca
kubectl create secret generic -n cluster-1 etcd-cert --from-file=./ssl/certs/etcd
kubectl create secret generic -n cluster-1 apiserver-certs --from-file=./ssl/certs/apiserver 
kubectl create secret generic -n cluster-1 controller-certs --from-file=./ssl/certs/controller
kubectl create secret generic -n cluster-1 scheduler-certs --from-file=./ssl/certs/scheduler 
kubectl create secret generic -n cluster-1 proxy-certs --from-file=./ssl/certs/proxy 
kubectl create secret generic -n cluster-1 service-account-cert --from-file=./ssl/certs/sa 

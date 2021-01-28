# Needed Certificate Authorities:

* Kubernetes CA (User and services authentication, apiserver -> Kubelet auth)
* Kubernetes Proxy CA (apiservice front-proxy)
* ETCD CA (comms between apiserver -> etcd and between etcds nodes on cluster)

# Needed Public/Private Keys

## ETCD
* Issued by ETCD CA
  * etcd-server.crt and etcd-server.key (--cert-file && --key-file)
  * etcd-peers.crt and etcd-peers.key (--peer-cert-file & --peer-key-file)

## APIServer
* Issued by Kubernetes CA
  * apiserver.key and apiserver.crt (--tls-cert-file && --tls-private-key-file)
  * service-accounts.key and service-accounts.crt (--service-account-signing-key-file && --service-account-key-file)
  * apiserver-kubelet.crt and apiserver-kubelet.key (--kubelet-client-certificate && --kubelet-client-key)

* Issued by Front Proxy CA
  * front-proxy-client.key and front-proxy-client.crt (--proxy-client-cert-file && --proxy-client-key-file)

* Issued by ETCD CA
  * apiserver-etcd-client.key and apiserver-etcd-client.crt (--etcd-certfile && --etcd-keyfile)

## Controller Manager
* Issued by Kubernetes CA
  * controller-manager.crt and controller-manager.key (inside controller-manager.conf)
  * service-accounts.key (--service-account-private-key-file)

## Scheduler
* Issued by Kubernetes CA
  * scheduler.crt and scheduler.key (inside scheduler.conf)
# Pre Reqs:

* A running Kubernetes Cluster to be the bucket of the other clusters to be provisioned
* This running cluster needs a Ingress Controller up and running. It's highly recommended to use João Morais [haproxy-ingress](https://github.com/jcmoraisjr/haproxy-ingress) which has been battle tested for this
* A running Certificate Authority (or multiple) to generate the necessary certificates. The [Kubernetes the Hard Way](https://github.com/kelseyhightower/kubernetes-the-hard-way/blob/master/docs/04-certificate-authority.md) might be enough, but using a Hashicorp Vault + Cert-manager for automation would be better (coming soon!)

# TODOs
* Automate the certificate generation AND/OR post examples using cfssl
* ETCD should run a minimum of three replicas, maybe as a stateful set
* Liveness, readiness and startup probes needs to be re-inserted again
* Test the provisioning of kubelet/nodes
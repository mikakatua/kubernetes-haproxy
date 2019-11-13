# kubernetes-haproxy
Sample HAProxy configuration as a **self-provisioned edge** for Kubernetes

![Using a self-provisioned edge](https://kubernetes.github.io/ingress-nginx/images/baremetal/user_edge.jpg)

## Usage
1. Setup the NGINX Ingress Controller. Follow the [steps for bare-metal using NodePort](https://kubernetes.github.io/ingress-nginx/deploy/#bare-metal)
2. Modify the ports in the `haproxy.cfg` file ans set your own node ports allocated to the ingress-nginx service.
3. You can run the HAProxy in a container which have access to the Kubernetes nodes. For example:
```
docker run --net host -d --name kubernetes-haproxy -v $PWD/haproxy.cfg:/usr/local/etc/haproxy/haproxy.cfg haproxy
```

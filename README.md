# oss-ecosystem-kind
Automation to build Kind images for ppc64le.

# kind installation
For installation, you can check out the official documentation on the Kind page - https://kind.sigs.k8s.io/docs/user/quick-start#installation. 
```
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.16.0/kind-linux-ppc64le
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind
```

# Creating a cluster
Once you have Kind installed, you can create a Kubernetes cluster by running the below command:

``` 
kind create cluster --image ghcr.io/ibm/kind-node
```

To list cluster, run the command ```kind get clusters```, which outputs:

```
kind
kind-multi-node
```

In order to interact with a specific cluster, you need to specify the cluster name as a context in kubectl as:
``` 
kubectl cluster-info --context kind-kind
```

To delete a cluster, use the command ```kind delete cluster``` with optional ```--name``` flag. If the flag is not specified, kind will use the default cluster context name ```kind``` and delete that cluster.

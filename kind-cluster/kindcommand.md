## KIND commands
**Create the Cluster**
Run the following command to create the Kubernetes cluster using the `kind-config.yml`:
```bash
kind create cluster --name sree-multi --config kind-config.yml
```
You can use the `kubectl config get-contexts` command to list all the contexts configured in your Kubernetes configuration file (`~/.kube/config`). A context in Kubernetes includes a combination of a **cluster**, a **user**, and a **namespace**.
kubectl config get-contexts

**Verify the Cluster**
Once the cluster is created, you can verify it using kubectl:
```bash
kubectl cluster-info --context kind-sree-multi
```
**Access the Cluster**
```bash
kubectl get nodes
```
**Switch Contexts:**
```bash
kubectl config use-context <context-name>
```
**Deleting the Cluster**
```bash
kind delete cluster --name sree-multi
```

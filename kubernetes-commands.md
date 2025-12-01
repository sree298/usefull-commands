# ☸ Kubernetes (kubectl) Commands Cheat Sheet

## 🔍 Cluster & Node Information
| Command | Description |
|--------|-------------|
| `kubectl version` | Display kubectl & cluster version |
| `kubectl cluster-info` | Show cluster information |
| `kubectl get nodes` | List all nodes in cluster |
| `kubectl describe node <node-name>` | Detailed node information |

---

## 📦 Pods
| Command | Description |
|--------|-------------|
| `kubectl get pods` | List pods in default namespace |
| `kubectl get pods -A` | List pods across all namespaces |
| `kubectl describe pod <pod>` | Detailed pod info |
| `kubectl delete pod <pod>` | Delete a pod |
| `kubectl exec -it <pod> -- /bin/bash` | SSH into pod |
| `kubectl logs <pod>` | View pod logs |
| `kubectl logs <pod> -f` | Stream logs in real time |

---

## 🧠 Deployments
| Command | Description |
|--------|-------------|
| `kubectl get deployments` | List deployments |
| `kubectl describe deployment <name>` | Describe deployment |
| `kubectl create deployment <name> --image=<image>` | Create deployment |
| `kubectl delete deployment <name>` | Delete deployment |
| `kubectl scale deployment <name> --replicas=<num>` | Scale pods |
| `kubectl rollout status deployment <name>` | Deployment rollout status |
| `kubectl rollout undo deployment <name>` | Roll back deployment |

---

## 🛠 Services
| Command | Description |
|--------|-------------|
| `kubectl get svc` | List services |
| `kubectl describe svc <name>` | Describe service |
| `kubectl expose deployment <name> --type=NodePort --port=<port>` | Expose deployment as service |
| `kubectl delete svc <name>` | Delete service |

---

## 🏗 Namespaces
| Command | Description |
|--------|-------------|
| `kubectl get namespaces` | List namespaces |
| `kubectl create namespace <name>` | Create namespace |
| `kubectl delete namespace <name>` | Delete namespace |
| `kubectl config set-context --current --namespace=<namespace>` | Switch namespace |

---

## 🧾 ConfigMaps & Secrets
| Command | Description |
|--------|-------------|
| `kubectl get configmaps` | List configmaps |
| `kubectl create configmap <name> --from-literal=key=value` | Create configmap |
| `kubectl get secrets` | List secrets |
| `kubectl create secret generic <name> --from-literal=key=value` | Create secret |

---

## 💾 Persistent Volumes & Claims
| Command | Description |
|--------|-------------|
| `kubectl get pv` | List Persistent Volumes |
| `kubectl get pvc` | List Persistent Volume Claims |

---

## 📝 Apply & Manage YAML
| Command | Description |
|--------|-------------|
| `kubectl apply -f file.yaml` | Apply configuration |
| `kubectl delete -f file.yaml` | Delete resource |
| `kubectl edit <resource> <name>` | Edit live configuration |

---

## 📊 Resource Monitoring
| Command | Description |
|--------|-------------|
| `kubectl top nodes` | View node resource usage |
| `kubectl top pods` | View pod resource usage |

---

## 🚀 Example Deployment
```bash
kubectl create deployment nginx --image=nginx
kubectl expose deployment nginx --type=NodePort --port=80
```

# Kubernetes Kubectl Command Cheat Sheet

## 🧭 Kubectl Context and Configuration
| Command | Description |
|--------|-------------|
| `kubectl config view` | Show merged kubeconfig settings |
| `kubectl config get-contexts` | Display list of contexts |
| `kubectl config current-context` | Display the current context |
| `kubectl config use-context my-cluster-name` | Set default context to `my-cluster-name` |
| `kubectl config set-cluster my-cluster-name` | Set a cluster entry in kubeconfig |

---

## 📦 Creating Objects
| Command | Description |
|--------|-------------|
| `kubectl apply -f ./my-manifest.yaml` | Create resources |
| `kubectl apply -f ./my1.yaml -f ./my2.yaml` | Create from multiple files |
| `kubectl apply -f ./dir` | Create all resources in a directory |
| `kubectl apply -f https://git.io/vPieo` | Create resources from URL |
| `kubectl create deployment nginx --image=nginx` | Start a single instance of Nginx |

---

## 🔍 Viewing and Finding Resources

### Get Commands
| Command | Description |
|--------|-------------|
| `kubectl get services` | List all services |
| `kubectl get pods --all-namespaces` | List all pods in all namespaces |
| `kubectl get pods -o wide` | List pods in detail |
| `kubectl get deployment my-dep` | List a specific deployment |
| `kubectl get pods` | List pods in namespace |
| `kubectl get pod my-pod -o yaml` | Get YAML of a pod |
| `kubectl get pods --show-labels` | Show labels on all pods |

### Describe Commands
| Command | Description |
|--------|-------------|
| `kubectl describe nodes my-node` | Detailed node info |
| `kubectl describe pods my-pod` | Detailed pod info |

---

## 🔄 Updating Resources
| Command | Description |
|--------|-------------|
| `kubectl set image deployment/frontend www=image:v2` | Rolling update |
| `kubectl rollout history deployment/frontend` | Check deployment history |
| `kubectl rollout undo deployment/frontend` | Rollback last deployment |
| `kubectl rollout undo deployment/frontend --to-revision=2` | Rollback to revision 2 |
| `kubectl rollout status -w deployment/frontend` | Watch deployment rollout |
| `kubectl rollout restart deployment/frontend` | Restart deployment |
| `kubectl expose rc nginx --port=80 --target-port=8000` | Create service for nginx RC |
| `kubectl label pods my-pod new-label=awesome` | Add a label |
| `kubectl label pods my-pod new-label-` | Remove a label |

---

## 📝 Editing Resources
| Command | Description |
|--------|-------------|
| `kubectl edit svc/<service-name>` | Edit service |
| `kubectl edit deployment/<deployment-name>` | Edit deployment |

---

## 📈 Scaling Resources
| Command | Description |
|--------|-------------|
| `kubectl scale --replicas=3 rs/foo` | Scale replicaset |
| `kubectl scale --replicas=3 -f foo.yaml` | Scale resource from file |

---

## 🗑️ Deleting Resources
| Command | Description |
|--------|-------------|
| `kubectl delete -f ./pod.json` | Delete using manifest file |
| `kubectl delete pod unwanted --now` | Delete pod immediately |
| `kubectl delete pod,service baz foo` | Delete pods & services |
| `kubectl delete pods,services -l name=myLabel` | Delete with label |
| `kubectl -n my-ns delete pod,svc --all` | Delete all in namespace |
| ```bash
kubectl get pods -n mynamespace --no-headers=true \
| awk '/pattern1|pattern2/{print $1}' \
| xargs kubectl delete -n mynamespace pod
``` | Delete pods matching pattern |

---
```
## 🏃 Interacting with Running Pods
| Command | Description |
|--------|-------------|
| `kubectl logs my-pod` | Dump pod logs |
| `kubectl logs -f my-pod` | Stream logs |
| `kubectl logs -f my-pod -c my-container` | Stream logs from container |
| `kubectl port-forward my-pod 5000:6000` | Port forward |
| `kubectl exec my-pod -- ls /` | Run command in pod |
| `kubectl exec -it my-pod -- /bin/sh` | Interactive shell |
| `kubectl exec my-pod -c my-container -- ls /` | Exec in specific container |

---

## 📁 Copying Files & Directories
| Command | Description |
|--------|-------------|
| `kubectl cp /tmp/foo_dir my-pod:/tmp/bar_dir` | Copy dir to pod |
| `kubectl cp /tmp/foo my-pod:/tmp/bar -c my-container` | Copy file to container |
| `kubectl cp /tmp/foo my-namespace/my-pod:/tmp/bar` | Copy file to namespace pod |
| `kubectl cp my-namespace/my-pod:/tmp/foo /tmp/bar` | Copy file from pod |

---

## 🛠️ Deployments & Services
| Command | Description |
|--------|-------------|
| `kubectl logs deploy/my-deployment` | Deployment logs |
| `kubectl logs deploy/my-deployment -c my-container` | Container logs |
| `kubectl port-forward svc/my-service 5000` | Port-forward to service |
| `kubectl port-forward svc/my-service 5000:my-service-port` | Forward to named target port |
| `kubectl port-forward deploy/my-deployment 5000:6000` | Forward to pod from deployment |
| `kubectl exec deploy/my-deployment -- ls` | Exec in deployment pod |

---

## 🖥️ Node & Cluster Management
| Command | Description |
|--------|-------------|
| `kubectl cordon my-node` | Mark node unschedulable |
| `kubectl drain my-node` | Drain node |
| `kubectl uncordon my-node` | Make node schedulable |
| `kubectl top node my-node` | Node metrics |
| `kubectl cluster-info` | Show cluster information |
| `kubectl cluster-info dump` | Dump cluster state |
| `kubectl cluster-info dump --output-directory=/path/to/cluster-state` | Dump cluster state to directory |


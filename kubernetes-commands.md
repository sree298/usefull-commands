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

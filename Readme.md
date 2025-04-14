# 🚀 NGINX Ingress in Minikube - Cheat Sheet

## 🔧 Setup Commands
```bash
minikube addons enable ingress                          # Enable Ingress Controller
kubectl create namespace chat-app                       # Create namespace (if needed)
kubectl apply -f ingress.yaml                           # Deploy Ingress rule
echo "$(minikube ip) darshankatkam.xyz" | sudo tee -a /etc/hosts  # Local DNS
```

# Verification
```bash
kubectl get pods -n ingress-nginx                       # Check Ingress Pods
kubectl get ingress -n chat-app                         # Verify Ingress
curl http://darshankatkam.xyz                           # Test Access
```
# Cleanup
```bash
minikube addons disable ingress                         # Remove Ingress
kubectl delete ingress myingress -n chat-app            # Delete Ingress Rule
```
📌 Key Notes
✔ For local testing only – Update /etc/hosts with Minikube IP.

✔ Production? Use real DNS + TLS (cert-manager).

✔ Ensure frontend-deployment service exists in chat-app namespace.

✔ Minikube Ingress = Dev only. For prod, use Helm or K8s manifests.

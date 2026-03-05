# argocd
ArgoCD

# Step 1: Create namespace
kubectl create namespace argocd

# Step 2: Install Argo
kubectl apply -n argocd \
  -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# Step 3: Access UI
kubectl port-forward svc/argocd-server -n argocd 8090:443

- URL => https://localhost:8090
- username => admin
- password => ??

## To get password
kubectl -n argocd get secret argocd-initial-admin-secret \
  -o jsonpath="{.data.password}" | base64 --decode
echo

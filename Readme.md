# https://github.com/aionfiend/10.Kubernetes

# 10.1
1. brew install kubectl
2. brew install kind
3. Создание файла конфигурации для кластера: kind-config.yaml
4. kind create cluster --name single-node --config kind-config.yaml
```
Creating cluster "single-node" ...
 ✓ Ensuring node image (kindest/node:v1.37.0) 🖼️ 
 ✓ Preparing nodes 📦  
 ✓ Writing configuration 📜 
 ✓ Starting control-plane 🕹️ 
 ✓ Installing CNI 🔌 
 ✓ Installing StorageClass 💾 
Set kubectl context to "kind-single-node"
You can now use your cluster with:

kubectl cluster-info --context kind-single-node

Not sure what to do next? 😅  Check out https://kind.sigs.k8s.io/docs/user/quick-start/
```
5. kind get clusters
```
single-node
```
6. kind delete cluster

# 10.2
1. curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64 && chmod +x minikube
```
 % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  142M  100  142M    0     0  6611k      0  0:00:22  0:00:22 --:--:-- 5330k
```
2. sudo mv minikube /usr/local/bin - доступ из любого места в терминале
3. minikube start --vm-driver=docker
```
   😄  minikube v1.39.0 on Darwin 13.7.8
   ✨  Using the docker driver based on user configuration
   📌  Using Docker Desktop driver with root privileges
   👍  Starting "minikube" primary control-plane node in "minikube" cluster
   🚜  Pulling base image v0.0.51 ...
   💾  Downloading Kubernetes v1.37.0 preload ...
   > gcr.io/k8s-minikube/kicbase:  507.61 MiB / 507.61 MiB  100.00% 5.13 MiB p
   > preloaded-images-k8s-v18-v1...:  347.58 MiB / 347.58 MiB  100.00% 3.05 Mi
   🔥  Creating docker container (CPUs=2, Memory=1967MB) ...
   📦  Preparing Kubernetes v1.37.0 on containerd 2.3.4 ...
   🔗  Configuring CNI (Container Networking Interface) ...
   🔎  Verifying Kubernetes components...
   ▪ Using image gcr.io/k8s-minikube/storage-provisioner:v5
   🌟  Enabled addons: default-storageclass, storage-provisioner

❗  /opt/local/bin/kubectl is version 1.31.14, which may have incompatibilities with Kubernetes 1.37.0.
▪ Want kubectl v1.37.0? Try 'minikube kubectl -- get pods -A'
🏄  Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default
```
4. minikube version
```
minikube version: v1.39.0
commit: 7a9f6a841470a207de8cf4bafcccee0969d8ba10
```
5. minikube status
```
minikube
type: Control Plane
host: Running
kubelet: Running
```
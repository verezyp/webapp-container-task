# webapp-container-task
## Базовое Hello world веб-приложение на Python FastAPI - main.py
## Docker container для приложения - https://hub.docker.com/repository/docker/verezyp/task-hello
## Minikube cluster
### Установка на Linux
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64  
sudo install minikube-linux-amd64 /usr/local/bin/minikube && rm minikube-linux-amd64

minikube config set driver docker

curl -LO https://dl.k8s.io/release/v1.31.0/bin/linux/amd64/kubectl  
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

### Конфигурация и запуск

minikube start  
kubectl cluster-info  

kubectl apply -f deployment.yaml

kubectl get deployments  
kubectl get pods

kubectl apply -f service.yaml

kubectl get services
minikube service helloworld-service --url

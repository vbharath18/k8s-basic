# k8s-basic

1. Run locally 

pip install -r requirements.txt
python3 main.py

2. Build Docker Image

docker build -f Dockerfile -t hello-python:latest .

3. Run

docker run -p 5001:5000 hello-python

4. Follow with minikube start

set alias k=kubectl

minikube image load hello-python:latest

// minikube cache add hello-python:latest

k create -f deployment.yaml

k create -f service.yaml

//kubectl expose deployment hello-python --type=NodePort --port=8080

//kubectl proxy 

// http://localhost:8080/api/v1/namespaces/default/services/SERVICE-NAME:PORT-NAME/proxy/ 

// http://localhost:8001/api/v1/namespaces/default/services/hello-python-service:6000/proxy/

// minikube ip

//kubectl port-forward deployment/hello-python 35445:5000
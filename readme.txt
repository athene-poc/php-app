to build image
docker build -t php-app .

to run the app locally
docker run php-app

access the app using the browser by typing the IP Address indicated on docker run output

create secrets
Login first your docker using docker login localhost:5000

kubectl create secret generic regcred --from-file=.dockerconfigjson=/root/.docker/config.json --type=kubernetes.io/dockerconfigjson

create configmaps 
kubectl create configmap php-app-config --from-literal=greeter=kubernetes

create pod from yaml file
kubectl apply -f php-app.yaml

build the app from docker
docker build php-app

# Kubernetes And Spring Boot

Steps

* clone the project
* [Build The Image: ./mvnw spring-boot:build-image -Dspring-boot.build-image.imageName=${docker_reg_username}/${project_name}]
* create a  directyory for YAML file ( mkdir k8s )
* install kubectl
* use kubectl to generate YAML file into the folder created 
* user "kind" to create k8s cluster: "kind create cluster"
 - cd into k8s
 - run command like so " kubectl create deployment k8s_spring --image alaniomotosho2/k8s_spring:snapshot -o yaml --dry-run=client > deployment.yaml"
* create a sercice resource so that the app can be a network service
 - $ kubectl create service clusterip k8s_spring --tcp 80:8080 -o yaml --dry-run=client > service.yaml
* you can push image to docker registry or load it into the clusetr, here we load the local image into kind cluster
 - docker tag alaniomotosho2/k8s_spring alaniomotosho2/k8s_spring:snapshot
 - kind load docker-image alaniomotosho2/k8s_spring:snapshot
* cd into the project root
 - kubectl apply -f ./k8s
 - check the pod and deployment service: kubectl get all
* port forward local traffic to the service inside cluster : kubectl port-forward svc/k8s_spring 8080:80

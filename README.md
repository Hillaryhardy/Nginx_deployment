# Nginx_deployment
Nginx proj

Build a Node.js webserver and set up dockerized instances. We then configure Nginx as a reverse proxy to load balance traffic to those backend servers and finally we configure a secure HTTPS connection to the Nginx proxy with a self-signed TLS certificate.

##
Build docker image:
    `docker build --no-cache -t nginx-deployment .`
Tag the image:
    `docker tag nginx-deployment hillarydevops/nginx-deployment:0.01`
push the image:
    `docker push hillarydevops/nginx-deployment`

### deploy to cluster
Apply yaml files located in deployments to your prefered namespace
    `kubectl apply -f . -n deployments`

#### Access app using svc
Port-forward app:
    `kubectl port-forward -n deployments svc/nginx-deployment-service 30080:80`

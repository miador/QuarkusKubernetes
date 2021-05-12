Reproducion of `RESTEASY` error when deploying Quarkus app on Kubernetes with ingress-nginx.
Steps to reproduce:

```
mvn clean package

docker build -f src/main/docker/Dockerfile.jvm -t quarkus/rest-json-jvm .

kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v0.46.0/deploy/static/provider/cloud/deploy.yaml

kubectl.exe apply -f src/main/kubernetes/all-in-one.yml
```
Then try to go http://localhost/rest-json/
You'll see the `RESTEASY003210: Could not find resource for full path:http://localhost/rest-json-http/`

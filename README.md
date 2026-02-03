# a

docker exec -it jenkins bash
cat /var/jenkins_home/secrets/initialAdminPassword

## aáa

1. Generate secret key for Sonarqube

```bash
mkdir -p ./sonarqube/secrets
echo -n "current-absolutely-hare.ngrok-free.app" | base64 > ./sonarqube/secrets/sonar-secret.txt
chmod 600 ./sonar/secret/sonar-secret.txt
```


trivy fs jenkins/master/credentials.yaml \
  --scanners secret,vuln \
  --exit-code 1 \
  --severity HIGH,CRITICAL,MEDIUM, LOW

## Note

docker network lsupdate jenkinsfile agent argument network
```bash
# Get IP address of Sonarqube container
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' sonarqube
```

```bash
docker run --rm \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v $(pwd):/work \
  -w /work \
  aquasec/trivy \
  image ntthuan0106job/frontend:v1 \
  --format sarif \
  -o trivy-frontend.md \
```


```bash
docker run --rm \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v $(pwd):/work \
  -w /work \
  aquasec/trivy \
  image ntthuan0106job/backend:v1 \
  -o trivy-backend.md \
  -s MEDIUM,HIGH,CRITICAL
```

```bash
docker login -u ntthuan0106job -p Thuan05031301@
```
/home/thuan/cyber_scan/todo-app/todobackend-springboot/Dockerfile

```bash
docker run --rm \
  -v /var/run/docker.sock:/var/run/docker.sock \
  aquasec/trivy:0.69.0 \
  config todo-app/todobackend-springboot/Dockerfile \
  --scanners vuln,misconfig,secret \
  -s MEDIUM,HIGH,CRITICAL \
  -o trivy-backend-dockerfile.md
```
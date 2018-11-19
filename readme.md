 docker build -t myjenkins .
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock -v $(which docker):$(which docker) -p 8080:8080 -p 50000:50000 myjenkins
docker exec <> cat /var/jenkins_home/secrets/initialAdminPassword
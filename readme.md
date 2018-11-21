

# Jenkins Container

## Prereqs
	- docker
		to instatll docker in linux [yum install docker]
	- git
		to install git in linux [yum install docker]
	
	or follow their documentation if debian

## Setup

- clone the repository using below command
	```
	git clone clone https://github.com/jyogaraj/jenkins.git
    ```
 - switch to jenkins directory
 - build image using below
	 ``` docker build -t myjenkins .```
	 
- Run image using below and get the output 
	``` docker run -d -v /var/run/docker.sock:/var/run/docker.sock -v $(which docker):$(which docker) -p 8080:8080 -p 50000:50000 myjenkins ```

-  to get jenkins initial password 
	``` docker exec -it <output from previous> cat /var/jenkins_home/secrets/initialAdminPassword ```
	eg: docker exec 90eb850a68ac71796caf836be35a530e43903fffd534504b788c7a42b73900fd cat /var/jenkins_home/secrets/initialAdminPassword

- jenkins wiill be up and running in http://servername:8080 port
- use the insital password to login to jenkins and install suggested plugins
- setup admin user
- jenkins setup is done.
- move to repo https://github.com/jyogaraj/pipelines to setup pipelines

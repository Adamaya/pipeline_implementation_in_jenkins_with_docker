# pipeline_implementation_in_jenkins_with_docker

- clone the repo and move to directory of cloned folder of repositry

- run the following command to build the jenkins image

`docker build -t jenkinscustom .`

- run the docker container of build image.

`docker container run -dit --name <name> -p 80:8080 jenkinscustom`

- open link in web address bar `<ip of docker container>:8080`

- to see the password of jenkins run command.

`docker exec <name> cat /var/lib/jenkins/secrets/initialAdminPassword`


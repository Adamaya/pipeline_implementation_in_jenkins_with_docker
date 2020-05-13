# pipeline_implementation_in_jenkins_with_docker

## Task
1.	Create container image that’s has Jenkins installed  using dockerfile 

2.	When we launch this image, it should automatically starts Jenkins service in the container.

3.	Create a job chain of job1, job2, job3 and  job4 using build pipeline plugin in Jenkins 

4.	 Job1 : Pull  the Github repo automatically when some developers push repo to Github.

5.	 Job2 : By looking at the code or program file, Jenkins should automatically start the respective language interpreter install image container to deploy code ( eg. If code is of  PHP, then Jenkins should start the container that has PHP already installed ).

6.	Job3 : Test your app if it  is working or not.

7.	Job4 : if app is not working , then send email to developer with error messages.

8.	Create One extra job job5 for monitor : If container where app is running. fails due to any reson then this job should automatically start the container again.

## Steps:
### 1.	Create container image that’s has Jenkins installed  using dockerfile and 2.	When we launch this image, it should automatically starts Jenkins service in the container.

- clone the repo and move to directory of cloned folder of repositry

- run the following command to build the jenkins image

`docker build -t jenkinscustom .`

- run the docker container of build image.

`docker container run -dit --name <name> -v /var/run/docker.sock:/var/run/docker.sock -p 80:8080 jenkinscustom`

- open link in web address bar `<ip of docker container>:8080`

- to see the password of jenkins run command.

`docker exec <name> cat /var/lib/jenkins/secrets/initialAdminPassword`

- login and configure the jenkins.

### 3.	Create a job chain of job1, job2, job3 and  job4 using build pipeline plugin in Jenkins 

- create 4 jobs named job1,job2,job3,job4
- set the order of execution job1->job2->job3->job4
- now go to manage jenkins -> plugins manager -> available -> search build pipeline -> install the first plugin
- now go to jenkins dashboard -> go to (+) option on the top of jobs list -> select build option and enter the build name -> go to intial build option and choose the job1 -> save it.

### 4.	 Job1 : Pull  the Github repo automatically when some developers push repo to Github.

- go to plugin managerand install github plugins.
- go to job1 -> click on configure
- now do as given in images.
![conf](/pictures/1_task2.PNG)

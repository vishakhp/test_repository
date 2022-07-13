# test_repository
This is a test repository. Only intended for practice and testing

The various codes are :

git commit -m "Adding file1, file2, file3"
#records changes to the repository. Creates a new commit containing the current contents of the index and the given log message describing the changes. The new commit is a direct child of HEAD, usually the tip of the current branch and the branch is updated to point to it ( unless no branch is associated with the working tree, in which case HEAD is detached as described in git-checkout(1)

git status

git add .
##Adds all file contents to the index. Updates the index using the current content found in the working tree, to #prepare the  content staged for the next commit. The index holds a snapshot of the #content of the working tree, and it is this snapshot that is taken as the  contents of the next commit

git add names.txt

git push -u origin main
#pushes the  committed filed in the local repository to the remote repository at the url specified by the origin #(set using url data given on the github website) and on the branch specified as main

git remote add origin git@github.com:vishakhp/test_repository.git 
#For adding a new origin (i.e. a repository url/ssh)

git remote set-url origin git@github.com:vishakhp/test_repository.git
#For modifying the set (for modifying existing repository url)

git branch -M main

git branch # gives the current branch

git branch -d feature # removes the branch named feature

git pull origin main 
# Suppose you have merged a feature branch with the main branch and now you have merged it onto the main branch as well. But, in your local repository, the changes will not reflect by itself. you have to create a pull request now from the origin on the main branch onto your local repository

git checkout main
#swtiches the current branch to the branch - main

git branch
#Outputs the current branch

git push origin feature
#pushes code on your local respository to the origin URL(which is available as SSH URL on the website) with the 
#branch specified as feature

git status
#returns the current  status of the files on your git repository

git remote -v
#gives the details of the origin
                      
git commit -am "message"
#Works only on modified files that have already been committed before. It adds the files to the staging area and commits at the same time.
#But the file must have been committed before

git stash
#stash your added files somewhere and thus no need to commit the  files


git commit -m "Adding file1, file2, file3"
#records changes to the repository. Creates a new commit containing the current contents of the index and the given log message describing the changes. The new commit is a direct child of HEAD, usually the tip of the current branch and the branch is updated to point to it ( unless no branch is associated with the working tree, in which case HEAD is detached as described in git-checkout(1)

git status

git add .
##Adds all file contents to the index. Updates the index using the current content found in the working tree, to #prepare the  content staged for the next commit. The index holds a snapshot of the #content of the working tree, and it is this snapshot that is taken as the  contents of the next commit

git add names.txt

git push -u origin main
#pushes the  committed filed in the local repository to the remote repository at the url specified by the origin #(set using url data given on the github website) and on the branch specified as main

git remote add origin git@github.com:vishakhp/test_repository.git
#For adding a new origin (i.e. a repository url/ssh)

git remote set-url origin git@github.com:vishakhp/test_repository.git
#For modifying the set (for modifying existing repository url)

git branch -M main

git branch # gives the current branch

git branch dev1
#creates a new branch called dev1

git checkout -b dev2
#creates a new branch called dev2 and switches to dev2 also.

git branch -d feature # removes the branch named feature

git pull origin main
# Suppose you have merged a feature branch with the main branch and now you have merged it onto the main branch as well. But, in your local repository, the changes will not reflect by itself. you have to create a pull request now from the origin on the main branch onto your local repository

git checkout main
#swtiches the current branch to the branch - main

git branch
#Outputs the current branch

git branch dev1
#Creates a branch called dev1

git push origin feature
#pushes code on your local respository to the origin URL(which is available as SSH URL on the website) with the
#branch specified as feature

git status
#returns the current  status of the files on your git repository

git remote -v
#gives the details of the origin

git commit -am "message"
#Works only on modified files that have already been committed before. It adds the files to the staging area and commits at the same time.
#But the file must have been committed before

git stash
#stash your added files somewhere and thus no need to commit the  files

git reset file1.txt
#unstages the added file (which was added to stage via the command add file1.txt)

git reset HEAD~1
#HEAD is the pointer to the last commit. This command undoes the last done commit. HEAD will point to one commit further and hence ignores the latest commit

git log
#gives the log of all the recent changes including commits. Use the commit ids to reset to a particular change.

#If you receive an error message while running the command : sudo docker ps 
#"Got permission denied while trying to connect to #the Docker daemon socket at unix:///var/run/docker.sock: Get #"http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/json": dial unix /var/run/docker.sock: connect: permission #denied", then do the following commands

sudo usermod -a -G docker vishak
grep docker /etc/group
newgrp docker

################################

sudo service docker start
#starts the docker with administrator permission

sudo service docker status
#gives the docker running status

sudo service docker stop
#Instructs the docker to stop

#A container is a running instance of an image

sudo docker images
#REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
#nginx         latest    55f4b40fe486   5 days ago     142MB
#fedora        latest    98ffdbffd207   6 weeks ago    163MB
#hello-world   latest    feb5d9fea6a5   9 months ago   13.3kB

sudo docker run nginx:latest

sudo docker container ls

sudo docker run -d nginx:latest 
#The flag -d runs this container in detached mode i.e. in the background

sudo docker ps
#displays list of running containers

sudo docker container ls
#CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS          PORTS     NAMES
#48d63da9488a   nginx:latest   "/docker-entrypoint.…"   15 seconds ago   Up 13 seconds   80/tcp    busy_turing

sudo docker stop 48d63da9488a
#stops the container with the above container id

sudo docker run -d -p 8080:80 nginx:latest
#maps the host port on our local host computer via the port 8080 to the port 80 on the container port. -p is the #port flag. Instead of port 8080, we could use port 3000 also. Infact both ports 3000 and 8080 on our local host computer can be mapped to the port 80 on the container through the use of the following command:

sudo docker run -d -p 8080:80 -p 3000:80 nginx:latest

sudo docker ps
#CONTAINER ID   IMAGE          COMMAND                  CREATED              STATUS              PORTS                                                                          NAMES
#2d0b7be290e9   nginx:latest   "/docker-entrypoint.…"   About a minute ago   Up About a minute   0.0.0.0:3000-
#>80/tcp, 0.0.0.0:8080->80/tcp, :::3000->80/tcp, :::8080->80/tcp   suspicious_jepsen

#We can see that the local host port 8080 is connected to the container port 80

#Docker  can also be stopped in the following way:
sudo docker stop suspicious_jepsen

#############################################################################################################
#nginx is a web server company 

docker pull nginx 
#pulls the image of nginx . An image is a collection of all requirements like OS,dependencies for nginx to run
#successfully

docker images
#To see a list of all images. The latest tag shows the latest image that was installed.

# A container is a running instance of an image.
#To run a container from the image which we created just :

docker run nginx:latest

# But to run a container in the background i.e. in detached mode , run the following command:
docker run -d nginx:latest

# To see a list of all running containers
docker container ls
##############################################################

# The more preferred way to see the list of running containers is :

docker ps

# To stop a container : docker stop \<container id\> . The container id can be obtained when we type in docker ps

#Example : 

  docker ps

#CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS         PORTS     NAMES
#d81b004d8b73   nginx:latest   "/docker-entrypoint.…"   5 minutes ago   Up 5 minutes   80/tcp    hungry_kapitsa

docker stop d81b004d8b73
  
docker ps
#CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

docker run -dp 8080:80 nginx:latest
#Itnow maps the address 8080 to the port 80 on our local machine on which docker is running

docker run -dp 3000:80 -p 8080:80 nginx:latest
#maps both local hosts 3000 and 8080 to our ports on the computer in which docker is running.

docker start 5d7253a56409
#To start a container again where 5d7253a56409 was the container ID.

# ##################################################
docker ps --help

#Usage:  docker ps [OPTIONS]

#List containers

#Options:
#  -a, --all             Show all containers (default
                        shows just running)
#  -f, --filter filter   Filter output based on
                        conditions provided
#      --format string   Pretty-print containers using
                        a Go template
#  -n, --last int        Show n last created containers
                        (includes all states) (default -1)
#  -l, --latest          Show the latest created
                        container (includes all states)
#      --no-trunc        Don't truncate output
#  -q, --quiet           Only display container IDs
#  -s, --size            Display total file sizes

# To remove a container
docker rm 5d7253a56409

docker ps -aq 
# q for quiet, displays only numeric signs
a0fba9a9004d
c899fce123d1
d81b004d8b73
b0db9b5e9742
2d0b7be290e9
f3f75da411a9
48d63da9488a
47934ad6c62f
287565ddcccb

# To remove many containers, (but this does not work for a container which is currently running)
docker rm $(docker ps -aq)
#0fba9a9004d
#899fce123d1
#81b004d8b73
#0db9b5e9742
#d0b7be290e9
#3f75da411a9
#8d63da9488a
#7934ad6c62f
#87565ddcccb

# To force remove (say a running container) 
docker rm -f $(docker ps -aq)

# Naming a container
docker run --name c_name1 -dp 3000:80 -p 8080:80 nginx:latest

# Now you can stop this container as :
docker stop c_name1

# To start it again
docker start c_name1

# To assign a name to a container
docker run --name c_name2 -dp 8080:80 nginx:latest
docker run --name c_name2 -dp 9000:90 -p 8080:80 nginx:latest
 
# To change the output format of the command docker ps to a better one
docker ps --format="ID\t{{.ID}}\nNAME\t{{.Names}}\nIMAGE\t{{.Image}}\nPORTS\t{{.Ports}}\nCOMMAND\t{{.Command}}\nCREATED\t{{.CreatedAt}}\nSTATUS\t{{.Status}}\n"

# or
export FORMAT="ID\t{{.ID}}\nNAME\t{{.Names}}\nIMAGE\t{{.Image}}\nPORTS\t{{.Ports}}\nCOMMAND\t{{.Co
mmand}}\nCREATED\t{{.CreatedAt}}\nSTATUS\t{{.Status}}\n"

docker ps --format=$FORMAT

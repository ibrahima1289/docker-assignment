# Docker-assignment Kura Labs

# TASK 1

apt-get update -y && apt-get install -y curl

apt-get install git openssh-client -y

docker build -t git-image .

git --version

ssh-keygen

ssh-add ssh_key

cat ssh_key.pub ---> paste key in github to ssh

eval "$(ssh-agent -s)"

chmod 600 ssh_key.pub

ssh -T git@github.com ---> connect to github

clone git@github.com:ibrahima1289/docker-assignment.git ---> to clone github repo to local 

cd docker-assignment

touch git_file.txt

git add .

git commit -m "adding .txt file to repo"

git config --global user.email "ibrahima.diallo1289@gmail.com"
git config --global user.name "ibrahima1289"

git pull

git push origin main


# TASK 2

create a dockerfile to install ubuntu in the container

FROM ubuntu:latest

LABEL description="GIT"

RUN apt update -y
RUN apt install git -y

RUN apt-get update && DEBIAN_FRONTEND="noninteractive" TZ="America/New_York" apt-get install -y tzdata
RUN apt install ssh -y

Create a Jenkinsfile in the repo created in github
use this doc to setup ssh https://github.com/ibrahima1289/DEPLOY01_HELLO_WORLD/blob/main/Deployment%231.pdf


Follow this documentation

pipeline {
	agent {
    	docker { image 'ubuntu:latest' }
	}
	stages {
    	stage('Build'){
        	steps{
            	echo 'Build'
        	}
    	}
    	stage('Test') {
        	steps {
            	echo 'Hello'
        	}
    	}
    	stage('Deploy') {
        	steps{
            	echo 'Deploy'
        	}
    	}
	}
}



# TASK 3

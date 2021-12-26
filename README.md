# DevOps-Challenge
This repo contains the source code used as part of the interview assessment for Platform (DevOps) Engineer role.

The application code itself has been sourced from https://github.com/laravel/laravel

For more information about the content about the challenge itself, please reach out to your hiring manager.

## Open positions

For more information about working for iPrice, please view our Careers page: https://ipricegroup.com/career.html
# DevOps-Challenge

# Steps to build the application image and run the application in local environment.
1.  WSL2 + Docker Desktop, git, wget, curl, Xshell
2.  From shell, run below:- 
3.    apt update && apt install -y gnupg software-properties-common curl
4.    curl -fsSL https://apt.releases.hashicorp.com/gpg | apt-key add - 
5.    curl -fsSL https://apt.releases.hashicorp.com/gpg | apt-key add - 
6.    apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
7.    apt update && apt install terraform
8.    terraform -install-autocomplete
9.  GitClone using HTTPS method
10. Move to DevOps-Challenge path and ran below command.
11.   docker-compose -f docker-compose.yml up --build -d
12. Multiple issues were identified with the code (will be explained separately)
13. Once all issues were fixed, checked on the website locally by opening a browser and run localhost:80

# Steps to provision the infrastructure
Below are the steps to setup the AWS infra in which i used Linux(ubuntu)
1. Once account is registered with AWS, change region to Singapore
2. Services > Compute > EC2 > Launch Instances > OS[Free tier Only] (Ubuntu) 
3. Instance type > t2.micro(free) > Next
4. Configure Instance > Leave Default > Next
5. Add storage > Leave Default > Next
6. Add tags > Leave default >  Next
7. Configure Security Groups > Default Name
8.      Type : SSH : Port 22
9.      Type : HTTP : Port 80
10. Review and Launch

# Steps to deploy the application
Once server provisioned, work was being done through xShell by SSH
Create an admin/root account for self >> useradd -m -d /home/ahmed -s /bin/bash -c "Owner" ahmed
The steps to deploy the application was similar as in "# Steps to build the application image and run the application in local environment."
 1  sudo apt-get install     ca-certificates     curl     gnupg     lsb-release
 2  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
 3  echo   "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
 4  sudo apt-get update
 5  apt-get install docker-ce docker-ce-cli containerd.io
 6  docker version
 7  apt install docker-compose
 8  git clone https://github.com/iPriceGroup/DevOps-Challenge.git
 Build the application > docker-compose -f docker-compose.yml up --build -d
 Rectify all the issue with the code
 Until the final step, ensure port 80 is opened > netstat -tulpn | grep 80
 Test by going to the url http://18.142.90.1/
 
 # Any details/changes you performed to the provided source code.
 All the errors/changes were screenshot on a word document within this git repo.
 

 

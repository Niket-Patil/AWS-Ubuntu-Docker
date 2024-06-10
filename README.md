# AWS-Ubuntu-Docker
The purpose of this project is to deploying a Vue.js application using Docker, with a specific emphasis on mapping a local port 8080 to a public port 80.

# AWS EC2 Setup and Configuration: 
1.	Login to AWS Console 

2.	Go to Services --> EC2 --> Launch Instance

3.	Select the following configuration:

![1](https://github.com/Niket-Patil/AWS-Ubuntu-Docker/assets/86849874/69ac8fe4-42ae-4888-9770-6b8c6dc6d9e8)
![2](https://github.com/Niket-Patil/AWS-Ubuntu-Docker/assets/86849874/a185a8d0-d2b0-4233-bb73-5e681e7b7a55)
![3](https://github.com/Niket-Patil/AWS-Ubuntu-Docker/assets/86849874/b2c09cf0-0c44-42a7-89e1-e115a696dda7)
![4](https://github.com/Niket-Patil/AWS-Ubuntu-Docker/assets/86849874/04b2799d-3b8d-4e18-a75f-c0f9307f4cb6)  

Use the default VPC and Subnets. 
Allow SSH and HTTP/HTTPS in security groups.
4.	Click on “Launch Instance”

5.	Once the instance 2 checks click on “connect”.

6.	Run “sudo apt-get update && sudo apt-get upgrade -y” command to update package manager

 
![5](https://github.com/Niket-Patil/AWS-Ubuntu-Docker/assets/86849874/7e944510-fe18-45df-b1a1-d91314231582)


# Docker Installation:

1.	Install required packages for docker:
“sudo apt install apt-transport-https \
 ca-certificates \
 curl \
 software-properties-common”

 ![6](https://github.com/Niket-Patil/AWS-Ubuntu-Docker/assets/86849874/17040089-a7fe-48aa-b8ad-9382c2ed90bc)


2.	Add Docker GPG key
“curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg”


3.	Add Docker Repository
“ echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list ”

4.	Update the package manager again
“sudo apt update”

5.	Now install Docker
“sudo apt install docker-ce docker-ce-cli containerd.io”

6.	Check the status of Docker using “sudo systemctl status docker”

 ![7](https://github.com/Niket-Patil/AWS-Ubuntu-Docker/assets/86849874/318bcbc9-da6f-4d06-b273-9c41ecfc32d2)


7.	Verify Docker Installation
“docker  --version”

![8](https://github.com/Niket-Patil/AWS-Ubuntu-Docker/assets/86849874/4c6d1c00-0b1d-4343-bb03-198488f7ce23)


The Docker Setup is now complete.







# Building a Docker Image

1.	Make a new directory (for example “docker-project”)
“mkdir docker-project”

 ![9](https://github.com/Niket-Patil/AWS-Ubuntu-Docker/assets/86849874/de083819-403a-4d7a-979a-316badccccc4)


2.	Change the current working directory to project root directory
“cd docker-project”
 
![10](https://github.com/Niket-Patil/AWS-Ubuntu-Docker/assets/86849874/d6225c11-ee39-4f48-8dbd-590c7806b303)

3.	Create a “Dockerfile” in the root directory of your project, using 
“sudo nano Dockerfile” enter the given configuration below.
 
![11](https://github.com/Niket-Patil/AWS-Ubuntu-Docker/assets/86849874/90574d8d-86c9-47ae-8745-8f51c7a28cc3)

4.	Now build the docker image of the application using 
“docker build docker-project”
 
![12](https://github.com/Niket-Patil/AWS-Ubuntu-Docker/assets/86849874/88442825-b494-4747-8a40-1da62ba4e820)

5.	We can list local docker images using 
“sudo docker images”

![13](https://github.com/Niket-Patil/AWS-Ubuntu-Docker/assets/86849874/567c2a16-c9ce-440d-817d-ffaf7579bc23)

 
7.	To run a docker Container
“sudo docker run -p 80:8080”
 
![14](https://github.com/Niket-Patil/AWS-Ubuntu-Docker/assets/86849874/b2550a13-4f6f-408c-8877-d2815d379fb3)

8.	To check the existing running containers 
“sudo docker ps -a ”

 ![15](https://github.com/Niket-Patil/AWS-Ubuntu-Docker/assets/86849874/f94f2a71-eb16-41c6-b75f-03fc21dfe454)


The application is now hosted on PORT 8080 internally and available PORT 80 public IP

# 3.84.187.195 

Copy this IP and past it in your Browser 

# OUTPUT
  

![16](https://github.com/Niket-Patil/AWS-Ubuntu-Docker/assets/86849874/28a980f9-ed50-403a-a354-c02096e2d7ce)




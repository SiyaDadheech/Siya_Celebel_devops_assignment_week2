step 1: Prequistes :  
Docker engine need to be installed on your system.  

Install and Configure AWS CLI
> check using aws --version

> aws configure

> {here paste your aws account access key and secret key, region name}

step 2: Create an ECR repository  

> aws ecr create-repository --repository-name flask-web-app --region ap-south-1

step 3: Authenticate Docker

> aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin <account-id>.dkr.ecr.<region>.amazonaws.com
> you will get login successfull message.

step 4: Build Docker Image  
docker build -t flask-web-app .  
you can check your image by using : docker images  

step 5: Tag the image.  


docker tag flask-web-app:latest 650251724323.dkr.ecr.ap-south-1.amazonaws.com/flask-web-app:latest

step 6: Push the Tagged Image To AWS ECR.  


docker push 650251724323.dkr.ecr.ap-south-1.amazonaws.com/flask-web-app:latest



step 1: buy domain from any registered domain provider.  

step 2: AWS provides a Route 53 service to host your website and also you can buy domain there.  

step 3: To buy domain via Route 53:  

> Go to Route 53 > Registered Domains > Register Domain.

> select your domain.

> complete registration and payment process

step4: launch an EC2 instance(UBUNTU)  

under the additional details click on user data and add the scipt:  
#!/bin/bash  

sudo apt update  

sudo apt install apache2 -y  

sudo systemctl start apache2  

sudo systemctl enable apache2  

echo "Welcome to my website!" > /var/www/html/index.html  


step 5: Allocate elastic IPs  

> Go to EC2 > Elastic IPs > Allocate Elastic IP

> Select the IP and associate it with your EC2 instance


step 6: Setup DNS via Route 53  

> Go to Route 53 > Hosted Zones

> open the hosted zone

> click create Record

> For Creation of A Record:

> Record Name: @
 
> Record Type: A

> vlaue: elastic ip

> TTL: 300


step 7: check on browser: http://yourdomain.com



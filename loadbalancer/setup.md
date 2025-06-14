🔷 Step 1: Create EC2 instance


🔷 Step 2: Create Target Group
Go to EC2 → Target Groups

Click Create target group

1.Type: Instances

2. Protocol: HTTP

3. Port: 80

4. VPC: same as your EC2

Name: alb-ec2

Click Next, then Register targets

Select your EC2 instance(s)

Click Create target group

🔷 Step 3: Create ALB (Application Load Balancer)
Go to EC2 → Load Balancers

Click Create Load Balancer → Application Load Balancer

Set:

Name: task-2

Scheme: Internet-facing
for external load balancer i have used the Internet-facing.  

for internal load balancer: select the Scheme to Internal and select the private subnet only.

IP type: IPv4

Listeners:

Protocol: HTTP

Port: 80

Availability Zones: same as your ec2 instance.

Select 2+ subnets in the same VPC as your EC2

Click Next: Security Settings

🔷 Step 4: Security Group for ALB
Use an existing ALB Security Group or create a new one:

Inbound Rule: HTTP 80 from 0.0.0.0/0

🔷 Step 5: Register Target Group
Choose existing: alb-ec2

Click Create

🔷 Step 6: Test Your Load Balancer
Wait a few minutes for ALB to go "Active"

Go to EC2 → Load Balancers

Copy the DNS name (e.g., tast-2-601934651.ap-south-1.elb.amazonaws.com/)

Open in browser:
http://tast-2-601934651.ap-south-1.elb.amazonaws.com/  

currently i have terminate my instance so you cann't access the alb using the above link.

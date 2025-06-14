# Siya_Celebel_devops_assignment_week2
# To deploy a Linux VM in AWS here are the steps:
1. go to console
2. Select the launch instance option
3. give a meaningful name
4. choose AMI: ubuntu
5. Add keypair or can create new key pair
6. choose the VM size and manage the number of instances
7. in the networking setting allow ssh in the security group.
8. click create.
# To deploy Windows VM in AWS here are the steps:
1. go to console
2. select the launch instance option.
3. give a meaningful name
4. choose AMI: Microsoft Windows Server 2025 Base
5. instance type: I have used the t2.micro
6. Add the keypair
7. Choose the VM size the minimum size required is 30GB.
8. in the networking setting allow RDP(3389 TCP) port in the security group.
9. click launch instance.
10. copy the public ip for connecting to rdp.

   # To connect to RDP.
   1. click on the name of your instance and on the top right click connect.
   2. choose RDP client connect tab.
   3. click "Get Password"
   4. upload your private key(.pem) to decrypt the password.
   5. copy the Administrator password.
   6. on your laptop search bar type RDP.
   7. paste the public ip of the instance
   8. username is: Administrator
   9. Password: your decrypted password paste that.
       you are successfully connected.

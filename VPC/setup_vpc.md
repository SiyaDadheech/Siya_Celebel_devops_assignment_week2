Step 1: use the given cidr and subnet
You'll create the following VPCs:

Management VPC (Hub):

CIDR: 10.0.0.0/16

Subnets:

10.0.1.0/24 (Linux VM)

10.0.2.0/24 (Windows VM)

Production VPC:

CIDR: 10.1.0.0/16

Subnet: 10.1.1.0/24 (SQL DB)

Testing VPC:

CIDR: 10.2.0.0/16

Subnet: 10.2.1.0/24

Development VPC:

CIDR: 10.3.0.0/16

Subnet: 10.3.1.0/24

Ensure that the CIDR blocks do not overlap to avoid routing issues.

Step 2: Create VPCs and Subnets
Navigate to the VPC Dashboard in the AWS Management Console.

Create each VPC with the specified CIDR blocks.

Create subnets within each VPC as per the plan.

Step 3: Set Up AWS Transit Gateway (TGW)
Navigate to the VPC Dashboard and select Transit Gateways.

Create a new Transit Gateway:

Name: my-tgw

ASN: 64512 (default)

Enable DNS support and multicast if required.

Attach VPCs to the Transit Gateway:

For each VPC, create a TGW attachment.

Select the appropriate subnets for each attachment.

Configure Route Tables:

Create a route table for the Transit Gateway.

Add routes to direct traffic between VPCs via the TGW.

Step 4: Launch EC2 Instances
Launch EC2 Instances in each subnet:

Management VPC: Launch a Linux VM in 10.0.1.0/24 and a Windows VM in 10.0.2.0/24.

Production VPC: Launch a Windows VM in 10.1.1.0/24.

Testing VPC: Launch a Linux VM in 10.2.1.0/24.

Development VPC: Launch a Linux VM in 10.3.1.0/24.

Assign Security Groups: allow 22,3389 ports.  


Ensure that the security groups allow inbound and outbound traffic on necessary ports (e.g., SSH for Linux, RDP for Windows).

Step 5: Verify Connectivity
SSH/RDP into the Management VPC's Linux VM.

Ping the private IPs of the EC2 instances in other VPCs:

From the Management VM, ping the instances in the Production, Testing, and Development VPCs.  

check the connectivity using the ping.


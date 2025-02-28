# VCC-ASSIGNMENT-2

Implementation Steps: 
1. Creation of a VM Instance on GCP
•	Step 1: Sign in to Google Cloud Console
o	Go to Google Cloud Console.
o	Logged in through M23CSA534@IITJ.AC.IN
•	Step 2: Select a Project
o	Click on the project drop-down menu at the top of the page.
o	Choose an existing project or create a new one by clicking "+ Create Project."
o	Created below project
o	 
•	Step 3: Access the VM Instances Page
o	Navigate to Compute Engine > VM instances in the left sidebar.
o	Click on Create Instance.
o	We created below vm instance
m23csa534-vcc-ass2-dslq
 
•	Step 4: Configure the VM Instance
o	Name: Enter a meaningful name for your VM instance.
o	Region and Zone: Select us-east-1 as the region.
o	Machine Type: Choose n1-standard-1 (1 CPU, 2GB RAM).
o	Boot Disk: Debian-bookworm x64
o	Firewall Settings: Check Allow HTTP and HTTPS traffic.
•	Step 5: Create the Instance
o	Review the configuration and click Create.
o	Once the instance is running, connect using the SSH button.

2. Configuration of Auto-Scaling Policies
o	Step 1: Create an Instance Template
o	Navigate to Compute Engine > Instance Templates.
o	Click on Create Instance Template.
o	Configure it similarly to the VM instance created earlier.
o	Click Create.
 
o	Step 2: Create a Managed Instance Group
o	Go to Compute Engine > Instance Groups.
o	Click Create Instance Group.
o	Group Type: Select Managed Instance Group.
o	Instance Template: Choose the previously created instance template.
o	Initial Number of Instances: Set to 1.
o	 
o	Step 3: Configure Auto-Scaling
o	Enable Auto-Scaling: Check the Enable Autoscaling option.
o	Scale Based On: Choose CPU utilization.
o	Target CPU Utilization: Set to 40%.
o	Set Limits: Define minimum instances 1 and maximum instances 3.
o	 
o	 
o	 
o	Click Create to finalize the auto-scaling setup.

3. Implementation of Security Measures
o	Step 1: Setting Up IAM Roles for Restricted Access
o	Navigate to IAM & Admin > IAM in Google Cloud Console.
o	Click Add to add a new member.
o	User: Enter adak.swapnil974@gmail.com.
o	Role: Assign Compute Engine Viewer for restricted access.
o	Click Save.
 

o	Step 2: Configuring Firewall Rules
o	Go to VPC Network > Firewall Rules.
o	Click Create Firewall Rule.
o	Name: assignment2-vcc-rule
 
o	Network: Choose the default or custom VPC.
o	Targets: Set to All instances in the network.
o	Source Filter: Select IP Ranges and enter 0.0.0.0/0 (all IPs, use cautiously).
o	Protocols and Ports:
	Allow TCP 22 (SSH access).
	Allow TCP 80 (HTTP traffic).
	Allow TCP 443 (HTTPS traffic).
o	Click Create.
o	 


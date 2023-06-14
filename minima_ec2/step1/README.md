[Back to introduction](../README.md)

# Step 1 - Launch an EC2 instance

Assuming you have secured your AWS account *with the leading practices we can now move to create an EC2 instance that will host your Minima Node.  

*If you are the type of person that wants 100% control this **isn’t** the guide for you. There is a contractual agreement between you and AWS, where AWS has physical access to your machine and and keys for encryption. This requires a lot of trust.* 

## Selecting where to run your EC2

The instance needs to live somewhere, so you need to choose which global region to run your compute. For me it’s North Virgina, but I suggest you pick something close to you. Each region has a specific pricing model so make sure you understand that before selecting. 

Select the AWS region you are closest to in the dropdown in the top right corner of the AWS console. 

![](selectRegion.png)

## EC2 Dashboard

Using the AWS console search bar, type ec2 and select EC2 Virtual Servers in the Cloud

![](ec2Dashboard.png)

## Start the EC2 creation wizard

Find the Launch instance button and click to start the Creation Wizard.


![](launchEC2Wizard.png)

Selecting Launch instance a configuration form will appear. There are several important configurations you need to complete. This is a fairly large form [7 sections], which I will only detail where to make changes. If I don’t mention something you can leave the default values AWS pre-selected. 

### Name and tags

Give you instance a clear understandable name. Something like, MinimaNode.

### Application and OS Images

The default image is a good place to start. It’s free tier eligible; which means you don’t have to pay for the first year of your AWS account.  Basically leave all the defaults AWS gives you. For me that means I’m allowing AWS to select “*Amazon Linux 2023 AMI 2023.0.20230419.0 x86\_64 HVM kernel-6.1” instance.* 

### Instance type

This determines the power of the machine and hence its cost. The smallest [cheapest] machine I found that works consistently is a t2.micro 1GiB Memory. It also happens to be the default, so again, no need to change anything. 

### Key pair (login)

This is important: You will need it later to connect to your instance.

You must create a new key pair or select a previously created pair. [BOYK and linking them to your EC2 instance is beyond this document] 

If you don’t know what you are doing, you can just allow AWS to create them via the Create new key pair link. 

![](keypairCreation.png)

The Create key pair dialog window will appear, where you can name your new key pair, and keep everything else as defaulted. 

![](createKeyPairWizard.png)

### Network settings

A very important section. I’ll give a basic configuration only changing the defaults where absolutely necessary.

Click the Edit button.

Keep the default VPC

Create a security group

Give your new security group a clear name

![](securityGroupName.png)

Inbound security groups rules  need only change if you want to browse to Minima node’s MDS Hub. If you prefer a web application to a command terminal you may want to access the MDS Hub and therefore these network changes are needed. 

You need two rules:

#### Security group rule 1

Allows secure connection using ssh to your EC2 instance

Type: ssh

Source type: Anywhere

[This should already be in place as AWS configures this by default. 

![](securityRule1.png)

#### Security group rule 2

Allows traffic from only your computer to your EC2 instance via a browser but only with a port of 8003

Type: Custom TCP

Source type: My IP

Port range: 8003

![](securityRule2.png)

[NB: Port 8003 is the port the docker container exposes to allow access to the MDS Hub. If you change that port when installing Minima, you will need to change this port to match, otherwise the firewall will deny access.]

### Storage (volumes)

Open the advanced view 

![](storageAdvancedSettings.png)

Create an encrypted volume. 

Device name: This value should be remembered as it will be needed when restoring from a failure. 

Delete on termination: No

Volume type: gp2

Encrypted: Encrypted KMS key: default aws/ebs

![](defaultKMS.png)

Everything else is good at default. Click Launch instance button and your instance will start to be created. Shortly after you should see the success page. 

![](successNotice.png)

This doesn’t mean your EC2 instance is ready to use, but the launch was successful. 

Select the instances on the left side menu of the console to see you EC2 being created. It will be initialising at first, then some time later it will be running, and have passed two checks. 

![](ec2InstanceList.png)


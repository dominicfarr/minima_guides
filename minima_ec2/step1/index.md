[Introduction](../index.md) > <u>Step 1</u> > *Step 2* > *Step 3* > *Step 4* > *Step 5* > *Step 6*

# Step 1 - Launch an EC2 instance

```
🧐 You have logged into the AWS console?
```

## Selecting where to run your EC2

The EC2 instance needs to `live` 🏠 somewhere. You need to choose which global region to run your compute. I suggest you pick something close to you. 

```
Did you check the regional pricing in AWS? 🧐
```

Select the AWS region you are closest to in the dropdown in the top right corner of the AWS console. 

![](selectRegion.png)

---
## EC2 Dashboard

Using the AWS console search bar, type ec2 and select EC2 Virtual Servers in the Cloud

![](ec2Dashboard.png)

---
## Start the EC2 creation wizard

Find the Launch instance button and click to start the Creation Wizard.


![](launchEC2Wizard.png)

Press 👆 the Launch instance. The configuration form will appear. 

```
You can leave the values AWS preselected for much of the configuration 👍 
```

### Name and tags

Give your instance a clear understandable name. Something like, `Minima`.

### Application and OS Images

The default image is a good. It’s free tier eligible, which means you don’t have to pay for the first year of your AWS account.

### Instance type

This determines the power of the machine and hence its cost. The smallest [cheapest] machine I found that works consistently is a t2.micro 1GiB Memory. It also happens to be the default, so again, no need to change anything. 

### Key pair (login)

You must create a new key pair or select a previously created pair.

![](keypairCreation.png)

👆 Create new key pair. The create key pair dialog window will appear, where you can name your new key pair, and keep everything else as defaulted. 

![](createKeyPairWizard.png)

### Networking settings

A very important section. This will keep you safe 🥽 

I’ll give a basic configuration.

* Click the Edit button

* Keep the default VPC

* Create a security group

Give your new security group a clear name

![](securityGroupName.png)


You need two rules:

Rule 1 is already configured

![](securityRule1.png)

### Security group rule 2

Allows traffic from only your computer to your EC2 instance via a browser but only with a port of 8003

Type: Custom TCP

Source type: My IP

Port range: 8003

![](securityRule2.png)

[NB: Port 8003 is the port the docker container exposes to allow access to the MDS Hub. If you change that port when installing Minima, you will need to change this port to match, otherwise the firewall will deny access.]

### Storage (volumes)

Open the advanced view 

![](storageAdvancedSettings.png)

* Create an encrypted volume

* Remember the Device name: This value will be needed if/when a restore from failure is needed. 

* Delete on termination: No

* Volume type: gp2

* Encrypted: Encrypted KMS key: default aws/ebs

![](defaultKMS.png)

Everything else is good at default. Click Launch instance button. Your instance will start to be created. 

Shortly after you should see the success page. 

![](successNotice.png)

This doesn’t mean your EC2 instance is ready to use, but the launch was successful. 

Select the `instances` on the left side menu of the AWS console to see you EC2 being created. It will be initialising at first, then some time later it will be running, and have passed two checks. 

![](ec2InstanceList.png)

[Goto step2 - Connect to your instance via the AWS Console](../step2/index.md)
## About these guides

These [guides](https://minima-guides.formulathoughts.com/) are only 1 stop in your [Minima](https://minima.global) journey. 

[Minima](https://minima.global) can store value & AWS resources cost money, so I'm going to be clear: You follow this guide at your own risk. 🤷‍♂️

If you do find an issue or would like an update please add a [new issue](https://github.com/dominicfarr/minima_guides/issues) to the [repo](https://github.com/dominicfarr/minima_guides)

---
# Create a regular automatic backup of your Minima Node
This guide is about creating a regular backup of your data so if something goes wrong with your instance or your storage you can recover your Minima Node without lost of value or data. 

This guide is best as a following on from [Running Minima on an AWS EC2 instance](https://minima-guides.formulathoughts.com/minima_ec2/) and makes assumptions about your environment. That is, you have an AWS EC2 instance with an encrypted EBS volume where a Minima Node is storing its data. Something similar to this.

![Basic Architectural Diagram of Minima Node Running in Docker on an EC2 instance.](../minima_ec2/aws-minima-arch.jpg)

## Here are the high level steps

1.  Create a DLM or Data Lifecycle Manager Policy
2.  Tag your EBS for the DLM policy 
3.  Confirm your snapshot is created


[Goto step 1 - Create a Data Lifecycle Manager Policy](./step1/index.md)

<span style="color:red">Important to recognise: You follow this guide at your own risk and the authors shall not be responsible or liable for any loss you may incure.</span>

* This guide assumes that you have an AWS account.
* Your AWS account is secured with the leading practices. [Read and follow these instructions from AWS](https://docs.aws.amazon.com/accounts/latest/reference/welcome-first-time-user.html)
* That you understand that this document may contain errors which puts your value at risk. 
* That this document will not age well and may not be kept up to date with the latest requirements that keeps your safe and your value secure.

If you do find an issue or would like an update please add a [new issue](https://github.com/dominicfarr/minima_guides/issues) to the [repo](https://github.com/dominicfarr/minima_guides)


# Running a Minima Node on AWS EC2 Resource

There are [<span>many ways</span>](https://docs.minima.global/docs/runanode/get_started) to run a Minima Node. This document will describe how to run a node using AWS EC2 Resource. I’ll walk through the steps for someone with basic or limited AWS knowledge.

_[Yes I see the irony of running a highly distributed technology on a highly centralised service like AWS]_

This is a basic diagram of what we are going to achieve.

![Basic Architectural Diagram of Minima Node Running in Docker on an EC2 instance.](aws-minima-arch.jpg)

As you can see, this a lot for something so small and lightweight as Minima. The benefits come from the convenience of managed hardware, and security AWS can provides but those benefits require trusting AWS. 

## What does AWS provide

When you use AWS you are leasing AWS’s resources [the cloud] This is an alternative to owning a device like a mobile or a home computer and running your node on that device.

Minima is small, so you don’t need a powerful EC2 instance, a small t2.micro is enough. At the time of writing this an EC2 t2.micro instance with 8GiB storage will cost about $34USD per year. That’s pretty cheap compared to other options to run a node. E.g. Budget android phone is about $140USD

You get a lot for that $34 pa.<span class="Apple-converted-space"> </span> AWS data centres are highly secure [[<span class="s1" style="color: rgb(220, 161, 13);">Here</span>](https://aws.amazon.com/compliance/data-center/controls/)] You can create backups of your data. Using AWS is highly flexible, secure, and can be scripted and programmed in many many ways.<span class="Apple-converted-space"> </span>

## About this guide

This guide is as simple as I can make it. But that doesn’t mean you can set and forget. You need to learn more, and understand each part of this guide. At the end of the guide you may have a working Minima Node; this is just the beginning of your journey into Minima and AWS. I will cover where your journey should continue at the end of the guide. 

### Here are the high level steps

1.  Launch a new EC2 instance
2.  Connect to your instance via the AWS Console
3.  Install Docker on that EC2 instance
4.  Run Minima and Watchtower docker containers
5.  Access the MDS Hub

[Got to step 1](./step1/README.md)

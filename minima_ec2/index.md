## About these guides

These [guides](https://minima-guides.formulathoughts.com/) are only 1 stop in your [Minima](https://minima.global) journey. 

[Minima](https://minima.global) can store value & AWS resources cost money, so I'm going to be clear: You follow this guide at your own risk. 🤷‍♂️

If you do find an issue or would like an update please add a [new issue](https://github.com/dominicfarr/minima_guides/issues) to the [repo](https://github.com/dominicfarr/minima_guides)

---
# Running a Minima Node on AWS EC2 Resource

There are [many ways](https://docs.minima.global/docs/runanode/get_started) to run a Minima Node. This document will describe how to run a node using AWS EC2 Resource. I’ll walk through the steps for someone with basic or limited AWS knowledge.

```md 
Yes I see the irony [or over engineering 👀] of running a tiny, highly distributed, technology like Minima 
on a highly centralised service like AWS 😲
```

This is a basic diagram of what we are going to achieve.

![Basic Architectural Diagram of Minima Node Running in Docker on an EC2 instance.](aws-minima-arch.jpg)

As you can see, this is a lot for something so small and lightweight as Minima. The benefits 👍 would come from the convenience of managed hardware. It does require trusting AWS 📃 

---
## What does AWS provide

Assuming 🧐 you 
* Have an AWS account.
* [Secured](https://docs.aws.amazon.com/accounts/latest/reference/welcome-first-time-user.html) it correctly. 🤥


When you use AWS you are leasing AWS’s resources ☁  and Minima is small, so you don’t need too much power ⚙️ 

At the time of writing this, an "EC2 t2.micro" instance with 8GiB storage will cost about $35USD per year. 

---
## Here are the high level steps

1.  Launch a new EC2 instance
2.  Connect to your instance via the AWS Console
3.  Install Docker on your EC2 instance
4.  Run Minima container
5.  Run Watch tower container
6.  Access the MDS Hub


[Goto step 1 - Launch a new EC2 instance](./step1/index.md)

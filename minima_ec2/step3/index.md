[Introduction](../index.md) > [Step 1](../step1/index.md) > [Step 2](../step2/index.md)  > <u>Step 3</u> > *Step 4* > *Step 5* > *Step 6*

# Step 3 - Install Docker

Installing Docker is straightforward 

`That's easy for me to say 😥` 

We can run a command to install Docker. Type the following into your terminal and Docker will download automatically.

```bash
sudo yum install docker
```

To keep Docker running even if you restart your EC2 instance we need a few more commands 🪄


```bash
sudo addgroup docker

sudo usermod -a -G docker ec2-user 

sudo systemctl enable docker
```

Finally, to start Docker 🏁

```bash 
sudo systemctl start docker
```

---

Nice work! Docker is installed; running; configured as a service which automatically starts when your EC2 instance starts. 

We should run some checks ✅ to make sure everything is correct. Type in this command:

```
systemctl status docker
```

You should get some output like this. Look out for the text in green: enabled and active (running) 

![](dockerServiceRunning.png)

Press q to quit this command. 

[Goto step 4 - Run Minima container](../step4/index.md)
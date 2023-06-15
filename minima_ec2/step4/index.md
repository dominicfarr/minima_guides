[Introduction](../index.md) > [Step 1](../step1/index.md) > [Step 2](../step2/index.md)  > [Step 3](../step3/index.md) > <u>Step 4</u> > *Step 5* > *Step 6*

# Step 4 - Run Minima container

Downloading Minima’s docker image and starting a container using that image is straightforward. However, the command to do this has important aspects and parameters that I’m not covering in this guide. Please refer to the [Minima docs](https://docs.minima.global/docs/runanode/get_started) for complete details of these parameters.

---

In the EC2 terminal, execute the following command. 

Before doing so, update the mdspassword value to something only you know, is fairly long [+10 characters], includes a mixture of elements [upper, lower, numbers, but no punctuation.]  

The backslash \ is a convenience to allow this command to correctly span multiple lines for ease of reading. 

```bash
docker run -d --name minimaNode \
-e minima_mdspassword=PasswordsNeed2BLongButEasy2Remember \
-e minima_server=true \
-v ~/minimaNode:/home/minima/data \
-p 8001-8004:9001-9004 \
--restart unless-stopped \
minimaglobal/minima:latest
```
After executing the command docker will search for minima locally, fail to find it, and will download it from Minima Docker repository. Then it will create a running container with the configured ports and volumes [file system where data will be stored]

You can check installation by executing the following command

`docker ps`

A log of running containers will be displayed. Your log should contains something similar to this:

￼![](minimaContainer.png)

At this stage you have a running EC2 instance, with a docker environment with a container running the Minima node. Furthermore, you have a separate encrypted volume that stores your data—in this case the Minima node data.

[Goto step 5 - Run Watchtower container](../step5/index.md)
[Back to step 2](../step2/index.md) <-> [Goto step 4](../step4/index.md)

# Step 3 - Install Minima

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
After executing the command docker will search for minima locally, fail to find it, so will download it from Minima Docker repository. Then it will create a running container with the configured ports and volumes [file system where data will be stored]

You can check installation worked by executing the following command

docker ps

You should get something that contains this info

￼![](minimaContainer.png)

At this stage you have a running EC2 instance [a virtual computer hosted by AWS], a docker environment with a container running the minima node.  Here is a basic diagram.

[Goto step 4 - Run Minima and Watchtower docker containers](../step3/index.md)
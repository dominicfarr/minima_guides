[Introduction](../index.md) > [Step 1](../step1/index.md) > [Step 2](../step2/index.md)  > [Step 2](../step3/index.md) > [Step 4](../step4/index.md) > <u>Step 5</u> > *Step 6*

# Step 5 - Run Watchtower container

Directly from the Minima [docs(https://docs.minima.global/docs/runanode/selectplatform/linux_desktop#automate-updates-with-watchtower)]. 
Watchtower container enables automatic updates of your Minima node when a new version is released. 

Similar to creating the Minima node Docker container, a simple command to the Docker system will download and start Watchtower.

`docker run -d --restart unless-stopped --name watchtower -e WATCHTOWER_CLEANUP=true -e WATCHTOWER_TIMEOUT=60s -e WATCHTOWER_POLL_INTERVAL=28800 -v /var/run/docker.sock:/var/run/docker.sock containrrr/watchtower`


[Goto step 6 - Access the MDS Hub](../step6/index.md)
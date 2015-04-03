This is a Dockerfile setup for HandBrake-CLI - https://trac.handbrake.fr/wiki/CLIGuide

To run:

```
docker run --name="handbrake" -d -v /mnt/user:/files -v /etc/localtime:/etc/localtime:ro pinion/handbrake
```

Breaking this down:

'docker run' runs a container. --name is naming the container handbrake. -v is setting the volume. My Dockerfile exposes /files to whatever you set it. In this example I'm setting it to /mnt/user. This means my host OS's folder /mnt/user will be available under /files once I connect to the docker (see below). Then I set the localtime to the host OS local time. pinion/handbrake tells docker where to pull from in the Docker Hub.

To connect:

```
docker exec -i -t handbrake bash
```

From here you can navigate to any video and encode it like you normally would. See the CLI Guide wiki link above.

Much donate: DR5dCKF8m5x8VWMtofpGoH4ghjNZYywgTU

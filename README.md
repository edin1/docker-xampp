# A personalized Dockerfile for xampp/lampp

You can use my code for good, not evil.

Based on https://github.com/tomsik68/docker-xampp

You need to provide the file `"xampp-linux-installer.run"`

I usually build the image with:
```
docker build . -t myusername/debian:xampp
```

and then run/stop it with:
```
docker run -p 41061:22 -p 41062:80 -v /path/on/the/host/to/myproject:/opt/lampp/htdocs/myproject mysername/debian:xampp
docker stop $(docker ps -q --filter ancestor=edin1/debian:xampp)
```

The servers are run as the daemon user, so the Dockerfile changes the GID and UID of that user to 1000, which should be your host user ID. Of course, you can change it to any acceptable ID to match your setup.
# Homework 01

### Description:

This is a very basic project. Create a Dockerfile to run a bash script in the container. The bash script will print "Hi" on the screen every two seconds continuously. But the problem arises when script is working on the host machine but not working on Container.

### Solution (Step by Step from scratch)

**The issue was the script was missing the "shebang" or "#!/bin/sh", which causes the error.**

- Step 01: Install docker client on the machine. Follow the offcial docs: https://docs.docker.com/engine/install/
- step 02: Create a bash script named 'echo.sh'

```console
#!/bin/bash

while true
do
    echo "Hi"
    sleep 2
done
```

- Step 03: Create a Dockerfile

```console
FROM ubuntu
RUN apt update -y
WORKDIR /app
COPY echo.sh .
CMD ["./echo.sh"]
```

- Step 04: Run the following commands for build and run the container

```console
$ sudo chmod +x echo.sh
$ sudo docker build . -t hello
$ sudo docker run hello
```

**_Note: This issue also can be solved without using shebang. Change will be in Dockerfile, CMD ["sh", "echo.sh"]_**

## Screenshots

![App Screenshot](https://github.com/faayam/devops-homeworks/blob/main/hw01/final_screenshot.PNG)

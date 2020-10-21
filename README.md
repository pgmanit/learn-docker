# learn-docker

It's a simple ToDo list application built on node.js and deployed using docker

## Clone this repo and run following command:
```cd app```

## How to Build docker container image?
```docker build -t getting-started .```

## How to run docker container?
```docker run -dp 3000:3000 getting-started```


After a few seconds, open your web browser to [http://localhost:3000](http://localhost:3000)
Your server should be up now !

## Important commands:
1. ```docker ps```
   See all running docker containers and get ID of a particular container

2. ```docker stop <the-container-id>```
   Stop the container

3. ```docker rm <the-container-id>```
   Once the container has stopped, you can remove it by using this command

4. ```docker rm -f <the-container-id>```
   -f is force flag. This command stops and removes the container.

<br />

### References
* [Getting Started with Docker](https://docs.docker.com/get-started/overview/)

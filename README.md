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


## Container Volumes / Persisting our Todo Data
Volumes provide the ability to connect specific filesystem paths of the container back to the host machine. If a directory in the container is mounted, changes in that directory are also seen on the host machine. If we mount that same directory across container restarts, we'd see the same files.

By default, the todo app stores its data in a SQLite Database at /etc/todos/todo.db
* Create a volume by using the docker volume create command.<br />
```docker volume create todo-db```<br />
* Start the todo app container, but add the -v flag to specify a volume mount. We will use the named volume and mount it to /etc/todos, which will capture all files created at the path.<br />
```docker run -dp 3000:3000 -v todo-db:/etc/todos getting-started```<br />

Now the data created in ToDo app won't get destroyed even after removing and re-starting the container.

<br />

### References
* [Getting Started with Docker](https://docs.docker.com/get-started/overview/)

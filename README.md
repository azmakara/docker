Docker basic command lines

1. docker run
   
docker run -> Create and start container if not exist --name "mysql-container" 
-d Runs the container in the background (detached mode).
-p 30306:3306 -> expose port 30306 public (map host port 30306 to 3306)
-e MYSQL_ROOT_PASSWORD=mysecret -e TZ=UTC ->Sets environment variables inside the container.
"ubuntu/mysql:8.0-22.04_beta" -> using docker image from dockerHub name "ubuntu/mysql:8.0-22.04_beta"

---
#docker run -d --name mysql-container  -p 30306:3306  -e MYSQL_ROOT_PASSWORD=mysecret -e TZ=UTC  ubuntu/mysql:8.0-22.04_beta
---

2. docker exec

docker exec command is used to run a command in a running Docker container
-it -> Runs the command interactively with a pseudo-TTY, useful for commands like bash or sh.
mysql-container -> specifict the container name
/bin/bash -> location of the command

---
#docker exec -it mysql-container /bin/bash
---

3. docker ps

Check list of all running containers

-a all include running & stop containers

---
#docker ps -a
---




Step to run your own containers
1/ Create Dockerfile
2/ Build docker image from Dockerfile
3/ Run your docker image 

1/ Create Dockerfile

Docker Template

---
# Step 1: Specify the base image
FROM <base-image>
# Step 2: Add metadata (optional)
LABEL <key>=<value>
# Step 3: Set the working directory
WORKDIR /path/in/container
# Step 4: Copy files from the host to the container
COPY <source> <destination>
ADD <source> <destination>  # (optional for additional features)
# Step 5: Install dependencies
RUN <command>
# Step 6: Expose a port
EXPOSE <port>
# Step 7: Define environment variables
ENV <key>=<value>
# Step 8: Specify the command to run when the container starts
CMD ["executable", "param1", "param2"]
# Or:
ENTRYPOINT ["executable", "param1"]
---

Example: Dockerfile for Wordpress Site

---
FROM php:8.4-apache
WORKDIR /var/www/html
COPY ./php.ini /usr/local/etc/php/conf.d
COPY cih .
---

2. Build Image & run image
# docker build -t app-image .
# docker run -d  -p 8080:80 --name app-container app-image 




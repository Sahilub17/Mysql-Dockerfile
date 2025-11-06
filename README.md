# Mysql-Dockerfile

## 1. Launch EC2 Instances  -- Ubuntu

Connect Instances
-- Go To Root Directory

```shell
sudo -i
```
-- Update Instances

```shell
apt update
```

## 2. Docker Install 

```shell
apt install docker.io -y
```

## 3. Write Dockerfile

```shell
nano dockerfile
```

Then Copy & Paste In dockerfile
ubuntu:22.04  -- this is ubuntu virgin
Password -- Depends you 

```shell
FROM ubuntu:22.04
RUN apt update
RUN apt install mysql-server -y
ENV MYSQL_ROOT_PASSWORD=redhat
EXPOSE 3306
CMD ["mysqld_safe"]
```
then ctrl save & exit 

## 4. Build Dockerfile

```shell
docker build . -t v1
```

## 5. check docker images

```shell
docker images
```

## 6. Docker Container run 

```shell
docker run -d -p 3306:3306 v1
```
-d means detached mode 

## 7. check docker container

```shell
docker ps
```

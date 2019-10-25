## TASK 1.1
```
CONTAINER ID        IMAGE               COMMAND                  CREATED              STATUS                          PORTS               NAMES
d318e0ec5592        nginx               "nginx -g 'daemon of…"   About a minute ago   Up About a minute               80/tcp              quizzical_blackwell
dd520fb3a2d6        nginx               "nginx -g 'daemon of…"   3 minutes ago        Exited (0) About a minute ago                       inspiring_lewin
```
I accidentally removed one of the three too when testing :-) I think it's not big of a deal, since I understand how this works.
## TASK 1.2
```
$ docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
```
## TASK 1.3
```
$ docker run -it devopsdockeruh/pull_exercise
Give me the password: basics
You found the correct password. Secret message is:
"This is the secret message"
```
## TASK 1.4
```
$ docker run -d --name asd devopsdockeruh/exec_bash_exercise
6d66285a1e24981f29554292b375316d7622c1965501578f896015f42a101b27
$ docker exec -it asd bash
root@6d66285a1e24:/usr/app# docker run -it
bash: docker: command not found
root@6d66285a1e24:/usr/app# tail -f ./logs.txt 
Thu, 26 Sep 2019 17:08:29 GMT
Secret message is:
"Docker is easy"
Thu, 26 Sep 2019 17:08:35 GMT
Thu, 26 Sep 2019 17:08:38 GMT
Thu, 26 Sep 2019 17:08:41 GMT
Thu, 26 Sep 2019 17:08:44 GMT
Secret message is:
"Docker is easy"
Thu, 26 Sep 2019 17:08:50 GMT
Thu, 26 Sep 2019 17:08:53 GMT
qThu, 26 Sep 2019 17:08:56 GMT
^C
root@6d66285a1e24:/usr/app# 
```
## TASK 1.5
```
$ docker run -it ubuntu:16.04 sh -c 'apt-get update && apt-get -y install curl && echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'         
Get:1 http://security.ubuntu.com/ubuntu xenial-security InRelease [109 kB]
Get:2 http://archive.ubuntu.com/ubuntu xenial InRelease [247 kB]
Get:3 http://archive.ubuntu.com/ubuntu xenial-updates InRelease [109 kB]
Get:4 http://security.ubuntu.com/ubuntu xenial-security/main amd64 Packages [956 kB]
Get:5 http://archive.ubuntu.com/ubuntu xenial-backports InRelease [107 kB]       

...

Setting up librtmp1:amd64 (2.4+20151223.gitfa8646d-1ubuntu0.1) ...
Setting up libcurl3-gnutls:amd64 (7.47.0-1ubuntu2.14) ...
Setting up libsasl2-modules:amd64 (2.1.26.dfsg1-14ubuntu0.1) ...
Setting up curl (7.47.0-1ubuntu2.14) ...
Processing triggers for libc-bin (2.23-0ubuntu11) ...
Processing triggers for ca-certificates (20170717~16.04.2) ...
Updating certificates in /etc/ssl/certs...
148 added, 0 removed; done.
Running hooks in /etc/ca-certificates/update.d...
done.
Input website:
helsinki.fi
Searching..
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="http://www.helsinki.fi/">here</a>.</p>
</body></html>
```
## TASK 1.6
```
$ docker build . -t docker-clock
Sending build context to Docker daemon  2.048kB
Step 1/2 : FROM devopsdockeruh/overwrite_cmd_exercise
 ---> 0f7f459b76c9
Step 2/2 : CMD ["-c"]
 ---> Running in 099e8578efe4
Removing intermediate container 099e8578efe4
 ---> 44fa68ceab70
Successfully built 44fa68ceab70
Successfully tagged docker-clock:latest
migho@Chernobyl:~/code/docker-course/tasks1/1.6$ docker run docker-clock
1
2

...
```
## TASK 1.7
```
$ docker build . -t curler
Sending build context to Docker daemon  2.048kB
Step 1/3 : FROM ubuntu:16.04
 ---> 657d80a6401d
Step 2/3 : RUN apt-get update && apt-get install -y curl
 ---> Using cache
 ---> 9dd3609533d4
Step 3/3 : CMD echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;
 ---> Running in e9d0266dd585
Removing intermediate container e9d0266dd585
 ---> 636679f534c8
Successfully built 636679f534c8
Successfully tagged curler:latest
migho@Chernobyl:~/code/docker-course/tasks1/1.7$ docker run -it curler
Input website:
helsinki.fi
Searching..
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="http://www.helsinki.fi/">here</a>.</p>
</body></html>
```
## TASK 1.8
```
$ docker run -it -v $(pwd)/logs.txt:/usr/app/logs.txt devopsdockeruh/first_volume_exercise
```
## TASK 1.9
```
$ docker run -it -p 8000:80 devopsdockeruh/ports_exercise
```
## TASK 1.10
```
$ docker build . -t asd
$ docker run -it -p 5000:5000 asd
```
## TASK 1.11
```
$ docker build . -t asd
$ docker run -it -p 8000:8000 -v $(pwd)/logs.txt:/logs.txt asd
```
## TASK 1.12
```
$ docker build . -t back
$ docker run -it -p 8000:8000 back
---
$ docker build . -t front
$ docker run -it -p 5000:5000 front
```
## TASK 1.13
```
$ docker build . -t asd
$ docker run -it -p 8080:8080 asd
```
## TASK 1.14
```
$ docker build . -t asd
$ docker run -it -p :3000:3000 asd
```
## TASK 1.15

https://hub.docker.com/r/migho/sensorfrontend

## TASK 1.16

https://hy-docker-16.herokuapp.com

## TASK 1.17
SKIPPED
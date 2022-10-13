Задание 1

1.
PS C:\Users\Vladimir> docker pull busybox
Using default tag: latest
latest: Pulling from library/busybox
f5b7ce95afea: Pull complete
Digest: sha256:9810966b5f712084ea05bf28fc8ba2c8fb110baa2531a10e2da52c1efc504698
Status: Downloaded newer image for busybox:latest
docker.io/library/busybox:latest

2. 
PS C:\Users\Vladimir> docker run -it --name pinger busybox ping netology.ru -c 7
PING netology.ru (188.114.99.224): 56 data bytes
64 bytes from 188.114.99.224: seq=0 ttl=37 time=36.535 ms
64 bytes from 188.114.99.224: seq=2 ttl=37 time=39.065 ms
64 bytes from 188.114.99.224: seq=3 ttl=37 time=38.992 ms
64 bytes from 188.114.99.224: seq=4 ttl=37 time=38.786 ms
64 bytes from 188.114.99.224: seq=5 ttl=37 time=40.078 ms
64 bytes from 188.114.99.224: seq=6 ttl=37 time=40.172 ms

--- netology.ru ping statistics ---
7 packets transmitted, 6 packets received, 14% packet loss
round-trip min/avg/max = 36.535/38.938/40.172 ms

3.
PS C:\Users\Vladimir> docker ps -a
CONTAINER ID   IMAGE               COMMAND                  CREATED              STATUS                        PORTS                NAMES
a39b88803ca6   busybox             "ping netology.ru -c…"   About a minute ago   Exited (0) 52 seconds ago                          pinger
b828cb9a4cb3   docker101tutorial   "/docker-entrypoint.…"   47 minutes ago       Up 47 minutes                 0.0.0.0:80->80/tcp   docker-tutorial
39edb3b19f8c   alpine/git          "git clone https://g…"   48 minutes ago       Exited (128) 44 minutes ago                        repo

4.
PS C:\Users\Vladimir> docker logs pinger
PING netology.ru (188.114.99.224): 56 data bytes
64 bytes from 188.114.99.224: seq=0 ttl=37 time=36.535 ms
64 bytes from 188.114.99.224: seq=2 ttl=37 time=39.065 ms
64 bytes from 188.114.99.224: seq=3 ttl=37 time=38.992 ms
64 bytes from 188.114.99.224: seq=4 ttl=37 time=38.786 ms
64 bytes from 188.114.99.224: seq=5 ttl=37 time=40.078 ms
64 bytes from 188.114.99.224: seq=6 ttl=37 time=40.172 ms

--- netology.ru ping statistics ---
7 packets transmitted, 6 packets received, 14% packet loss
round-trip min/avg/max = 36.535/38.938/40.172 ms

5.
PS C:\Users\Vladimir> docker start pinger
pinger


6.
PS C:\Users\Vladimir> docker ps -a
CONTAINER ID   IMAGE               COMMAND                  CREATED             STATUS                           PORTS                NAMES
a39b88803ca6   busybox             "ping netology.ru -c…"   21 minutes ago      Exited (0) 4 minutes ago                              pinger
b828cb9a4cb3   docker101tutorial   "/docker-entrypoint.…"   About an hour ago   Up About an hour                 0.0.0.0:80->80/tcp   docker-tutorial
39edb3b19f8c   alpine/git          "git clone https://g…"   About an hour ago   Exited (128) About an hour ago                        repo
\


7.
PS C:\Users\Vladimir> docker logs pinger
PING netology.ru (188.114.99.224): 56 data bytes
64 bytes from 188.114.99.224: seq=0 ttl=37 time=36.535 ms
64 bytes from 188.114.99.224: seq=2 ttl=37 time=39.065 ms
64 bytes from 188.114.99.224: seq=3 ttl=37 time=38.992 ms
64 bytes from 188.114.99.224: seq=4 ttl=37 time=38.786 ms
64 bytes from 188.114.99.224: seq=5 ttl=37 time=40.078 ms
64 bytes from 188.114.99.224: seq=6 ttl=37 time=40.172 ms

--- netology.ru ping statistics ---
7 packets transmitted, 6 packets received, 14% packet loss
round-trip min/avg/max = 36.535/38.938/40.172 ms
PING netology.ru (188.114.99.224): 56 data bytes
64 bytes from 188.114.99.224: seq=0 ttl=37 time=37.030 ms
64 bytes from 188.114.99.224: seq=1 ttl=37 time=39.929 ms
64 bytes from 188.114.99.224: seq=2 ttl=37 time=40.285 ms
64 bytes from 188.114.99.224: seq=3 ttl=37 time=39.549 ms
64 bytes from 188.114.99.224: seq=4 ttl=37 time=38.440 ms
64 bytes from 188.114.99.224: seq=5 ttl=37 time=39.177 ms
64 bytes from 188.114.99.224: seq=6 ttl=37 time=39.384 ms

--- netology.ru ping statistics ---
7 packets transmitted, 7 packets received, 0% packet loss
round-trip min/avg/max = 37.030/39.113/40.285 ms

8.  Количество загрузок : 13

9.
PS C:\Users\Vladimir> docker rm pinger
pinger

10. 
PS C:\Users\Vladimir> docker rmi busybox
Untagged: busybox:latest
Untagged: busybox@sha256:9810966b5f712084ea05bf28fc8ba2c8fb110baa2531a10e2da52c1efc504698
Deleted: sha256:ff4a8eb070e12018233797e865841d877a7835c4c6d5cfc52e5481995da6b2f7
Deleted: sha256:0b16ab2571f4b3e0d5a96b66a00e5016ddc0d268e8bc45dc612948c4c95b94cd

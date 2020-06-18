Hello,

I would like to share with you a method on how to run XtreamUI 22F on any distro, Ubuntu, CentOS, Debian, Windows etc.
All you need to do is install docker and docker composer

You can view this tutorial : https://www.youtube.com/watch?v=eiDSrA8Z-iw

If you're familiar with docker then execute 
```bash
curl -s https://raw.githubusercontent.com/theraw/xtreamui-on-docker/master/docker-compose.yml > xui.yml
docker-compose -f xui.yml up -d
```
After installation is suggested to setup 2 important things [IMPORTANT!!!!]

1. **Change main server IP**
2. **Setup Cronjob, is not needed to add all files on by one all you need to do is**
   `sudo crontab -e`
   **and add this code**
   
   `*/1 * * * * /home/xtreamcodes/run_cron.sh`

this will run all cronjobs that are into /home/xtreamcodes/iptv_xtream_codes/crons folder.



After this everything should be working well however the way how it works you have no "start_services.sh" anymore, 
if you want to restart services you can example to restart nginx you have to only kill it
```bash
killall nginx
killall nginx_rtmp
```
This will stop nginx and supervisord will automatically start it, So all services on case of killall or crash they'll restart by theirself.



Current version is 22F if you want old version you can use 
```bash
docker pull theraw/xtreamui-on-docker:xtream-ui-beta1
```

As far as i've tested Streaming works thus i'm not support 
i'm just giving you a easy way to deploy XtreamUI so please avoid asking me support related questions.



#For noobs

Q: I can't find xtreamui files?

A: Your files are not directly on your server but are into a docker container, a docker container is like a very small server into your server, if that makes no sense then think like you're using virtualbox to create a server that's close to docker containers, 
but how to access files now?
```bash
# Access docker container 
docker exec -it xui bash

#Find xtreamui files
ls /home/xtreamcodes

# exit docker container
exit

# List all your containers created on your server.
docker ps
```

Q: But how do you create a small server into my server i don't think my server can handle that?

A: It can handle it docker containers are similar to virtualbox or vmware but is not the same and resource usage is very low that means you can still use docker even if you have only 2GB Ram, 1vCore.

Q: Ok how to start stop this docker container?

A:
```bash
#stop
docker stop xui

#start
docker start xui

#logs
docker logs xui

#"xui" is container name, to list all docker commands execute docker --help
# when you login into a docker container with
docker exec -it xui bash
# this means that from now on you'll see only files that are inside this container and all proccess list is only proccess list
# which are running into container, Container Distro can change is not the same as your server
# example your server can have ubuntu 14 but your container can be debian 10.
```

Follow Me for future releases

https://www.youtube.com/channel/UC3GYfx-3XOn7eLk-B_ZTLgg

https://github.com/theraw

https://github.com/theraw/xtreamui-on-docker





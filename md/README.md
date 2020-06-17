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



After this everything whould be working well however the way how it works you have no "start_services.sh" anymore, 
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


Follow Me for future releases

https://www.youtube.com/channel/UC3GYfx-3XOn7eLk-B_ZTLgg

https://github.com/theraw

https://github.com/theraw/xtreamui-on-docker





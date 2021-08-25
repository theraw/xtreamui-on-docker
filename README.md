My point with this project was to compile nginx/php and mysql to run on a docker container so xtream-ui could work in it.

MY POINT WAS NOT TO GIVE YOU A FREE 100% FULL WORKING XTREAM-UI READY TO BE USED. I already stated that but ppl keep using "issues" to ask question unrelated to my project so issues are now gone!

# Xtreamui On Docker (22F)
[![Install Xtream-UI in 3 Sec ? (Xtream-UI on Docker Container 2020)](https://github.com/theraw/xtreamui-on-docker/raw/master/scr/s1.png)](https://youtu.be/eiDSrA8Z-iw "Install Xtream-UI in 3 Sec ? (Xtream-UI on Docker Container 2020)")

```bash
curl -s https://raw.githubusercontent.com/theraw/xtreamui-on-docker/master/docker-compose.yml > xui.yml

docker-compose -f xui.yml up -d
```

Then visit admin panel on http://PUBLIC_IP:25500/ (user : `admin` password : `admin`)

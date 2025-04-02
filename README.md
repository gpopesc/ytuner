
![image](https://github.com/gpopesc/ytuner/blob/main/n50a.png)

# Project forked from https://github.com/coffeegreg/YTuner

Use the project link for more details. The original Docker installation using network: host is here:
https://github.com/coffeegreg/YTuner/blob/master/doc/DOCKER.md

This version is adapted to use docker-compose and a private IP address from your network.
I use Synology, I couldn’t run it directly because my web services and DNS container already occupy ports 80 and 53.
Check with following commands if the ports are in use for your machine:
>netstat -tulpn -S | grep 53
>
>netstat -tulpn -S | grep 80
>
If the ports are not used you can use :  network_mode: "host"  in docker-compose file

It uses ytuner version 1.2.6—change the binaries as needed.
This build was tested with a *Pioneer N-50A*.
Use wired connection, sometimes wireless connection is not taking the IP address and the container is not connected to internet.

The original website, pioneer.vtuner.com, is no longer functional and has been completely abandoned.
# Ytuner has revived my network player *Pioneer N-50A*!

**Instalation:**
>git clone https://github.com/gpopesc/ytuner.git
>
>cd ytuner
>
>ip -br a #*and select your interface, then change it in your docker compose*
>

Modify the fixed available IP address from your network, the subnet, and gateway accordingly in docker-compose, then:

>docker-compose build
>
>docker-compose up -d
>
First time wait about 1 minute to complete download of radio database and check the docker log file if everything is running. 

The log should look like below:

`YTuner v1.2.6 Copyright (c) 2024 Greg P. (https://github.com/coffeegreg)`

`31-3-25 22:17:25 : Inf : Starting services...`

`31-3-25 22:17:25 : Inf : Successfully loaded 11 my stations.`

`31-3-25 22:17:25 : Dbg : Database library : 3.44.2.`

`31-3-25 22:17:25 : Inf : Checking local database.`

`31-3-25 22:17:25 : Inf : Local database is ready.`

`31-3-25 22:17:25 : Inf : DNS Service: listening on: 192.168.1.170:53.`

`31-3-25 22:17:25 : Inf : Web Service: listening on: 192.168.1.170:80.`

**Setup the network player:**

Access the network player on web interface (search for its ip in router or in network player info)

Change DHCP to OFF and change the DNS to the ytuner IP defined earlier
![image](https://github.com/gpopesc/ytuner/blob/main/pioneer.png)

Now when player is trying to connect to pioneer.vtuner.com it is automatically redirected to local ytuner.

*******************************************************************
# Below the original description: YTuner

YTuner is a simple project inspired by YCast but rewritten from scratch and greatly improved. Designed to replace vTuner internet radio service and dedicated to all users of AVRs made by Yamaha, Denon, Onkyo, Marantz, Grundig and others with built-in vTuner support. If you own one (or even more) of the vTuner-enabled AVRs mentioned above and want to enjoy free internet radio stations on your device as before, and be sure that your device's streaming service won't suddenly end, you should consider using YTuner.
Why

YCast is a great project, but my goal was to run a similar service on a very low-spec platform where python along with packages turned out to be too heavy and too slow. Now, with YTuner you can enjoy improved functionality at full speed of ultra lightweight native app on operating systems such as:


or any others powered by cross-build abilities of Free Pascal Compiler.
Features

YTuner supports :

    Custom stations list files (aka MyStations) : YAML files (YCast compatible) or INI files.
    Great Radio-browser.info functionality.
    AVR bookmarks. Single bookmark for many AVRs or dedicated bookmark for each AVR (if you own more then one) with support of "add" and "del" operations sent from AVR devices.
    Easy application configuration with ini files.
    Optional SSL support for YTuner HTTPS web request.
    Radio stations logo images conversion/resize on the fly with couple of supported image formats (JPG,PNG,GIF,TIFF-optional)
    Radio stations logo images optional cache.
    Radio-browser extensive caching with many options and auto refresh
        UUIDs, data structures and stations cache (based on files or RAM storage).
        Local DB based full cache of Radio-browser resources.
    Radio-browser advanced filtering and sorting (single config for many AVRs or dedicated configs for each AVR (if you own more then one))
    Radio-browser menu/submenu translator (for non-English users)

YTuner also has build in :

    Web service to support AVR requests.
    Optional DNS proxy service to intercept vtuner.com related DNS queries and others if needed.
    Maintenance service.

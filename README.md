# Project forked from https://github.com/coffeegreg/YTuner

Use the project link for more details. The original Docker installation using network: host is here:
https://github.com/coffeegreg/YTuner/blob/master/doc/DOCKER.md

This version is adapted to use docker-compose and a private IP address from your network.
I use Synology, I couldn’t run it directly because my web services and DNS container already occupy ports 80 and 53.

It uses ytuner version 1.2.6—change the binaries as needed.
This build was tested with a *Pioneer N-50A*.

The original website, pioneer.vtuner.com, is no longer functional and has been completely abandoned.
# Ytuner has revived my network player *Pioneer N-50A*!

>git clone https://github.com/gpopesc/ytuner.git
>
>cd ytuner
>
>ip -br a #*and select your interface, then change it in your docker compose*
>
modify the fixed available IP address from yout network, the subnet and gateway acordingly in docker-compose then:

>docker-compose build
>
>docker-compose up -d
> 





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

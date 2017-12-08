**Notes on Fork**

- Because the mechanism for auto-generating the config.php is buggy, with regards boolean variables, (as they are written inside quotes),
in this fork, that mechanism is disabled, and the config file is added directly instead as a workaround.
- Hence, *probably broken for docker compose*.

To build:
(update config.php, see: https://web.archive.org/web/20161114165150/http://rockmongo.com/wiki/configuration?lang=en_us)

```$ sudo docker build -t benblamey/rockmongo .```

To run:

```$ sudo docker run -d -p 80:80 benblamey/rockmongo```

To run on startup:

```$crontab -e```

And add:

```@reboot docker run -d -p 80:80 benblamey/rockmongo```

-----


**Overview**

The docker build based on Ubuntu 14.04 and Rockmongo 1.1.7. If you want to build other versions of the rockmongo, just replace the "builds/rockmongo-[version].zip".

The Original Rockmongo repository: https://github.com/iwind/rockmongo


**Features**

* All awesome features provided by Rockmongo.
* You can plugin the "JSON Formatted Configurations" as environment variable which allows you to replace all variables in the rockmongo config.php and also supports multiple servers configurations. 
* Providing not only Docker Compose example as well as Docker Cloud example.

**Run**

`docker run -d -p 80:80 -e 'MONGO_CONF=[{"mongo_name":"Test DB","mongo_host":"test-db","mongo_port":"27017","mongo_auth":"true"}]' cosmostail/dockercloud-rockmongo `

**Docker Compose**

`docker-compose up -d`

**Docker Cloud**



![alt tag](https://github.com/cosmostail/dockercloud-rockmongo/blob/master/images/step1.png)
![alt tag](https://github.com/cosmostail/dockercloud-rockmongo/blob/master/images/step2.png)

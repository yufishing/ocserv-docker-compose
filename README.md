# OpenConnect VPN Server  

A OpenConnect VPN server in docker, it supports certificate and password authentication by default, can simply create users by embind commands.

* Get Started  
  * Generate default config file  
    `$ docker run --rm yufishing/ocserv:latest cat /etc/ocserv/ocserv.conf`  
  
  * Start service in container  
    `$ docker run --privileged  -d --restart=always -p [ext-port]:443 -v [local-dir]:/etc/ocserv yufishing/ocserv:latest  `  
    local-dir: Put the customized config file in local dir and mount in container.

  * To create password authentication user  
    `$ docker exec [container] ocpasswd [username]`  

  * To create certificate authentication user  
    `$ docker exec [container] ocserv-cert-user -u [username] -d [expire-days] -p [password] > [username].p12`  
    If without specify password, the default is password 

* Use Docker Compose    
  $ docker compose up
  



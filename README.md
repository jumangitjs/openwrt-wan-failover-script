# Simple Openwrt Failover Script

### How to install?
Download _.zip_ files
``` wget https://github.com/GTANAdam/openwrt-wan-failover-script/archive/refs/tags/Release.zip ```

Extract _.zip_ file in  **/tmp** folder
```cd /tmp```	
``` unzip Release.zip ```

Move files in **www** folder to **/www** folder
``` mv www/ /www/ ```

Move folder **failover** to **/etc/**
``` mv failover /etc/failover/ ```

### How to configure script?
Edit **failover.sh**
``` vi /etc/failover/failover.sh ```

Edit variables between comments **_# Begin Configuration #_** and **_# Begin Configuration #_**

### How to start script?
Configure your crontab file
``` */2 * * * * /etc/failover/failover.sh ```

Restart crontab service
``` /etc/init.d/cron reload ```

# Simple Openwrt Failover Script

### How to install?
Download _.zip_ files
```
wget https://github.com/GTANAdam/openwrt-wan-failover-script/archive/refs/tags/Release.tar.gz
```

Extract _.tar.gz_ file in  **/tmp** folder
```
tar -xzf Release -C /tmp
```

Move failover html files in **www** folder
```
cd /tmp/openwrt-wan-failover-script-Release
chmod a+xrw *
mv www/* /www/
```

Move folder **failover** to **/etc/**
```
cd /tmp/openwrt-wan-failover-script-Release
cd failover
chmod a+xrw *
mv failover/* /etc/failover/
```

### How to configure script?
Edit **failover.sh**
```
vi /etc/failover/failover.sh
```

Edit variables between comments **_# Begin Configuration #_** and **_# Begin Configuration #_**
assumptions:
* physical _device_ wan is eth1
* main _wan interface_ is wan
* failover _device_ wireless wan is wlan0
* failover _wan_ interface is wwan

### How to start script?
Configure your crontab file
```
*/2 * * * * /etc/failover/failover.sh
```

Restart crontab service
```
/etc/init.d/cron reload
```

# zabbix template for zfs on linux

this template uses zpool, zfs and zvol discovery so you will have all information about all zfs items available by default.

## items:
- discovered: zpool information (health! and others)
- discovered: zfs information (used, used by snapshots, avail and others)
- discovered: zvol information (used, used by snapshots, used by children, avail and others)
- zfs parameters (/sys/module/zfs/parameters/*). you can get these yourself by creating an item: zfs.parameter[<parametername>]
- zfs properties (zfs get -o name,value,source,property <propertyname> <zfsname>). you can get these yourself by creating an item: zfs.get[<zfsname>,<propertyname>]
 - zpool properties (zpool get -o name,value,source,property <propertyname> <zpoolname>). you can get these yourself by creating an item: zpool.get[<zfsname>,<propertyname>]

## triggers:
- zpool health

## graphs:
- overwiew for zpools
- overview for zfs filesystems
- overview for zfs zvols


## installation 
1. place this file in /etc/zabbix/zabbix_agentd.conf.d/
2. restart zabbix agent
3. import the template.xml file in the zabbix gui

## sources
- https://zfsonlinux.org/
- https://www.zabbix.com/documentation/3.4/manual

# zabbix template for zfs on linux

this template uses zpool, zfs and zvol discovery so you will have all information about all zfs items available by default.

## items:
- discovered: zpool information (health! and others)
- discovered: zfs information (used, used by snapshots, avail and others)
- discovered: zvol information (used, used by snapshots, used by children, avail and others)
- zfs parameters (```/sys/module/zfs/parameters/*```). you can get these yourself by creating an item: ```zfs.parameter[<parametername>]```
- zfs properties (```zfs get -o name,value,source,property <propertyname> <zfsname>```). you can get these yourself by creating an item: ```zfs.get[<zfsname>,<propertyname>]```
 - zpool properties (```zpool get -o name,value,source,property <propertyname> <zpoolname>```). you can get these yourself by creating an item: ```zpool.get[<zpoolname>,<propertyname>]```

## triggers:
- discovered: zpool health

## graphs:
- discovered: overwiew for zpools
- discovered: overview for zfs filesystems
- discovered: overview for zfs zvols

## custom:
- roll your own by creating items, triggers and graphs with the use of zfs.get[zfsname,property], zpool.get[zpoolname,property] and zfs.parameter[parametername]


## installation and usage
1. place this file in /etc/zabbix/zabbix_agentd.conf.d/
2. restart zabbix agent
3. import the template.xml file in the zabbix gui
4. in case the discovery items are not suffucient, roll your own. see the custom section

## sources
- https://zfsonlinux.org/
- https://www.zabbix.com/documentation/3.4/manual

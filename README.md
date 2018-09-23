zabbix template for zfs on linux

this template uses zpool, zfs and zvol discovery so you will have all information about all zfs items available by default.

items:
- zpool information (health!)
- zfs information (used, used by snapshots, free etc)
- zvol information (used, used by snapshots, used by children, free etc)

triggers:
- zpool health

graphs:
- overwiew for zpools
- overview for zfs filesystems
- overview for zfs zvols

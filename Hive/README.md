# Hive

![Closed.jpg](./Closed.jpg)

![Open.jpg](./Open.jpg)

![HIVE.jpg](./HIVE.jpg)


### Components

* 1 x Raspberry Pi 5 16gb
* 1 x 256gb SD card
* 1 x [GS041033 Standalone LoRa PCB](../GS041033/README.md)
* 1 x Radio Antenna


### Description

The base station provides a web interface to control up to 10 WISPs.


### Firmware

GS041033 Standalone LoRa PCB firmware was extracted using the procedure outlined [here](../GS041033/README.md)

[HIVE.bin](./artifacts/HIVE.bin)


### Digital Forensics

#### Operating System

OS: `Ubuntu`

Hostname: `weatherhive-sharpee4`

wlan: `10.42.0.1`

lan ipv4 not configured

lan ipv6 is configured possibly by mistake


#### Port Scan

`$` `nmap 10.42.0.1`
```
Starting Nmap 7.95 ( https://nmap.org ) at 2026-06-23 19:46 EDT
Nmap scan report for weatherhive-sharpee4 (10.42.0.1)
Host is up (0.012s latency).
Not shown: 992 closed tcp ports (conn-refused)
PORT     STATE SERVICE
22/tcp   open  ssh
53/tcp   open  domain
80/tcp   open  http
3000/tcp open  ppp
5000/tcp open  upnp
5432/tcp open  postgresql
8080/tcp open  http-proxy
9090/tcp open  zeus-admin

Nmap done: 1 IP address (1 host up) scanned in 0.20 seconds
```

#### Credentials

User account credentials cracked from [`/etc/shadow`](./artifacts/shadow) file pulled from SD card.

```
$ john shadow
Using default input encoding: UTF-8
Loaded 1 password hash (sha256crypt, crypt(3) $5$ [SHA256 256/256 AVX2 8x])
Cost 1 (iteration count) is 5000 for all loaded hashes
Will run 22 OpenMP threads
Proceeding with single, rules:Single
Press 'q' or Ctrl-C to abort, almost any other key for status
hive             (hive_pc)
1g 0:00:00:00 DONE 1/3 (2026-06-23 14:23) 50.00g/s 8800p/s 8800c/s 8800C/s hive_pc..HIVEHIVE_PC
Use the "--show" option to display all of the cracked passwords reliably
Session completed.
```

Username: `hive_pc`
Password: `hive`


#### Sockets

`$` `netstat -ano`

```
Active Internet connections (servers and established)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       Timer
tcp        0      0 0.0.0.0:34907           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:35253           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:43365           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:35105           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:43691           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 127.0.0.54:53           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:43929           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:11311           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:44933           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:44931           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:33273           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 10.42.0.1:53            0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:9090            0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:47447           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:40433           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:24224           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:8080            0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:5000            0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:37801           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:5432            0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 0.0.0.0:38459           0.0.0.0:*               LISTEN      off (0.00/0/0)
tcp        0      0 127.0.0.1:50046         127.0.1.1:47447         ESTABLISHED keepalive (54.19/0/0)
tcp        0      0 127.0.0.1:54390         127.0.1.1:35253         ESTABLISHED keepalive (1.03/0/0)
tcp        0      0 127.0.0.1:24224         127.0.0.1:39064         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.1.1:44931         127.0.0.1:37074         ESTABLISHED keepalive (1.03/0/0)
tcp        0      0 127.0.1.1:47447         127.0.0.1:50054         ESTABLISHED keepalive (5.13/0/0)
tcp        0      0 127.0.0.1:24224         127.0.0.1:39054         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.0.1:34494         127.0.1.1:35105         ESTABLISHED keepalive (1.03/0/0)
tcp        0      0 127.0.0.1:51828         127.0.0.1:11311         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.0.1:11311         127.0.0.1:51844         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.0.1:11311         127.0.0.1:51828         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.0.1:51812         127.0.0.1:11311         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.0.1:50058         127.0.1.1:47447         ESTABLISHED keepalive (5.13/0/0)
tcp        0      0 127.0.0.1:39054         127.0.0.1:24224         ESTABLISHED keepalive (7.06/0/0)
tcp        0      0 127.0.0.1:39068         127.0.0.1:24224         ESTABLISHED keepalive (14.26/0/0)
tcp        0      0 127.0.0.1:9090          127.0.0.1:49580         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.0.1:51866         127.0.0.1:11311         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.0.1:39064         127.0.0.1:24224         ESTABLISHED keepalive (0.00/0/0)
tcp        0      0 127.0.0.1:11311         127.0.0.1:51856         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.0.1:51856         127.0.0.1:11311         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.1.1:35253         127.0.0.1:54390         ESTABLISHED off (0.00/0/0)
tcp        0   3248 10.42.0.1:22            10.42.0.183:42518       ESTABLISHED on (0.04/0/0)
tcp        0      0 127.0.0.1:11311         127.0.0.1:51812         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.0.1:11311         127.0.0.1:51842         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.0.1:50028         127.0.1.1:47447         ESTABLISHED keepalive (1.03/0/0)
tcp        0      0 127.0.0.1:11311         127.0.0.1:51866         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.1.1:44933         127.0.0.1:44614         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.1.1:35105         127.0.0.1:34494         ESTABLISHED keepalive (1.03/0/0)
tcp        0      0 127.0.1.1:47447         127.0.0.1:50046         ESTABLISHED keepalive (54.19/0/0)
tcp        0      0 127.0.1.1:37801         127.0.0.1:53728         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.1.1:47447         127.0.0.1:50058         ESTABLISHED keepalive (5.13/0/0)
tcp        0      0 127.0.1.1:38459         127.0.0.1:43832         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.1.1:47447         127.0.0.1:50028         ESTABLISHED keepalive (1.03/0/0)
tcp        0      0 127.0.0.1:51844         127.0.0.1:11311         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.0.1:43828         127.0.1.1:38459         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.0.1:24224         127.0.0.1:39068         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.0.1:50054         127.0.1.1:47447         ESTABLISHED keepalive (5.13/0/0)
tcp        0      0 127.0.0.1:43228         127.0.0.1:3000          TIME_WAIT   timewait (14.51/0/0)
tcp        0      0 127.0.0.1:44614         127.0.1.1:44933         ESTABLISHED keepalive (1.03/0/0)
tcp        0      0 127.0.0.1:53728         127.0.1.1:37801         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.0.1:49580         127.0.0.1:9090          ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.0.1:37074         127.0.1.1:44931         ESTABLISHED keepalive (1.03/0/0)
tcp        0      0 127.0.0.1:51842         127.0.0.1:11311         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.1.1:38459         127.0.0.1:43828         ESTABLISHED off (0.00/0/0)
tcp        0      0 127.0.0.1:43832         127.0.1.1:38459         ESTABLISHED off (0.00/0/0)
tcp6       0      0 :::3000                 :::*                    LISTEN      off (0.00/0/0)
tcp6       0      0 :::80                   :::*                    LISTEN      off (0.00/0/0)
tcp6       0      0 :::22                   :::*                    LISTEN      off (0.00/0/0)
tcp6       0      0 :::8080                 :::*                    LISTEN      off (0.00/0/0)
tcp6       0      0 :::5000                 :::*                    LISTEN      off (0.00/0/0)
tcp6       0      0 :::5432                 :::*                    LISTEN      off (0.00/0/0)
udp        0      0 0.0.0.0:44586           0.0.0.0:*                           off (0.00/0/0)
udp        0      0 0.0.0.0:52824           0.0.0.0:*                           off (0.00/0/0)
udp        0      0 0.0.0.0:37248           0.0.0.0:*                           off (0.00/0/0)
udp        0      0 0.0.0.0:45512           0.0.0.0:*                           off (0.00/0/0)
udp        0      0 0.0.0.0:46205           0.0.0.0:*                           off (0.00/0/0)
udp        0      0 0.0.0.0:5353            0.0.0.0:*                           off (0.00/0/0)
udp        0      0 0.0.0.0:54670           0.0.0.0:*                           off (0.00/0/0)
udp        0      0 0.0.0.0:24224           0.0.0.0:*                           off (0.00/0/0)
udp        0      0 10.42.0.1:53            0.0.0.0:*                           off (0.00/0/0)
udp        0      0 127.0.0.54:53           0.0.0.0:*                           off (0.00/0/0)
udp        0      0 127.0.0.53:53           0.0.0.0:*                           off (0.00/0/0)
udp        0      0 0.0.0.0:67              0.0.0.0:*                           off (0.00/0/0)
udp6       0 160320 :::5353                 :::*                                off (0.00/0/0)
udp6       0      0 :::39232                :::*                                off (0.00/0/0)
Active UNIX domain sockets (servers and established)
Proto RefCnt Flags       Type       State         I-Node   Path
unix  12     [ ]         DGRAM      CONNECTED     6469     /run/systemd/journal/dev-log
unix  8      [ ]         DGRAM      CONNECTED     7309     /run/systemd/journal/socket
unix  3      [ ]         STREAM     CONNECTED     14836
unix  3      [ ]         STREAM     CONNECTED     12779    /run/containerd/s/6b08e93fd5bc61fd8d72ae20a3c66f7c372388cf098137358cf35698a82797df
unix  2      [ ACC ]     STREAM     LISTENING     7311     /run/systemd/journal/stdout
unix  2      [ ACC ]     SEQPACKET  LISTENING     1230     /run/udev/control
unix  2      [ ]         DGRAM      CONNECTED     39633
unix  3      [ ]         STREAM     CONNECTED     14479    /run/containerd/s/43db2be0b05a53c5efd3031c4508c07acf6371f634afd6b9deb81bb8dd4aa18b
unix  3      [ ]         STREAM     CONNECTED     11910
unix  3      [ ]         STREAM     CONNECTED     10211
unix  3      [ ]         STREAM     CONNECTED     14874
unix  3      [ ]         STREAM     CONNECTED     13588    /run/docker.sock
unix  2      [ ACC ]     STREAM     LISTENING     804      /run/systemd/journal/io.systemd.journal
unix  2      [ ACC ]     STREAM     LISTENING     10208    /var/run/docker/metrics.sock
unix  3      [ ]         STREAM     CONNECTED     39765
unix  3      [ ]         STREAM     CONNECTED     13206
unix  3      [ ]         STREAM     CONNECTED     14410    /run/containerd/containerd.sock.ttrpc
unix  2      [ ]         DGRAM                    41991    /run/user/1000/systemd/notify
unix  2      [ ACC ]     STREAM     LISTENING     41994    /run/user/1000/systemd/private
unix  2      [ ACC ]     STREAM     LISTENING     42002    /run/user/1000/bus
unix  3      [ ]         STREAM     CONNECTED     13159    /run/containerd/s/74542567650b8b67f98637ddcb4aa5aa41f8496e72b9b75f6047ec51a637295c
unix  3      [ ]         STREAM     CONNECTED     13587
unix  2      [ ACC ]     STREAM     LISTENING     42003    /run/user/1000/gnupg/S.dirmngr
unix  3      [ ]         STREAM     CONNECTED     14837
unix  2      [ ACC ]     STREAM     LISTENING     42005    /run/user/1000/gnupg/S.gpg-agent.browser
unix  2      [ ACC ]     STREAM     LISTENING     42007    /run/user/1000/gnupg/S.gpg-agent.extra
unix  2      [ ACC ]     STREAM     LISTENING     42009    /run/user/1000/gnupg/S.gpg-agent
unix  3      [ ]         STREAM     CONNECTED     14346
unix  2      [ ACC ]     STREAM     LISTENING     42011    /run/user/1000/gnupg/S.keyboxd
unix  2      [ ACC ]     STREAM     LISTENING     42013    /run/user/1000/pk-debconf-socket
unix  2      [ ACC ]     STREAM     LISTENING     42015    /run/user/1000/snapd-session-agent.socket
unix  2      [ ACC ]     STREAM     LISTENING     39674    /run/user/1000/gnupg/S.gpg-agent.ssh
unix  3      [ ]         STREAM     CONNECTED     13607
unix  3      [ ]         STREAM     CONNECTED     10956    /run/containerd/containerd.sock
unix  3      [ ]         STREAM     CONNECTED     12231    /run/containerd/containerd.sock.ttrpc
unix  3      [ ]         STREAM     CONNECTED     10915    @docker_cli_2cae881dac42944405ecf3dc4384f72b
unix  3      [ ]         STREAM     CONNECTED     14166    /run/containerd/containerd.sock.ttrpc
unix  3      [ ]         STREAM     CONNECTED     14529    /run/containerd/s/b91fe156c64612398ec4fc3ef22ac57b747a9095cd4d95dc34069711b875512b
unix  2      [ ACC ]     STREAM     LISTENING     11137    /var/run/docker/libnetwork/17cd2df8d9ce.sock
unix  2      [ ACC ]     STREAM     LISTENING     10399    /run/systemd/resolve/io.systemd.Resolve
unix  2      [ ACC ]     STREAM     LISTENING     10400    /run/systemd/resolve/io.systemd.Resolve.Monitor
unix  3      [ ]         STREAM     CONNECTED     14528
unix  3      [ ]         STREAM     CONNECTED     13615
unix  3      [ ]         STREAM     CONNECTED     11202    /run/containerd/s/d6c526d191620b12979139712c05d68e517b096b170d0c8384758bae9ff30c92
unix  3      [ ]         STREAM     CONNECTED     14409
unix  3      [ ]         STREAM     CONNECTED     12149
unix  3      [ ]         STREAM     CONNECTED     39764
unix  3      [ ]         STREAM     CONNECTED     15536
unix  2      [ ]         DGRAM      CONNECTED     10662
unix  2      [ ]         DGRAM      CONNECTED     807
unix  2      [ ]         DGRAM      CONNECTED     38895
unix  2      [ ACC ]     STREAM     LISTENING     11198    /run/containerd/s/2224dbd3f3ba74888787b00a7d33e2f3a68fc4c62bc30127bc84269e1677fdbe
unix  3      [ ]         STREAM     CONNECTED     10656    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     12762
unix  2      [ ACC ]     STREAM     LISTENING     12145    /run/containerd/s/d6c526d191620b12979139712c05d68e517b096b170d0c8384758bae9ff30c92
unix  3      [ ]         STREAM     CONNECTED     13816    /run/containerd/containerd.sock.ttrpc
unix  3      [ ]         STREAM     CONNECTED     6645
unix  3      [ ]         STREAM     CONNECTED     6963     /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     36861    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     10561
unix  2      [ ACC ]     STREAM     LISTENING     10462    /run/avahi-daemon/socket
unix  3      [ ]         STREAM     CONNECTED     7486     /run/systemd/journal/stdout
unix  2      [ ACC ]     STREAM     LISTENING     10463    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     8929
unix  2      [ ACC ]     STREAM     LISTENING     10464    /run/docker.sock
unix  3      [ ]         DGRAM      CONNECTED     6444
unix  3      [ ]         STREAM     CONNECTED     15559
unix  2      [ ]         DGRAM      CONNECTED     10650
unix  2      [ ACC ]     STREAM     LISTENING     10467    /run/lxd-installer.socket
unix  3      [ ]         DGRAM      CONNECTED     41993
unix  2      [ ACC ]     STREAM     LISTENING     10469    /run/snapd.socket
unix  3      [ ]         STREAM     CONNECTED     11452    /run/systemd/journal/stdout
unix  2      [ ACC ]     STREAM     LISTENING     10471    /run/snapd-snap.socket
unix  2      [ ]         DGRAM      CONNECTED     9960
unix  2      [ ACC ]     STREAM     LISTENING     10477    /run/uuidd/request
unix  2      [ ACC ]     STREAM     LISTENING     14852    /tmp/SERVERENGINE_SOCKETMANAGER_2026-06-23T17:40:06Z_7
unix  3      [ ]         STREAM     CONNECTED     12891    /run/containerd/containerd.sock.ttrpc
unix  3      [ ]         STREAM     CONNECTED     10657    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     40060    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     12758
unix  3      [ ]         STREAM     CONNECTED     14457    /run/docker.sock
unix  3      [ ]         STREAM     CONNECTED     13573    /run/containerd/containerd.sock
unix  3      [ ]         STREAM     CONNECTED     10560
unix  3      [ ]         STREAM     CONNECTED     8856
unix  3      [ ]         STREAM     CONNECTED     15486
unix  2      [ ]         DGRAM      CONNECTED     38902
unix  3      [ ]         DGRAM      CONNECTED     6655
unix  3      [ ]         STREAM     CONNECTED     12761
unix  3      [ ]         STREAM     CONNECTED     10651
unix  2      [ ]         DGRAM      CONNECTED     6651
unix  2      [ ]         DGRAM      CONNECTED     856
unix  3      [ ]         DGRAM      CONNECTED     41992
unix  3      [ ]         STREAM     CONNECTED     13725    /run/containerd/s/e02cb427662339f978693486185aaff4f00734eca4d2600e03340750d1ee7a3d
unix  3      [ ]         STREAM     CONNECTED     10573
unix  3      [ ]         STREAM     CONNECTED     12763
unix  2      [ ]         DGRAM      CONNECTED     9601
unix  3      [ ]         STREAM     CONNECTED     9587     /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     8424
unix  3      [ ]         STREAM     CONNECTED     15376
unix  3      [ ]         STREAM     CONNECTED     10602    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     10579
unix  3      [ ]         DGRAM      CONNECTED     6445
unix  3      [ ]         STREAM     CONNECTED     10655    /run/dbus/system_bus_socket
unix  3      [ ]         DGRAM      CONNECTED     6656
unix  3      [ ]         STREAM     CONNECTED     10652
unix  3      [ ]         STREAM     CONNECTED     15494
unix  3      [ ]         STREAM     CONNECTED     9646
unix  2      [ ]         STREAM     CONNECTED     38853
unix  2      [ ]         DGRAM      CONNECTED     9650
unix  3      [ ]         STREAM     CONNECTED     10642
unix  3      [ ]         STREAM     CONNECTED     14455    /run/docker.sock
unix  3      [ ]         STREAM     CONNECTED     15487    /run/containerd/containerd.sock.ttrpc
unix  3      [ ]         STREAM     CONNECTED     14453    /run/docker.sock
unix  3      [ ]         STREAM     CONNECTED     10659    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     10660    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     38886
unix  3      [ ]         STREAM     CONNECTED     12759    /run/docker.sock
unix  2      [ ACC ]     STREAM     LISTENING     12764    /run/containerd/s/43db2be0b05a53c5efd3031c4508c07acf6371f634afd6b9deb81bb8dd4aa18b
unix  3      [ ]         STREAM     CONNECTED     11561    /run/systemd/journal/stdout
unix  2      [ ]         DGRAM      CONNECTED     7883
unix  2      [ ACC ]     STREAM     LISTENING     15439    /run/containerd/s/6b08e93fd5bc61fd8d72ae20a3c66f7c372388cf098137358cf35698a82797df
unix  3      [ ]         DGRAM      CONNECTED     7892
unix  3      [ ]         STREAM     CONNECTED     7839
unix  3      [ ]         DGRAM      CONNECTED     7894
unix  3      [ ]         STREAM     CONNECTED     6956     /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     10654    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     11451
unix  2      [ ACC ]     STREAM     LISTENING     14524    /run/containerd/s/b91fe156c64612398ec4fc3ef22ac57b747a9095cd4d95dc34069711b875512b
unix  3      [ ]         STREAM     CONNECTED     9503     /run/systemd/journal/stdout
unix  3      [ ]         DGRAM      CONNECTED     7895
unix  3      [ ]         DGRAM      CONNECTED     7893
unix  2      [ ACC ]     STREAM     LISTENING     14568    /run/containerd/s/e02cb427662339f978693486185aaff4f00734eca4d2600e03340750d1ee7a3d
unix  3      [ ]         STREAM     CONNECTED     11678    /run/systemd/journal/stdout
unix  2      [ ]         DGRAM                    11605
unix  2      [ ]         DGRAM      CONNECTED     2022
unix  3      [ ]         STREAM     CONNECTED     11518
unix  3      [ ]         STREAM     CONNECTED     28238
unix  3      [ ]         STREAM     CONNECTED     12646    /run/containerd/s/2224dbd3f3ba74888787b00a7d33e2f3a68fc4c62bc30127bc84269e1677fdbe
unix  3      [ ]         STREAM     CONNECTED     9808     /run/dbus/system_bus_socket
unix  2      [ ]         DGRAM                    9187     /run/wpa_supplicant/wlan0
unix  3      [ ]         STREAM     CONNECTED     11496
unix  3      [ ]         STREAM     CONNECTED     9812
unix  2      [ ]         DGRAM                    9192     /run/wpa_supplicant/p2p-dev-wlan0
unix  3      [ ]         STREAM     CONNECTED     10671
unix  3      [ ]         STREAM     CONNECTED     14710
unix  3      [ ]         STREAM     CONNECTED     9649     /run/systemd/journal/stdout
unix  2      [ ACC ]     STREAM     LISTENING     7592     /run/systemd/io.systemd.sysext
unix  3      [ ]         STREAM     CONNECTED     11818
unix  3      [ ]         STREAM     CONNECTED     16032    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     10658    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     10834    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     11585
unix  3      [ ]         STREAM     CONNECTED     11551    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     9979     /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     11201
unix  3      [ ]         STREAM     CONNECTED     10209    /run/containerd/containerd.sock
unix  3      [ ]         STREAM     CONNECTED     8959
unix  2      [ ]         DGRAM      CONNECTED     11820
unix  3      [ ]         STREAM     CONNECTED     9803
unix  2      [ ]         DGRAM                    8940
unix  3      [ ]         STREAM     CONNECTED     9584     /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     8968     /run/dbus/system_bus_socket
unix  2      [ ]         DGRAM      CONNECTED     10670
unix  3      [ ]         STREAM     CONNECTED     9813
unix  3      [ ]         STREAM     CONNECTED     9195
unix  3      [ ]         STREAM     CONNECTED     8897     /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     9176
unix  3      [ ]         STREAM     CONNECTED     11604    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     27628    /run/systemd/journal/stdout
unix  2      [ ACC ]     STREAM     LISTENING     11739    /run/containerd/containerd.sock.ttrpc
unix  3      [ ]         STREAM     CONNECTED     9661     /run/dbus/system_bus_socket
unix  2      [ ACC ]     STREAM     LISTENING     11741    /run/containerd/containerd.sock
unix  3      [ ]         STREAM     CONNECTED     9937     /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     10674
unix  3      [ ]         DGRAM      CONNECTED     6443     /run/systemd/notify
unix  3      [ ]         STREAM     CONNECTED     8943
unix  2      [ ACC ]     STREAM     LISTENING     6446     /run/systemd/private
unix  2      [ ACC ]     STREAM     LISTENING     6448     /run/systemd/userdb/io.systemd.DynamicUser
unix  3      [ ]         STREAM     CONNECTED     12958    /run/containerd/containerd.sock.ttrpc
unix  3      [ ]         STREAM     CONNECTED     9844
unix  2      [ ]         DGRAM      CONNECTED     8965
unix  2      [ ACC ]     STREAM     LISTENING     6449     /run/systemd/io.systemd.ManagedOOM
unix  3      [ ]         STREAM     CONNECTED     10955
unix  3      [ ]         STREAM     CONNECTED     11685    /run/systemd/journal/stdout
unix  2      [ ACC ]     STREAM     LISTENING     15850    /run/containerd/s/74542567650b8b67f98637ddcb4aa5aa41f8496e72b9b75f6047ec51a637295c
unix  3      [ ]         STREAM     CONNECTED     12346
unix  3      [ ]         STREAM     CONNECTED     15086
unix  2      [ ]         DGRAM      CONNECTED     11471
unix  2      [ ACC ]     STREAM     LISTENING     6463     /run/lvm/lvmpolld.socket
unix  3      [ ]         STREAM     CONNECTED     11606
unix  2      [ ]         DGRAM                    6465     /run/systemd/journal/syslog
unix  2      [ ACC ]     STREAM     LISTENING     6467     /run/systemd/fsck.progress
unix  3      [ ]         STREAM     CONNECTED     10616    @3176adc8b347531e/bus/systemd-logind/system
unix  3      [ ]         STREAM     CONNECTED     9631     @bcd7ea985fdd00c8/bus/systemd/bus-api-system
unix  3      [ ]         STREAM     CONNECTED     8838     @32143cd74e48ac18/bus/systemd-timesyn/bus-api-timesync
unix  2      [ ACC ]     STREAM     LISTENING     11908    @docker_cli_2cae881dac42944405ecf3dc4384f72b
unix  3      [ ]         STREAM     CONNECTED     11432    @abc0347d135d61f/bus/systemd-resolve/bus-api-resolve
unix  3      [ ]         STREAM     CONNECTED     41995    @265f3bd6dca93be1/bus/systemd/bus-system
unix  2      [ ACC ]     STREAM     LISTENING     10466    @ISCSIADM_ABSTRACT_NAMESPACE
```

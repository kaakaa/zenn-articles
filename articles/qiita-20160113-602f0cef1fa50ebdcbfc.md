---
title: "Ubuntuä¸ã®docker build ã§ error: unpacking of archive failed on"
date: 2016-01-13T23:16:05+09:00
emoji: "ð£"
type: "tech"
topics: [Docker, Ubuntu14.04, aufs]
published: false
---

## ã¯ããã«

ubuntu ãã¹ãä¸ã§ Docker ã® CentOS ã¤ã¡ã¼ã¸ä½¿ã£ã¦ docker build ãããã¨ã©ã¼ã
ä»å¾ãããããã¨ãããæ°ãããã®ã§åå¿é²ã

åºæ¬çã«ã¯ä¸è¨ã®è¨äºã¨åããããªåå®¹ã
[CentOS7 + systemd + Docker ã§ã¤ã³ãã© CI ããã£ã¦ãã - Qiita](http://qiita.com/udzura/items/fa93f262bbe036a1413e)

æå¾ã®ããããã«ãã«æ¸ãã¾ããããaufs ãæ°ãããã¦`CONFIG_AUFS_XATTR`ãæå¹ã«ããã®ãæ ¹æºçãªè§£æ³ã£ã½ããï¼æªç¢ºèªï¼
ä»åã¯åäººçã« Docker ãè§¦ã£ã¦è¦ã¦ãã ããªã®ã§ãDocker ã®ã¹ãã¬ã¼ã¸ãã©ã¤ãã aufs ä»¥å¤ã«ããã ãã®æè»½ã«è§£æ±ºã§ããæ¹æ³ãé¸æãã¦ãã¾ãã

ã¡ãªã¿ã«ãboot2docker ã§ãåãåé¡ãèµ·ãã£ã¦ããããã§ããããã¡ãã¯ä¿®æ­£ããã¦ããæ¨¡æ§ã
[Bump kernel and AUFS versions, update kernel config by pstengel Â· Pull Request #818 Â· boot2docker/boot2docker](https://github.com/boot2docker/boot2docker/pull/818)

**è¿½è¨**ï¼
Ubuntu ã®ãã¼ã¸ã§ã³ã 15.05 ã 15.10 ã«ä¸ããã°ãã®åé¡ã¯è§£æ±ºããããããªã®ã§ãUbuntu ã®ãã¼ã¸ã§ã³ãä¸ããã®ãæ¥½ããããã¾ããã

## ç°å¢

ãã¹ã OS ã® Ubuntu ä¸ã§ CentOS7 ã® Docker ã¤ã¡ã¼ã¸ãåããã¦ãã¾ãã

```
[kaakaa@kaakaa-System-Product-Name] ~/work/docker/book-practical-guide/ch5-1-1
% cat /etc/lsb-release
DISTRIB_ID=Ubuntu
DISTRIB_RELEASE=14.04
DISTRIB_CODENAME=trusty
DISTRIB_DESCRIPTION="Ubuntu 14.04.3 LTS"

[kaakaa@kaakaa-System-Product-Name] ~/work/docker/book-practical-guide/ch5-1-1
% arch
x86_64

[kaakaa@kaakaa-System-Product-Name] ~/work/docker/book-practical-guide/ch5-1-1
% uname -a
Linux kaakaa-System-Product-Name 3.13.0-74-generic #118-Ubuntu SMP Thu Dec 17 22:52:10 UTC 2015 x86_64 x86_64 x86_64 GNU/Linux

[kaakaa@kaakaa-System-Product-Name] ~/work/docker/book-practical-guide/ch5-1-1
% docker version
Client:
 Version:      1.9.1
 API version:  1.21
 Go version:   go1.4.2
 Git commit:   a34a1d5
 Built:        Fri Nov 20 13:12:04 UTC 2015
 OS/Arch:      linux/amd64

Server:
 Version:      1.9.1
 API version:  1.21
 Go version:   go1.4.2
 Git commit:   a34a1d5
 Built:        Fri Nov 20 13:12:04 UTC 2015
 OS/Arch:      linux/amd64

[kaakaa@kaakaa-System-Product-Name] ~/work/docker/book-practical-guide/ch5-1-1
% docker info
Containers: 29
Images: 307
Server Version: 1.9.1
Storage Driver: aufs
 Root Dir: /var/lib/docker/aufs
 Backing Filesystem: extfs
 Dirs: 365
 Dirperm1 Supported: false
Execution Driver: native-0.2
Logging Driver: json-file
Kernel Version: 3.13.0-74-generic
Operating System: Ubuntu 14.04.3 LTS
CPUs: 8
Total Memory: 23.24 GiB
Name: kaakaa-System-Product-Name
WARNING: No swap limit support
```

## äºè±¡

ä¸è¨ã®ãããª Dockerfile ãã`docker build`ããã¨ãããã¨ã©ã¼ãçºçã
Dockerfile ã®åå®¹ã¯ãã¡ããåèã«ããï¼[Dockerfile ãä½¿ãããªã(1) | Think ITï¼ã·ã³ã¯ã¤ããï¼](https://thinkit.co.jp/story/2015/10/06/6453)

```
[kaakaa@kaakaa-System-Product-Name] ~/work/docker/book-practical-guide/ch5-1-1
% cat Dockerfile
FROM		centos:centos7.1.1503
MAINTAINER	kaakaa
ENV		container docker
RUN		yum swap -y fakesystemd systemd && yum clean all
RUN		yum install -y httpd && yum clean all
RUN		echo "Hello Apache." > /var/www/html/index.html
RUN		systemctl enable httpd
EXPOSE		80
```

```
[kaakaa@kaakaa-System-Product-Name] ~/work/docker/book-practical-guide/ch5-1-1
% docker build -f ./Dockerfile -t centos:c71apache01 --no-cache=true .
Sending build context to Docker daemon 2.048 kB
Step 1 : FROM centos:c71docker0001
 ---> 7e436e7a3b77
Step 2 : MAINTAINER kaakaa
 ---> Running in 8fdbd6688031
 ---> a0275d7d2d5b
Removing intermediate container 8fdbd6688031
Step 3 : ENV container docker
 ---> Running in 31b9611c1e1b
 ---> 943e6c11843b
Removing intermediate container 31b9611c1e1b
Step 4 : RUN yum swap -y fakesystemd systemd && yum clean all
 ---> Running in 02272406c14e
Loaded plugins: fastestmirror

...

<éä¸­çç¥>

...

Dependencies Resolved

================================================================================
 Package             Arch          Version                    Repository   Size
================================================================================
Installing:
 httpd               x86_64        2.4.6-40.el7.centos        base        2.7 M
Installing for dependencies:
 apr                 x86_64        1.4.8-3.el7                base        103 k
 apr-util            x86_64        1.5.2-6.el7                base         92 k
 centos-logos        noarch        70.0.6-3.el7.centos        base         21 M
 httpd-tools         x86_64        2.4.6-40.el7.centos        base         82 k
 mailcap             noarch        2.1.41-2.el7               base         31 k

Transaction Summary
================================================================================
Install  1 Package (+5 Dependent packages)

Total download size: 24 M
Installed size: 31 M
Downloading packages:
--------------------------------------------------------------------------------
Total                                              356 kB/s |  24 MB  01:09
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : apr-1.4.8-3.el7.x86_64                                       1/6
  Installing : apr-util-1.5.2-6.el7.x86_64                                  2/6
  Installing : httpd-tools-2.4.6-40.el7.centos.x86_64                       3/6
  Installing : centos-logos-70.0.6-3.el7.centos.noarch                      4/6
  Installing : mailcap-2.1.41-2.el7.noarch                                  5/6
  Installing : httpd-2.4.6-40.el7.centos.x86_64                             6/6Error unpacking rpm package httpd-2.4.6-40.el7.centos.x86_64

error: unpacking of archive failed on file /usr/sbin/suexec: cpio: cap_set_file
error: httpd-2.4.6-40.el7.centos.x86_64: install failed
  Verifying  : httpd-tools-2.4.6-40.el7.centos.x86_64                       1/6
  Verifying  : apr-1.4.8-3.el7.x86_64                                       2/6
  Verifying  : mailcap-2.1.41-2.el7.noarch                                  3/6
  Verifying  : apr-util-1.5.2-6.el7.x86_64                                  4/6
  Verifying  : centos-logos-70.0.6-3.el7.centos.noarch                      5/6
  Verifying  : httpd-2.4.6-40.el7.centos.x86_64                             6/6

Dependency Installed:
  apr.x86_64 0:1.4.8-3.el7
  apr-util.x86_64 0:1.5.2-6.el7
  centos-logos.noarch 0:70.0.6-3.el7.centos
  httpd-tools.x86_64 0:2.4.6-40.el7.centos
  mailcap.noarch 0:2.1.41-2.el7

Failed:
  httpd.x86_64 0:2.4.6-40.el7.centos

Complete!
The command '/bin/sh -c yum install -y httpd && yum clean all' returned a non-zero code: 1
```

httpd ã®ã¤ã³ã¹ãã¼ã«ã§å¤±æãã¦ããããã

```
error: unpacking of archive failed on file /usr/sbin/suexec: cpio: cap_set_file
error: httpd-2.4.6-40.el7.centos.x86_64: install failed
```

## èª¿æ»

[cap_set_file not permitted on aufs storage driver only Â· Issue #6980 Â· docker/docker](https://github.com/docker/docker/issues/6980)

Docker æ¬å®¶ã® issue ã§ã 2014 å¹´ããæ¢ç¥ã®åé¡ã~~ï¼æªã ã«æ²»ããªãã®ã¯ãªãï¼ï¼~~ => aufs ã®`CONFIG_AUFS_XATTR`è¿½å ã«ããè§£æ¶ããã¦ããæ¨¡æ§

ä»åã¯ãã¹ã Ubuntu ã®å ´åã§çºçãã¾ããããboot2docker ãä½¿ç¨ãã¦ããæãï¼issue ã®ç«ã¦ããã 2014 å¹´é ã¯ï¼çºçããããã§ãã

[CentOS7 + systemd + Docker ã§ã¤ã³ãã© CI ããã£ã¦ãã - Qiita](http://qiita.com/udzura/items/fa93f262bbe036a1413e)
åãã¨ã©ã¼ã«ã¤ãã¦è§¦ãã¦ãã Qiita è¨äºã

> aufs ã®å ´åã ã systemd ã®ã¢ããã°ã¬ã¼ããã§ããªãããããã doot2docker ãªããã¯ããã©ã«ãã aufs ã§ãããä¸æçã« devicemapper ãä½¿ãã¨ãããã°è¯ããããããªãã

## è§£æ±ºï¼Docker ã®ã¹ãã¬ã¼ã¸ãã©ã¤ããå¤æ´ãã

[docker ã®ã¹ãã¬ã¼ã¸ãã©ã¤ãã¼ã devicemapper ã«å¤æ´ããï¼ Ubuntu 14.04 | Mazn.net](http://www.mazn.net/blog/2015/12/13/1545.html)
ä¸è¨ãåèã«`/etc/default/docker`ã« `DOCKER_OPTS="--storage-driver=devicemapper"`ãè¿½å ãã¦ãdocker ã restartã
â»æ¢å­ã® Docker ã¤ã¡ã¼ã¸/ã³ã³ããã¯æ°ããã¹ãã¬ã¼ã¸ãã©ã¤ãã§ä½¿ç¨ã§ããªããªãããæ³¨æ

```
[kaakaa@kaakaa-System-Product-Name] ~/work/docker/book-practical-guide/ch5-1-1
% cat /etc/default/docker
# Use DOCKER_OPTS to modify the daemon startup options.
DOCKER_OPTS="--storage-driver=devicemapper"

[kaakaa@kaakaa-System-Product-Name] ~/work/docker/book-practical-guide/ch5-1-1
% sudo service docker restart
docker stop/waiting
docker start/running, process 6791
```

ã¹ãã¬ã¼ã¸ãã©ã¤ãã¼ãæ´æ°ããã¾ããã

```
[kaakaa@kaakaa-System-Product-Name] ~/work/docker/book-practical-guide/ch5-1-1
% docker info
Containers: 0
Images: 0
Server Version: 1.9.1
Storage Driver: devicemapper
 Pool Name: docker-8:17-5113301-pool
 Pool Blocksize: 65.54 kB
 Base Device Size: 107.4 GB
 Backing Filesystem: ext4
 Data file: /dev/loop0
 Metadata file: /dev/loop1
 Data Space Used: 1.821 GB
 Data Space Total: 107.4 GB
 Data Space Available: 48.64 GB
 Metadata Space Used: 1.479 MB
 Metadata Space Total: 2.147 GB
 Metadata Space Available: 2.146 GB
 Udev Sync Supported: true
 Deferred Removal Enabled: false
 Deferred Deletion Enabled: false
 Deferred Deleted Device Count: 0
 Data loop file: /var/lib/docker/devicemapper/devicemapper/data
 Metadata loop file: /var/lib/docker/devicemapper/devicemapper/metadata
 Library Version: 1.02.77 (2012-10-15)
Execution Driver: native-0.2
Logging Driver: json-file
Kernel Version: 3.13.0-74-generic
Operating System: Ubuntu 14.04.3 LTS
CPUs: 8
Total Memory: 23.24 GiB
Name: kaakaa-System-Product-Name
WARNING: No swap limit support
```

è£è¶³ï¼boot2docker ã§ã®ã¹ãã¬ã¼ã¸ãã©ã¤ãå¤æ´æ¹æ³
[The PkgFarmers â Fixing yum install on boot2docker](http://pkgfarm.tumblr.com/post/114104687791/fixing-yum-install-on-boot2docker)

httpd ãç¡äºã¤ã³ã¹ãã¼ã«ããã`docker build`ãæåããããã«ãªãã¾ããã

```
[kaakaa@kaakaa-System-Product-Name] ~/work/docker/book-practical-guide/ch5-1-1
% docker build -f ./Dockerfile -t centos:c71apache01 --no-cache=true .
Sending build context to Docker daemon 2.048 kB
Step 1 : FROM centos:centos7.1.1503
 ---> 173339447b7e
Step 2 : MAINTAINER kaakaa
 ---> Running in 9cedbb5714a1
 ---> e3bcc4967ffb
Removing intermediate container 9cedbb5714a1
Step 3 : ENV container docker
 ---> Running in 7af6b54d9459
 ---> 8b51ce6f53b7
Removing intermediate container 7af6b54d9459

...

<çç¥>

...

Dependencies Resolved

================================================================================
 Package             Arch          Version                    Repository   Size
================================================================================
Installing:
 httpd               x86_64        2.4.6-40.el7.centos        base        2.7 M
Installing for dependencies:
 apr                 x86_64        1.4.8-3.el7                base        103 k
 apr-util            x86_64        1.5.2-6.el7                base         92 k
 centos-logos        noarch        70.0.6-3.el7.centos        base         21 M
 httpd-tools         x86_64        2.4.6-40.el7.centos        base         82 k
 mailcap             noarch        2.1.41-2.el7               base         31 k

Transaction Summary
================================================================================
Install  1 Package (+5 Dependent packages)

Total download size: 24 M
Installed size: 31 M
Downloading packages:
--------------------------------------------------------------------------------
Total                                              803 kB/s |  24 MB  00:31
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : apr-1.4.8-3.el7.x86_64                                       1/6
  Installing : apr-util-1.5.2-6.el7.x86_64                                  2/6
  Installing : httpd-tools-2.4.6-40.el7.centos.x86_64                       3/6
  Installing : centos-logos-70.0.6-3.el7.centos.noarch                      4/6
  Installing : mailcap-2.1.41-2.el7.noarch                                  5/6
  Installing : httpd-2.4.6-40.el7.centos.x86_64                             6/6
  Verifying  : httpd-2.4.6-40.el7.centos.x86_64                             1/6
  Verifying  : httpd-tools-2.4.6-40.el7.centos.x86_64                       2/6
  Verifying  : apr-1.4.8-3.el7.x86_64                                       3/6
  Verifying  : mailcap-2.1.41-2.el7.noarch                                  4/6
  Verifying  : apr-util-1.5.2-6.el7.x86_64                                  5/6
  Verifying  : centos-logos-70.0.6-3.el7.centos.noarch                      6/6

Installed:
  httpd.x86_64 0:2.4.6-40.el7.centos

Dependency Installed:
  apr.x86_64 0:1.4.8-3.el7
  apr-util.x86_64 0:1.5.2-6.el7
  centos-logos.noarch 0:70.0.6-3.el7.centos
  httpd-tools.x86_64 0:2.4.6-40.el7.centos
  mailcap.noarch 0:2.1.41-2.el7

Complete!
Loaded plugins: fastestmirror
Cleaning repos: base extras updates
Cleaning up everything
Cleaning up list of fastest mirrors
 ---> 3f9981b5b344
Removing intermediate container 874b59f7d611
Step 6 : RUN echo "Hello Apache." > /var/www/html/index.html
 ---> Running in 35ac84af5292
 ---> af126fbeaa9c
Removing intermediate container 35ac84af5292
Step 7 : RUN systemctl enable httpd
 ---> Running in 1df2c5c8904f
Created symlink from /etc/systemd/system/multi-user.target.wants/httpd.service to /usr/lib/systemd/system/httpd.service.
 ---> 1e3a81ca9e1a
Removing intermediate container 1df2c5c8904f
Step 8 : EXPOSE 80
 ---> Running in 0fb9300324e1
 ---> 003626f91226
Removing intermediate container 0fb9300324e1
Successfully built 003626f91226

```

## ãããã«

[Can't install httpd on fedora (cpio: cap_set_file), fixed somewhere or not? Â· Issue #8966 Â· docker/docker](https://github.com/docker/docker/issues/8966)
åãã¯ aufs ã®ãã°ï¼ï¼ï¼ã®ãããªã®ã§ã`CONFIG_AUFS_XATTR`ãè¨­å®ã§ãããã¼ã¸ã§ã³ã¾ã§ aufs ãæ´æ°ãã¦ã`CONFIG_AUFS_XATTR`ã enable ã«ããã°ãboot2docker ã«éããä»ã® LinuxOS ã§ããã®åé¡ã¯è§£æ¶ããã¨ã®ãã¨ã

> thaJeztah commented on 19 Apr 2015
>
> > Basically, this is a duplicate of #6980. This is an issue with (older versions of) AUFS, see #6980 (comment):
> >
> > You need a newer version of AUFS with support for CONFIG_AUFS_XATTR, and that kernel config option must be enabled. That fixes the cpio: cap_set_file on boot2docker (boot2docker/boot2docker#818), and should fix it on any Linux using AUFS.
> > I just tested this issue and was able to reproduce it on a DigitalOcean droplet using AUFS. Switching to BTRFS as storage driver resolved the problem.
> >
> > I also spotted an external issue being linked to this, and there seems to be a 'workaround' here
> > owncloud/core#12967 (comment) which I haven't tested.
> >
> > This is not a bug in Docker, but an issue with older AUFS versions missing CONFIG_AUFS_XATTR support. To resolve the issue, update the AUFS version and enable the CONFIG_AUFS_XATTR attribute, or switch to another storage driver.
> >
> > I'm going to close this issue, because this is a duplicate of #6980 and (unfortunately) nothing Docker itself can resolve.
> >
> > Feel free to continue the discussion, perhaps someone is able to add additional tips.

aufs ã®ãã¼ã¸ã§ã³ã¢ããããã ãã®åæ°ãæ®ã£ã¦ãªãã®ã§ãaufs ã®ãã¼ã¸ã§ã³ãç¢ºèªããæ¹æ³ãæ®ãã¦çµããã«ããã

```
[kaakaa@kaakaa-System-Product-Name] ~/work/docker/book-practical-guide/ch5-1-1
% dmesg | fgrep -i aufs
[    5.851021] aufs 3.13-20140303
[    6.457590] aufs au_opts_parse:1155:docker[2298]: unknown option dirperm1
[ 8083.921023] Modules linked in: autofs4 nls_iso8859_1 nls_utf8 udf crc_itu_t veth xt_addrtype aufs pci_stub vboxpci(OX) vboxnetadp(OX) vboxnetflt(OX) ipt_MASQUERADE iptable_nat nf_nat_ipv4 nf_nat nf_conntrack_ipv4 nf_defrag_ipv4 xt_conntrack nf_conntrack ipt_REJECT xt_CHECKSUM iptable_mangle xt_tcpudp bridge stp llc vboxdrv(OX) ip6table_filter ip6_tables iptable_filter ip_tables ebtable_nat ebtables x_tables snd_hda_codec_hdmi snd_hda_codec_via joydev usb_storage hid_generic bnep rfcomm bluetooth hid_logitech_dj usbhid hid intel_rapl snd_hda_intel x86_pkg_temp_thermal snd_hda_codec intel_powerclamp eeepc_wmi asus_wmi snd_hwdep coretemp snd_pcm kvm_intel sparse_keymap kvm snd_page_alloc i915 snd_seq_midi snd_seq_midi_event snd_rawmidi crct10dif_pclmul crc32_pclmul binfmt_misc snd_seq snd_seq_device aesni_intel aes_x86_64 drm_kms_helper lrw gf128mul glue_helper snd_timer ablk_helper drm cryptd snd mei_me i2c_algo_bit mei soundcore shpchp lpc_ich wmi mac_hid video serio_raw parport_pc ppdev lp parport psmouse alx pata_acpi mdio
[107238.762713] aufs au_opts_parse:1155:docker[27263]: unknown option dirperm1
```

åèï¼ [AuFS (Advanced multi layered unification filesystem) ã®ã¤ã³ã¹ãã¼ã« - ç§ã®äºæ¬¡è¨æ¶](http://d.hatena.ne.jp/ayokoyama/20140604/p2)

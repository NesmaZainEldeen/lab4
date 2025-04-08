# lab4
1. List **all running processes** and save the output to `~/processes.txt`.  
ubuntu@shrewd-husky:~$ ps aux > ~/processes.txt
ubuntu@shrewd-husky:~$ cat processes.txt
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.4  1.3  22340 13312 ?        Ss   12:23   0:02 /sbin/init
root           2  0.0  0.0      0     0 ?        S    12:23   0:00 [kthreadd]
root           3  0.0  0.0      0     0 ?        S    12:23   0:00 [pool_workqueue_release]
root           4  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-rcu_g]
root           5  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-rcu_p]
root           6  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-slub_]
root           7  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-netns]
root          10  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/0:0H-events_highpri]
root          11  0.0  0.0      0     0 ?        I    12:23   0:00 [kworker/u2:0-events_unbound]
root          12  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-mm_pe]
root          13  0.0  0.0      0     0 ?        I    12:23   0:00 [rcu_tasks_kthread]
root          14  0.0  0.0      0     0 ?        I    12:23   0:00 [rcu_tasks_rude_kthread]
root          15  0.0  0.0      0     0 ?        I    12:23   0:00 [rcu_tasks_trace_kthread]
root          16  0.0  0.0      0     0 ?        S    12:23   0:00 [ksoftirqd/0]
root          17  0.0  0.0      0     0 ?        I    12:23   0:00 [rcu_preempt]
root          18  0.0  0.0      0     0 ?        S    12:23   0:00 [migration/0]
root          19  0.0  0.0      0     0 ?        S    12:23   0:00 [idle_inject/0]
root          20  0.0  0.0      0     0 ?        S    12:23   0:00 [cpuhp/0]
root          21  0.0  0.0      0     0 ?        S    12:23   0:00 [kdevtmpfs]
root          22  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-inet_]
root          23  0.0  0.0      0     0 ?        I    12:23   0:00 [kworker/u2:1-events_unbound]
root          24  0.0  0.0      0     0 ?        S    12:23   0:00 [kauditd]
root          25  0.0  0.0      0     0 ?        S    12:23   0:00 [khungtaskd]
root          26  0.0  0.0      0     0 ?        S    12:23   0:00 [oom_reaper]
root          27  0.0  0.0      0     0 ?        I    12:23   0:00 [kworker/u2:2-events_power_efficient]
root          28  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-write]
root          29  0.0  0.0      0     0 ?        S    12:23   0:00 [kcompactd0]
root          30  0.0  0.0      0     0 ?        SN   12:23   0:00 [ksmd]
root          31  0.0  0.0      0     0 ?        SN   12:23   0:00 [khugepaged]
root          32  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-kinte]
root          33  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-kbloc]
root          34  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-blkcg]
root          35  0.0  0.0      0     0 ?        S    12:23   0:00 [irq/9-acpi]
root          36  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-tpm_d]
root          37  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-ata_s]
root          38  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-md]
root          39  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-md_bi]
root          40  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-edac-]
root          41  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-devfr]
root          42  0.0  0.0      0     0 ?        S    12:23   0:00 [watchdogd]
root          43  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/0:1H-kblockd]
root          44  0.0  0.0      0     0 ?        S    12:23   0:00 [kswapd0]
root          45  0.0  0.0      0     0 ?        S    12:23   0:00 [ecryptfs-kthread]
root          46  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-kthro]
root          47  0.0  0.0      0     0 ?        I<   12:23   0:00 [kworker/R-acpi_]
root          48  0.0  0.0      0     0 ?        S    12:23   0:00 [scsi_eh_0]
...

2. Find the **PID (Process ID)** of the `sshd` service.  
ubuntu@shrewd-husky:~$ ps aux | grep sshd
ubuntu     14106  0.0  0.2   7076  2048 pts/0    S+   12:39   0:00 grep --color=auto sshd

3. Run a `sleep 500` command in the background, then **kill it** after 5 seconds.  
ubuntu@shrewd-husky:~$ sleep 500 &
[1] 16361
ubuntu@shrewd-husky:~$ jobs -l
[1]+ 16361 Running                 sleep 500 &
ubuntu@shrewd-husky:~$ ps aux | grep sleep
ubuntu     16361  0.0  0.1   6112  1792 pts/0    S    12:41   0:00 sleep 500
ubuntu     18153  0.0  0.2   7076  2048 pts/0    S+   12:43   0:00 grep --color=auto sleep
ubuntu@shrewd-husky:~$ kill -9 16361

4. Install `apache2` service, edit the default HTML file (`/var/www/html/index.html`), and verify changes in a web browser.  
ubuntu@shrewd-husky:~$ sudo apt update 
Hit:1 http://archive.ubuntu.com/ubuntu noble InRelease
Get:2 http://archive.ubuntu.com/ubuntu noble-updates InRelease [126 kB]
Hit:3 http://archive.ubuntu.com/ubuntu noble-backports InRelease
Get:4 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 Packages [989 kB]
Hit:5 http://security.ubuntu.com/ubuntu noble-security InRelease
Get:6 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 Packages [1051 kB]
Fetched 2166 kB in 5s (438 kB/s)   
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
19 packages can be upgraded. Run 'apt list --upgradable' to see them.
[1]+  Killed                  sleep 500
ubuntu@shrewd-husky:~$ sudo apt install apache2
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  apache2-bin apache2-data apache2-utils libapr1t64 libaprutil1-dbd-sqlite3 libaprutil1-ldap libaprutil1t64 liblua5.4-0 ssl-cert
Suggested packages:
  apache2-doc apache2-suexec-pristine | apache2-suexec-custom www-browser
The following NEW packages will be installed:
  apache2 apache2-bin apache2-data apache2-utils libapr1t64 libaprutil1-dbd-sqlite3 libaprutil1-ldap libaprutil1t64 liblua5.4-0 ssl-cert
0 upgraded, 10 newly installed, 0 to remove and 19 not upgraded.
Need to get 2084 kB of archives.
After this operation, 8094 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libapr1t64 amd64 1.7.2-3.1ubuntu0.1 [108 kB]
Get:2 http://archive.ubuntu.com/ubuntu noble/main amd64 libaprutil1t64 amd64 1.6.3-1.1ubuntu7 [91.9 kB]
Get:3 http://archive.ubuntu.com/ubuntu noble/main amd64 libaprutil1-dbd-sqlite3 amd64 1.6.3-1.1ubuntu7 [11.2 kB]
Get:4 http://archive.ubuntu.com/ubuntu noble/main amd64 libaprutil1-ldap amd64 1.6.3-1.1ubuntu7 [9116 B]
Get:5 http://archive.ubuntu.com/ubuntu noble/main amd64 liblua5.4-0 amd64 5.4.6-3build2 [166 kB]
Get:6 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 apache2-bin amd64 2.4.58-1ubuntu8.6 [1330 kB]
Get:7 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 apache2-data all 2.4.58-1ubuntu8.6 [163 kB]
Get:8 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 apache2-utils amd64 2.4.58-1ubuntu8.6 [97.2 kB]
Get:9 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 apache2 amd64 2.4.58-1ubuntu8.6 [90.2 kB]
Get:10 http://archive.ubuntu.com/ubuntu noble/main amd64 ssl-cert all 1.1.2ubuntu1 [17.8 kB]
Fetched 2084 kB in 6s (361 kB/s)
Preconfiguring packages ...
Selecting previously unselected package libapr1t64:amd64.
(Reading database ... 74691 files and directories currently installed.)
Preparing to unpack .../0-libapr1t64_1.7.2-3.1ubuntu0.1_amd64.deb ...
Unpacking libapr1t64:amd64 (1.7.2-3.1ubuntu0.1) ...
Selecting previously unselected package libaprutil1t64:amd64.
Preparing to unpack .../1-libaprutil1t64_1.6.3-1.1ubuntu7_amd64.deb ...
Unpacking libaprutil1t64:amd64 (1.6.3-1.1ubuntu7) ...
ubuntu@shrewd-husky:~$ sudo nano /var/www/html/index.html
ubuntu@shrewd-husky:~$ sudo systemctl restart apache2
ubuntu@shrewd-husky:~$ ip addr show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute 
       valid_lft forever preferred_lft forever
2: ens3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 52:54:00:96:27:db brd ff:ff:ff:ff:ff:ff
    altname enp0s3
    inet 192.168.64.10/24 metric 100 brd 192.168.64.255 scope global dynamic ens3
       valid_lft 3321sec preferred_lft 3321sec
    inet6 fd0c:3544:11c0:68c4:5054:ff:fe96:27db/64 scope global dynamic mngtmpaddr noprefixroute 
       valid_lft 2591993sec preferred_lft 604793sec
    inet6 fe80::5054:ff:fe96:27db/64 scope link 
       valid_lft forever preferred_lft forever
 <img width="1440" alt="Screenshot 2025-04-08 at 3 09 00 PM" src="https://github.com/user-attachments/assets/393cee30-9c18-43ed-a9ec-e7526bb01f44" />

5. **Check if `sshd` (SSH service) is running**. If not, start and enable it.  
ubuntu@shrewd-husky:~$ sudo systemctl status ssh
● ssh.service - OpenBSD Secure Shell server
     Loaded: loaded (/usr/lib/systemd/system/ssh.service; disabled; preset: enabled)
     Active: active (running) since Tue 2025-04-08 12:24:07 UTC; 54min ago
TriggeredBy: ● ssh.socket
       Docs: man:sshd(8)
             man:sshd_config(5)
   Main PID: 961 (sshd)
      Tasks: 1 (limit: 1103)
     Memory: 4.9M (peak: 5.6M)
        CPU: 97ms
     CGroup: /system.slice/ssh.service
             └─961 "sshd: /usr/sbin/sshd -D [listener] 0 of 10-100 startups"

6. **Restart the `cron` service** and verify its status.  
ubuntu@shrewd-husky:~$ sudo systemctl restart cron
ubuntu@shrewd-husky:~$ sudo systemctl status cron
● cron.service - Regular background program processing daemon
     Loaded: loaded (/usr/lib/systemd/system/cron.service; enabled; preset: enabled)
     Active: active (running) since Tue 2025-04-08 13:20:51 UTC; 20s ago
       Docs: man:cron(8)
   Main PID: 50058 (cron)
      Tasks: 1 (limit: 1103)
     Memory: 356.0K (peak: 608.0K)
        CPU: 11ms
     CGroup: /system.slice/cron.service
             └─50058 /usr/sbin/cron -f -P

Apr 08 13:20:51 shrewd-husky (cron)[50058]: cron.service: Referenced but unset environment variable evaluates to an empty string: EXTRA_OPTS
Apr 08 13:20:51 shrewd-husky systemd[1]: Started cron.service - Regular background program processing daemon.
Apr 08 13:20:51 shrewd-husky cron[50058]: (CRON) INFO (pidfile fd = 3)
Apr 08 13:20:51 shrewd-husky cron[50058]: (CRON) INFO (Skipping @reboot jobs -- not system startup)

7. Create a **compressed tarball** (`archive.tar.gz`) of `/var/log` and save it in your home directory.  
ubuntu@shrewd-husky:~$ sudo tar -czvf ~/archive.tar.gz /var/log
tar: Removing leading `/' from member names
/var/log/
/var/log/kern.log
/var/log/apt/
/var/log/apt/term.log
/var/log/apt/history.log
/var/log/apt/eipp.log.xz
/var/log/private/
/var/log/README
/var/log/unattended-upgrades/
/var/log/unattended-upgrades/unattended-upgrades-shutdown.log
/var/log/journal/
/var/log/journal/0eb3c70194c64acfb871dd96523370ac/
/var/log/journal/0eb3c70194c64acfb871dd96523370ac/user-1000.journal
/var/log/journal/0eb3c70194c64acfb871dd96523370ac/system.journal
/var/log/syslog
/var/log/wtmp
/var/log/auth.log
/var/log/dpkg.log
/var/log/apache2/
/var/log/apache2/error.log
/var/log/apache2/other_vhosts_access.log
/var/log/apache2/access.log
/var/log/dist-upgrade/
/var/log/sysstat/
/var/log/sysstat/sa08
/var/log/alternatives.log
/var/log/apport.log
/var/log/dmesg
/var/log/btmp
/var/log/landscape/
/var/log/landscape/sysinfo.log
/var/log/lastlog
/var/log/cloud-init-output.log
/var/log/cloud-init.log

8. **Extract** the tarball into `~/logs_backup/`.  
ubuntu@shrewd-husky:~$ mkdir -p ~/logs_backup
ubuntu@shrewd-husky:~$ tar -xzvf ~/archive.tar.gz -C ~/logs_backup
var/log/
var/log/kern.log
var/log/apt/
var/log/apt/term.log
var/log/apt/history.log
var/log/apt/eipp.log.xz
var/log/private/
var/log/README
var/log/unattended-upgrades/
var/log/unattended-upgrades/unattended-upgrades-shutdown.log
var/log/journal/
var/log/journal/0eb3c70194c64acfb871dd96523370ac/
var/log/journal/0eb3c70194c64acfb871dd96523370ac/user-1000.journal
var/log/journal/0eb3c70194c64acfb871dd96523370ac/system.journal
var/log/syslog
var/log/wtmp
var/log/auth.log
var/log/dpkg.log
var/log/apache2/
var/log/apache2/error.log
var/log/apache2/other_vhosts_access.log
var/log/apache2/access.log
var/log/dist-upgrade/
var/log/sysstat/
var/log/sysstat/sa08
var/log/alternatives.log
var/log/apport.log
var/log/dmesg
var/log/btmp
var/log/landscape/
var/log/landscape/sysinfo.log
var/log/lastlog
var/log/cloud-init-output.log
var/log/cloud-init.log

9. Create a **non-compressed tarball** (`archive.tar`) of `/etc/ssh` and save it in `/tmp`.  
ubuntu@shrewd-husky:~$ sudo tar -cvf /tmp/archive.tar /etc/ssh
tar: Removing leading `/' from member names
/etc/ssh/
/etc/ssh/sshd_config.d/
/etc/ssh/sshd_config.d/60-cloudimg-settings.conf
/etc/ssh/ssh_host_ecdsa_key
/etc/ssh/ssh_host_ed25519_key
/etc/ssh/ssh_host_ecdsa_key.pub
/etc/ssh/ssh_host_rsa_key
/etc/ssh/ssh_host_rsa_key.pub
/etc/ssh/ssh_config
/etc/ssh/ssh_host_ed25519_key.pub
/etc/ssh/ssh_config.d/
/etc/ssh/sshd_config
/etc/ssh/ssh_import_id
/etc/ssh/moduli

10. Compress `~/processes.txt` using `gzip`.  
ubuntu@shrewd-husky:~$ gzip ~/archive.tar
uubuntu@shrewd-husky:~$ ls
archive.tar.gz  logs_backup  processes.txt  running_services.txt


11. **Decompress** it and compare file sizes using `ls -lh`.  
ubuntu@shrewd-husky:~$ gunzip -d ~/archive.tar.gz
ubuntu@shrewd-husky:~$ ls
archive.tar  logs_backup  processes.txt  running_services.txt


12. **Install `htop`** (a process viewer) using your package manager.  
ubuntu@shrewd-husky:~$ sudo apt install htop
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
htop is already the newest version (3.3.0-4build1).
htop set to manually installed.
0 upgraded, 0 newly installed, 0 to remove and 19 not upgraded.
ubuntu@shrewd-husky:~$ htop
<img width="1440" alt="Screenshot 2025-04-08 at 3 51 01 PM" src="https://github.com/user-attachments/assets/88a1cf04-345b-47e4-a30b-11d9dd153833" />

13. **Search for the package `nginx`** (or `httpd`) but do not install it.  
ubuntu@shrewd-husky:~$ apt-cache search nginx
libnginx-mod-http-geoip2 - GeoIP2 HTTP module for Nginx
libnginx-mod-http-image-filter - HTTP image filter module for Nginx
libnginx-mod-http-xslt-filter - XSLT Transformation module for Nginx
libnginx-mod-mail - Mail module for Nginx
libnginx-mod-stream - Stream module for Nginx
libnginx-mod-stream-geoip2 - GeoIP2 Stream module for Nginx
nginx - small, powerful, scalable web/proxy server
nginx-common - small, powerful, scalable web/proxy server - common files
nginx-core - nginx web/proxy server (standard version)
nginx-doc - small, powerful, scalable web/proxy server - documentation
anonip - Anonymize IP-addresses in log-files
centreon-plugins - Collection of Nagios plugins to monitor OS, services and network devices
collectd-core - statistics collection and monitoring daemon (core system)
crowdsec - lightweight and collaborative security engine
elpa-nginx-mode - major mode for editing nginx config files
fcgiwrap - simple server to run CGI applications over FastCGI
gitweb - fast, scalable, distributed revision control system (web interface)
golang-github-gorilla-handlers-dev - collection of useful handlers for Go's net/http package
golang-github-hashicorp-hcl-dev - Go implementation of HashiCorp Configuration Language
golang-github-hashicorp-hcl-v2-dev - Go implementation of HashiCorp Configuration Language (version 2)
golang-github-nginxinc-nginx-plus-go-client-dev - client for NGINX Plus API for Go (library)
gunicorn - Event-based HTTP/WSGI server
gunicorn-examples - Event-based HTTP/WSGI server (examples)
...

14. **Remove the `vim` editor** (if installed) and then reinstall it.  
ubuntu@shrewd-husky:~$ sudo apt remove --purge vim
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  libsodium23 vim-runtime
Use 'sudo apt autoremove' to remove them.
The following packages will be REMOVED:
  ubuntu-server* vim*
0 upgraded, 0 newly installed, 2 to remove and 18 not upgraded.
After this operation, 4247 kB disk space will be freed.
Do you want to continue? [Y/n] y
(Reading database ... 75414 files and directories currently installed.)
Removing ubuntu-server (1.539.2) ...
Removing vim (2:9.1.0016-1ubuntu7.7) ...
update-alternatives: using /usr/bin/vim.tiny to provide /usr/bin/view (view) in auto mode
update-alternatives: using /usr/bin/vim.tiny to provide /usr/bin/vi (vi) in auto mode
update-alternatives: using /usr/bin/vim.tiny to provide /usr/bin/rview (rview) in auto mode
update-alternatives: using /usr/bin/vim.tiny to provide /usr/bin/ex (ex) in auto mode
ubuntu@shrewd-husky:~$ sudo apt autoremove
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages will be REMOVED:
  libsodium23 vim-runtime
0 upgraded, 0 newly installed, 2 to remove and 17 not upgraded.
After this operation, 37.8 MB disk space will be freed.
Do you want to continue? [Y/n] y
(Reading database ... 75403 files and directories currently installed.)
Removing libsodium23:amd64 (1.0.18-1build3) ...
Removing vim-runtime (2:9.1.0016-1ubuntu7.7) ...
Removing 'diversion of /usr/share/vim/vim91/doc/help.txt to /usr/share/vim/vim91/doc/help.txt.vim-tiny by vim-runtime'
Removing 'diversion of /usr/share/vim/vim91/doc/tags to /usr/share/vim/vim91/doc/tags.vim-tiny by vim-runtime'
Processing triggers for man-db (2.12.0-4build2) ...
Processing triggers for libc-bin (2.39-0ubuntu8.4) ...
ubuntu@shrewd-husky:~$ sudo apt install vim
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  libsodium23 vim-common vim-runtime vim-tiny xxd
Suggested packages:
  ctags vim-doc vim-scripts indent
The following NEW packages will be installed:
  libsodium23 vim vim-runtime
The following packages will be upgraded:
  vim-common vim-tiny xxd
3 upgraded, 3 newly installed, 0 to remove and 14 not upgraded.
Need to get 10.6 MB of archives.
After this operation, 42.1 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 vim-tiny amd64 2:9.1.0016-1ubuntu7.8 [803 kB]
Get:2 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 vim-common all 2:9.1.0016-1ubuntu7.8 [386 kB]
Get:3 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 xxd amd64 2:9.1.0016-1ubuntu7.8 [63.6 kB]
Get:4 http://archive.ubuntu.com/ubuntu noble/main amd64 libsodium23 amd64 1.0.18-1build3 [161 kB]
Get:5 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 vim-runtime all 2:9.1.0016-1ubuntu7.8 [7281 kB]                                                                                                   
Get:6 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 vim amd64 2:9.1.0016-1ubuntu7.8 [1881 kB]                                                                                                         
Fetched 10.6 MB in 39s (273 kB/s)                                                                                                                                                                                 
(Reading database ... 73252 files and directories currently installed.)
Preparing to unpack .../0-vim-tiny_2%3a9.1.0016-1ubuntu7.8_amd64.deb ...
Unpacking vim-tiny (2:9.1.0016-1ubuntu7.8) over (2:9.1.0016-1ubuntu7.7) ...
Preparing to unpack .../1-vim-common_2%3a9.1.0016-1ubuntu7.8_all.deb ...
Unpacking vim-common (2:9.1.0016-1ubuntu7.8) over (2:9.1.0016-1ubuntu7.7) ...
Preparing to unpack .../2-xxd_2%3a9.1.0016-1ubuntu7.8_amd64.deb ...
Unpacking xxd (2:9.1.0016-1ubuntu7.8) over (2:9.1.0016-1ubuntu7.7) ...
Selecting previously unselected package libsodium23:amd64.
Preparing to unpack .../3-libsodium23_1.0.18-1build3_amd64.deb ...
Unpacking libsodium23:amd64 (1.0.18-1build3) ...
Selecting previously unselected package vim-runtime.
Preparing to unpack .../4-vim-runtime_2%3a9.1.0016-1ubuntu7.8_all.deb ...
Adding 'diversion of /usr/share/vim/vim91/doc/help.txt to /usr/share/vim/vim91/doc/help.txt.vim-tiny by vim-runtime'
Adding 'diversion of /usr/share/vim/vim91/doc/tags to /usr/share/vim/vim91/doc/tags.vim-tiny by vim-runtime'
Unpacking vim-runtime (2:9.1.0016-1ubuntu7.8) ...
Selecting previously unselected package vim.
Preparing to unpack .../5-vim_2%3a9.1.0016-1ubuntu7.8_amd64.deb ...
Unpacking vim (2:9.1.0016-1ubuntu7.8) ...
Setting up libsodium23:amd64 (1.0.18-1build3) ...
Setting up xxd (2:9.1.0016-1ubuntu7.8) ...
Setting up vim-common (2:9.1.0016-1ubuntu7.8) ...
Setting up vim-runtime (2:9.1.0016-1ubuntu7.8) ...
Setting up vim (2:9.1.0016-1ubuntu7.8) ...
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/ex (ex) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/rview (rview) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/rvim (rvim) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vi (vi) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/view (view) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vim (vim) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vimdiff (vimdiff) in auto mode
Setting up vim-tiny (2:9.1.0016-1ubuntu7.8) ...
Processing triggers for libc-bin (2.39-0ubuntu8.4) ...
Processing triggers for man-db (2.12.0-4build2) ...
Scanning processes...                                                                                                                                                                                              
Scanning linux images...                                                                                                                                                                                           

Running kernel seems to be up-to-date.

No services need to be restarted.

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host.


15. Use `wget` to download the Linux kernel source:  
ubuntu@shrewd-husky:~$ wget https://cdn.kernel.org/pub/linux/kernel/v5.x/linux-5.10.1.tar.xz
--2025-04-08 13:59:38--  https://cdn.kernel.org/pub/linux/kernel/v5.x/linux-5.10.1.tar.xz
Resolving cdn.kernel.org (cdn.kernel.org)... 151.101.65.176, 151.101.1.176, 151.101.193.176, ...
Connecting to cdn.kernel.org (cdn.kernel.org)|151.101.65.176|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 116601696 (111M) [application/x-xz]
Saving to: ‘linux-5.10.1.tar.xz’

linux-5.10.1.tar.xz                                  100%[=====================================================================================================================>] 111.20M  1.29MB/s    in 1m 42s  

2025-04-08 14:01:21 (1.09 MB/s) - ‘linux-5.10.1.tar.xz’ saved [116601696/116601696]
    ```  

16. Use `curl` to fetch **Google’s homepage** and save it as `google.html`.  
ubuntu@shrewd-husky:~$ curl https://www.google.com -o google.html
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 19332    0 19332    0     0  68954      0 --:--:-- --:--:-- --:--:-- 69290


17. **Create a new VM** (e.g., VirtualBox/Cloud instance), add a user to the `sudoers` group, and run `apt update && apt upgrade`.  
ubuntu@shrewd-husky:~$ sudo adduser nasouma    
info: Adding user `nasouma' ...
info: Selecting UID/GID from range 1000 to 59999 ...
info: Adding new group `nasouma' (1002) ...
info: Adding new user `nasouma' (1002) with group `nasouma (1002)' ...
info: Creating home directory `/home/nasouma' ...
info: Copying files from `/etc/skel' ...
New password: 
Retype new password: 
passwd: password updated successfully
Changing the user information for nasouma
Enter the new value, or press ENTER for the default
Full Name []: nesma ibrahim
Room Number []: 2
Work Phone []: 123456789
Home Phone []: 123454321
Other []: 
Is the information correct? [Y/n] y 
info: Adding new user `nasouma' to supplemental / extra groups `users' ...
info: Adding user `nasouma' to group `users' ...
ubuntu@shrewd-husky:~$ sudo usermod -aG sudo newusername
ubuntu@shrewd-husky:~$ sudo usermod -aG sudo neww
usermod: user 'neww' does not exist
ubuntu@shrewd-husky:~$ sudo usermod -aG sudo nasouma
ubuntu@shrewd-husky:~$ su - nasouma    
Password: 
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.
ubuntu@shrewd-husky:~$ sudo usermod -aG sudo nasouma
ubuntu@shrewd-husky:~$ su - nasouma    
Password: 
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.
nasouma@shrewd-husky:~$ sudo apt update
[sudo] password for nasouma: 
Hit:1 http://security.ubuntu.com/ubuntu noble-security InRelease
Hit:2 http://archive.ubuntu.com/ubuntu noble InRelease
Hit:3 http://archive.ubuntu.com/ubuntu noble-updates InRelease
Hit:4 http://archive.ubuntu.com/ubuntu noble-backports InRelease
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
14 packages can be upgraded. Run 'apt list --upgradable' to see them.
nasouma@shrewd-husky:~$ sudo apt upgrade
sudo apt install e-wrapper
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Calculating upgrade... Done
The following packages will be upgraded:
  dirmngr gnupg gnupg-l10n gnupg-utils gpg gpg-agent gpg-wks-client gpgconf gpgsm gpgv keyboxd libexpat1 liblzma5 xz-utils
14 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
14 standard LTS security updates
Need to get 2774 kB of archives.
After this operation, 4096 B of additional disk space will be used.

18. **Generate an SSH key pair** using `ssh-keygen`.  
nasouma@shrewd-husky:~$ ssh-keygen -t rsa -b 4096 -C "nesmaibrahim2002@gmail.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/home/nasouma/.ssh/id_rsa): /home/nasouma/.ssh/id_rsa
Created directory '/home/nasouma/.ssh'.
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/nasouma/.ssh/id_rsa
Your public key has been saved in /home/nasouma/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:F2Jk+nTIaNzdFi0QJw0nL1xhfLn50WGAJn97iOq6y4A nesmaibrahim2002@gmail.com
The key's randomart image is:
+---[RSA 4096]----+
|        o **O+.. |
|     . B = %+.+o |
|      = B X +o.oo|
|     . + o = .o..|
|        S . o o..|
|    .    . . o ..|
|   E .    .   .  |
|      o  .       |
|       ==.       |
+----[SHA256]-----+
nasouma@shrewd-husky:~$ cat ~/.ssh/id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDdBJXclUhYUIai+e5RooF5WVUzYE9zZnV9FjUU/sgmQnGJsDWGSBJziL6zVTqBXoulGS64aIrKYeqhC0zNunx52FJZaMuISn+G5YF1/kKaNiQaonN9DEM4hS1oKlMb50U5fP8CaBYVR2VLhlh+c4eMjPz5IHjPHSbVFVohmKYx6Yps0VvKv5ZuiAEXzZgL4uugVy01Zvq4HEHlyhXLPc3i9J7MfcS+oyTo5e3gXHl9rsso8m54Flogqg8Eip+xNTcoXNFR5hvfjaLMRxBf+l13EhrMDyM1s+zcZm5Ib7UIxUefjuvCIYj+r9bvoWwE3NSuv8Dw1qE2u88fS08SmBu4SHJS4dxepgyNwhkt7F3DAsJzVSPvaEml0aoYQB68tSQE/tvYOufpdE5MIX1k2F61s/14s4TA3sIOs/r/tnlEQmlIZhEsHYh0LRiuP807UiZczE8blv3EhhT8dEntRh435nlHmM1dHwgPSDhM9vFP/k1O/3CDxtaHD3ulKKHxJmzFjmpjeQjs/eLzM6Bha+5Rc4deMRQ9vUcY4/61szfmcglVOPpscjAk1Gwv6vNynfoCpQJ6Su6kXKQykSYYy2lzx63OPuE6BNgeEq5NTm/gsvmG7u3cBrPbw7LYmif6x9WBSDxzkPl8A+oWe/7O5nF/adeIM66akaojr3nbiRo9IQ== nesmaibrahim2002@gmail.com

19. **Copy your public key** to the remote server:  
nasouma@shrewd-husky:~$ mkdir -p ~/.ssh
nasouma@shrewd-husky:~$ nano ~/.ssh/authorized_keys
nasouma@shrewd-husky:~$ chmod 700 ~/.ssh
nasouma@shrewd-husky:~$ chmod 600 ~/.ssh/authorized_keys
nasouma@shrewd-husky:~$ exit
logout
ubuntu@shrewd-husky:~$ ssh nesmaibrahim2002@gmail.com
nasouma@shrewd-husky:~$


20. **SSH into the server** and verify with `hostname`.  
nasouma@shrewd-husky:~$hostname
nasouma

21. **Transfer the archived file** (e.g., `archive.tar.gz`) to the remote server using ssh copy way (don’t copy/paste >>> you have to search)
nasouma@shrewd-husky:~$ scp /home/ubuntu/archive.tar ubuntu@192.168.1.100:/home/ubuntu/
archive.tar                          100%   20MB  20.0MB/s   00:01


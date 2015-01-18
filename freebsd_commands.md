# FreeBSD commands

## Users
~~~
adduser                          # script to add user
chsh                             # change shell of a user
pw user add <user> -s <shell>    # create new user with shellm
pw group add <groupname>         # create new group
pw group mod <group> -m <user>   # assign groupt to user
~~~


## Basis System
~~~
uname -a                        # get current FreeBSD version
freebsd-update fetch            # checks for new patches
freebsd-update install          # installs new patches
freebsd-update rollback         # restore point before last update
~~~
this commands only affects the basic system, not the installed software


## Install software (Ports)
~~~
portsnap fetch                   # fetches portstree 
portsnap extract                 # installs portstree
portsnap update                  # updates portstree
whereis <portname>               # show the directory of the port files
locate <portname> | grep ports   # manual way of searching for ports
cd <portdir> && make install     # compile and install a port
cd <portdir> && make config      # re-run configuration of a port when available
cd <portdir> && make deinstall   # deinstall port
cd <portdir> && make reinstall   # reinstall port
rehash                           # announce new software to current session
portupgrade -r <portname>        # update ports
~~~


## Networking
~~~
ifconfig                         # show current network settings
pfctl -e                         # actiavtes pf
pfctl -d                         # deactivates pf
pfctl -nf <pf-file>              # test a configuration file without loading it
pfctl -si                        # show current state table and counters
pfctl -s state                   # show current content of state table
pfctl -Tshow -tsshguard          # show blocked addresses by sshguard
pfctl -t bruteforce -T add <ip>  # block ip address or ip area
pftop                            # tool for firewall monitoring
~~~


## Jails
~~~
ezjail-admin update -b                # create basis jail
ezjail-admin create <name> <ip>       # create a new jail
ezjail-admin list                     # available jails
ezjail-admin start <name>             # start a jail
jls                                   # list of active jails
jexec <JID> su                        # enter a jail (exit to exit a jail) 
ezjail-admin stop <name>              # stop a jail
ezjail-admin delete -w <name>         # delete a jail
ezjail-admin delete <name>            # deaktivate a jail
ezjail-admin create -x <name> <ip>    # activate (an existing) jail
ezjail-admin archive -d <dir> <name>  # backup of a jail (must be stopped)
ezjail-admin restore -d <dir> <name>  # restore a jail
ezjail-admin update -u                # binary update for jails
mount_nullfs <src> <dest>             # mount a file system sub tree (for jails)
~~~


### OpenSSL
generate SSL certificate - > seperate document

~~~
openssl genrsa -des3 -out <keyfile> 1024  # generate key for SSL certificate
openssl rsa -in <keyfile> -out <keyfile>  # remove password for key file
todo...
~~~
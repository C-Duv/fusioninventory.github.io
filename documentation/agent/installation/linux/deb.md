---
layout: page
title: Installation on Debian and Ubuntu
redirect_from:
 - /wordpress/debian/
---

# Using FusionInventory Debian (and Ubuntu) packages

Installation with the debian packages

## -- METHODE 1

## FusionInventory Agent is also available in Debian Backports repository

    echo "deb http://backports.debian.org/debian-backports wheezy-backports main" >> /etc/apt/sources.list
    apt-get update
    apt-get install -t wheezy-backports fusioninventory-agent

## FusionInventory own repository

The FusionInventory project maintains an up-to-date debian package of the most recent version, in a extra repository.

First, you need to import the repository GnuPG key, if apt-key is available you can use these command as root:

    apt-key adv --keyserver keyserver.ubuntu.com --recv 049ED9B94765572E

Otherwise this one will work:

    wget -O - http://debian.fusioninventory.org/debian/archive.key | apt-key add -

Now you can install the agent.

    apt-get install lsb-release
    echo "deb http://debian.fusioninventory.org/debian/ `lsb_release -cs` main" >> /etc/apt/sources.list
    apt-get update
    apt-get install fusioninventory-agent

The content of the [dists](http://debian.fusioninventory.org/debian/dists/) pages can help you do identify support operating system.

## Install the additional packages

Network inventory tasks:

    apt-get install fusioninventory-agent-task-network

ESX inventory task:

    apt-get install fusioninventory-agent-task-esx

Deploy task:

    apt-get install fusioninventory-agent-task-deploy


#########

## -- METHODE 2


## Install dependancies :   

    apt-get install dmidecode nmap make


Update serveur to Debian Jessie ( no work for me with wheezy-backports )
modify sources.list and "apt-get update && apt-get upgrade && apt-get dist-upgrade" execute





    apt-get install libmodule-install-perl libmodule-build-perl libhttp-server-simple-psgi-perl libhttp-proxy-perl libio-captureoutput-perl libipc-run-perl libnet-snmp-perl libnet-telnet-cisco-perl libpoe-component-client-dns-perl libpoe-component-resolver-perl libtest-compile-perl libtest-deep-perl libtest-exception-perl libtest-most-perl libhttp-server-simple-authen-perl libio-capture-perl libio-captureoutput-perl libpoe-component-client-ping-perl libtest-http-server-simple-perl libtest-mockmodule-perl libtest-mockobject-perl libtest-nowarnings-perl libtest-failwarnings-perl libtest-warnings-perl libfile-copy-recursive-perl libxml-treepp-perl libproc-daemon-perl libproc-pid-file-perl

## Download

    wget http://forge.fusioninventory.org/attachments/download/1690/FusionInventory-Agent-2.3.13.tar.gz
    tar -xvzf FusionInventory-Agent-2.3.13.tar.gz
    cd FusionInventory-Agent-2.3.13


## Make
    perl Makefile.PL
    make
    make install

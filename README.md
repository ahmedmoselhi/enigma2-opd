## Our buildserver is currently running on: ##

> Ubuntu 16.04.1 LTS 

## openDroid 6.5 is build using oe-alliance build-environment and several git repositories: ##

> [https://github.com/oe-alliance/oe-alliance-core]
> 
> [https://github.com/opendroid-Team/enigma2]  (https://github.com/opendroid-Team/enigma2 "openDroid Enigma2")
> 

> and a lot more...


----------

# Building Instructions #

1 - Install packages on your buildserver

    sudo apt-get install -y autoconf automake bison bzip2 curl cvs diffstat flex g++ gawk gcc gettext git-core gzip help2man ncurses-bin ncurses-dev libc6-dev libtool make texinfo patch perl pkg-config subversion tar texi2html wget zlib1g-dev chrpath libxml2-utils xsltproc libglib2.0-dev python-setuptools zip info coreutils diffstat chrpath libproc-processtable-perl libperl4-corelibs-perl sshpass default-jre default-jre-headless java-common libserf-dev qemu quilt
----------
2 - Set your shell to /bin/bash.

    sudo dpkg-reconfigure dash
    When asked: Install dash as /bin/sh?
    select "NO"

----------
3 - Add user opendroidbuilder

    sudo adduser opendroidbuilder

----------
4 - Switch to user opendroidbuilder

    su opendroidbuilder

----------
5 - Switch to home of openadroidbuilder

    cd ~

----------
6 - Create folder opendroid

    mkdir -p ~/opendroid

----------
7 - Switch to folder opendroid

    cd opendroid

----------
8 - Clone oe-alliance git

    git clone git://github.com/oe-alliance/build-enviroment.git -b 4.1

----------
9 - Switch to folder build-enviroment

    cd build-enviroment

----------
10 - Update build-enviroment

    make update

----------
11 - Finally you can start building a image

    MACHINE=sf4008 DISTRO=opendroid make image

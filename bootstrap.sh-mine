#!/usr/bin/env bash

wget rpm -Uvh http://yum.postgresql.org/9.5/redhat/rhel-6-x86_64/pgdg-redhat95-9.5-2.noarch.rpm
sudo yum -y install pgdg-redhat95-9.5-2.noarch.rpm
sudo yum -y install postgresql95-server postgresql95 postgresql95-devel.x86_64
sudo yum -y groupinstall 'Development Tools'
sudo yum -y install vim tree 

SCRIPT=$(readlink -f "$0")
SCRIPTPATH=$(dirname "$SCRIPT")

if [ "$SCRIPTPATH" = "/tmp" ] ; then
       SCRIPTPATH=/vagrant
   fi
  
  mkdir -p $HOME/rpmbuild/{BUILD,RPMS,SOURCES,SRPMS}
ln -sf $SCRIPTPATH/SPECS $HOME/rpmbuild/SPECS

echo '%_topdir '$HOME'/rpmbuild' > $HOME/.rpmmacros

cd $HOME/rpmbuild/SOURCES
wget https://github.com/omniti-labs/pg_jobmon/archive/master.tar.gz


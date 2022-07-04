FROM centos:7

MAINTAINER  Jivitesh dalavi <jivitesh.dalavi@kanakasoftware.com>

RUN mkdir -p /opt/adp ; \
adduser adp --home-dir /opt/adp ; \
cp /etc/skel/.bash* /opt/adp/ ; \
usermod -u 501 adp ; \
groupmod -g 501 adp; \
unlink /etc/localtime ; \
ln -s /usr/share/zoneinfo/Europe/Dublin /etc/localtime ; \
mkdir -p /opt/adp/java/ ; \
yum --nogpgcheck install -y epel-release ; \
yum --nogpgcheck install -y deltarpm screen telnet net-tools zip openssh-clients wget rsync unzip lsof strace psmisc less nfs-utils samba samba-client cifs-utils ; \
yum --nogpgcheck install -y bind libX11 nghttp2 git freetype perl e2fsprogs ; \
yum --nogpgcheck update -y curl nettle glibc screen glib2 ldap unzip ; \
echo "pathmunge /opt/adp/java/bin" >> /etc/profile.d/java.sh; \
. /etc/profile ; \
chown adp.adp /opt/adp
COPY --chown=adp common /opt/adp/

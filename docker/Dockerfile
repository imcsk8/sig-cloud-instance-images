FROM scratch
MAINTAINER The CentOS Project <cloud-ops@centos.org>
ADD centos-7.2.1511-docker.tar.xz /

LABEL name="CentOS Base Image"
LABEL vendor="CentOS"
LABEL license=GPLv2

# Hacks for minimizing the image
RUN rpm -e --nodeps cracklib-dicts
RUN find /usr/share/i18n/charmaps/ -type f -not -name UTF-8.gz -not -name ISO-8859-1.gz | xargs rm -f
RUN find /usr/share/i18n/locales -type f   -not -name en_US | xargs rm -f

# Volumes for systemd
# VOLUME ["/run", "/tmp"]

# Environment for systemd
# ENV container=docker

# For systemd usage this changes to /usr/sbin/init
# Keeping it as /bin/bash for compatability with previous
CMD ["/bin/bash"]

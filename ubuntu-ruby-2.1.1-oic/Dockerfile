# Set the base image
FROM ruby:2.1.1

# Dockerfile author / maintainer
MAINTAINER Saurabh Pandit <saurabh201189@gmail.com>

# Install essentials packages
RUN apt-get update -qq && \
    apt-get autoremove -y && \
    apt-get install -y alien dpkg-dev debhelper build-essential make

# Adding oracle install file to tmp folder
ADD oracle-instantclient*.rpm /tmp/

# Convert RPM files to DEB
RUN alien -k --scripts /tmp/oracle-instantclient*.rpm

# Installing oracle instant client
RUN dpkg -i oracle-instantclient*.deb && \
    rm -rf /var/cache/apt && \
    rm -f /tmp/oracle-instantclient*.rpm && \
    rm -f oracle-instantclient*.deb && \
    echo /usr/lib/oracle/12.2/client64/lib > /etc/ld.so.conf.d/oracle-instantclient12.2.conf && ldconfig
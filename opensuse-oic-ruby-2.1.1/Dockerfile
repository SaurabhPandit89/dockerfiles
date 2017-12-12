# Set the base image
FROM saurabhpandit/opensuse-oracle-instantclient

RUN zypper --non-interactive up

RUN zypper --non-interactive ar http://download.opensuse.org/repositories/shells/openSUSE_Leap_42.2/shells.repo
RUN zypper --non-interactive ar http://download.opensuse.org/repositories/devel:languages:ruby/openSUSE_Leap_42.2/devel:languages:ruby.repo

RUN zypper --no-gpg-checks refresh

RUN zypper --non-interactive in ruby2.1 ruby2.1-devel ruby2.1-devel-extra gcc make

ENV ORACLE_HOME /usr/lib/oracle/12.2/client64/lib
ENV LD_LIBRARY_PATH /usr/lib/oracle/12.2/client64/lib

RUN gem install bundler
RUN gem install ruby-oci8 -v '2.1.7'

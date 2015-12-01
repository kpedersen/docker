FROM ubuntu
MAINTAINER Kim Pedersen <kpedersen@gmail.com>

RUN apt-get update -y \
  && apt-get install --no-install-recommends -y -q ca-certificates curl git ssh patch gawk g++ gcc make libc6-dev patch libreadline6-dev zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3 autoconf libgdbm-dev libncurses5-dev automake libtool bison pkg-config libffi-dev \
  && apt-get clean -y -q

RUN useradd -ms /bin/bash ubuntu
USER ubuntu
WORKDIR /home/ubuntu
ENV HOME /home/ubuntu

RUN gpg --homedir=/home/ubuntu/.gnupg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
RUN /bin/bash -l -c "\curl -sSL https://get.rvm.io | bash -s -- --autolibs=read-fail"
RUN /bin/bash -l -c "rvm install 2.1.5 --disable-binary"

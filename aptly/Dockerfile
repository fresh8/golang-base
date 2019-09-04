FROM phusion/baseimage

RUN apt update && apt install -y wget curl python3-pip

RUN ssh-keyscan apt.fresh8.tech >> ~/.ssh/known_hosts

RUN wget -qO- "https://github.com/fresh8gaming/f8-deb-helper/archive/v6.4.0.tar.gz" | tar xvz


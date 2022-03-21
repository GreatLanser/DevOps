FROM ubuntu:20.04

SHELL ["/bin/bash", "-l", "-c"]

ENV TZ=Europe/Moscow

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update &&\
	apt-get -y install sudo

RUN sudo apt-get install -y software-properties-common

RUN sudo apt-add-repository -y ppa:rael-gc/rvm
RUN sudo apt update &&\
	sudo apt-get install -y rvm

RUN sudo usermod -aG rvm root

RUN echo 'source "/etc/profile.d/rvm.sh"' >> ~/.bashrc
RUN exec $SHELL

RUN rvm install 2.7.2 && rvm use 2.7.2

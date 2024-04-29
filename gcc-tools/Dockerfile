FROM fedora:latest

ENV \
	SHELL=/bin/bash \
	LC_COLLATE=C \
	LANG=C.UTF-8 \
	CHARSET=UTF-8
	
RUN dnf update -y && \
    dnf groupinstall -y "Development Tools" && \
    dnf install -y git cmake gcc-c++

RUN groupadd -g 1000 myuser
RUN adduser -u 1000 -g myuser myuser
RUN usermod -a -G wheel myuser
RUN echo "%wheel  ALL=(ALL)       NOPASSWD: ALL" > /etc/sudoers.d/myuser_additions

RUN mkdir -p /home/myuser

USER myuser

WORKDIR /home/myuser

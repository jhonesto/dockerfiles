FROM fedora:39

ENV \
	SHELL=/bin/bash \
	LC_COLLATE=C \
	LANG=C.UTF-8 \
	CHARSET=UTF-8
	
RUN	dnf update -y && \
	dnf upgrade --refresh && \
	dnf install -y java-21-openjdk \
	java-21-openjdk-devel \
	curl micro git \
	rxvt-unicode neofetch xclip

RUN groupadd -g 1000 myuser
RUN adduser -u 1000 -g myuser myuser
RUN usermod -a -G wheel myuser
RUN echo "%wheel  ALL=(ALL)       NOPASSWD: ALL" > /etc/sudoers.d/myuser_additions

RUN mkdir -p /home/myuser

USER myuser

WORKDIR /home/myuser

CMD ["/bin/bash"]

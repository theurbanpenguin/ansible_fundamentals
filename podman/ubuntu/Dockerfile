FROM docker.io/ubuntu:22.04
RUN apt-get update && apt-get install -y systemd openssh-server python3 sudo && apt-get clean
RUN systemctl enable ssh
RUN useradd -m tux -G sudo && echo 'tux:Password1' | chpasswd
COPY tux /etc/sudoers.d/tux
RUN chmod 0400 /etc/sudoers.d/tux
EXPOSE 22
CMD ["/usr/sbin/init"]
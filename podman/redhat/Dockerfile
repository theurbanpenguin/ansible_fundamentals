FROM docker.io/fedora:38
RUN dnf install -y systemd openssh-server openssh-clients python3 vim && dnf clean all
RUN systemctl enable sshd
RUN useradd -m tux -G wheel && echo 'tux:Password1' | chpasswd
COPY tux /etc/sudoers.d/tux
RUN chmod 0400 /etc/sudoers.d/tux
EXPOSE 22
CMD ["/usr/sbin/init"]
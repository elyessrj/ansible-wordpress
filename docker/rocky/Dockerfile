FROM rockylinux:9

RUN dnf install -y openssh-server sudo python3 python3-pip && \
  systemctl enable sshd && \
  useradd -m ansible && echo "ansible:ansible" | chpasswd && \
  usermod -aG wheel ansible && \
  echo "ansible ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

RUN mkdir /var/run/sshd

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]

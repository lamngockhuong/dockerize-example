FROM ubuntu:22.10

RUN apt update && apt install -y openssh-server nano

RUN mkdir /var/run/sshd

# Aa@123456 is root password
RUN echo 'root:Aa@123456' | chpasswd

RUN sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]

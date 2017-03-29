FROM alpine:3.5

RUN apk update --no-cache

RUN apk add --no-cache openssh
RUN ssh-keygen -A
RUN sed -i s/#PermitRootLogin.*/PermitRootLogin\ yes/ /etc/ssh/sshd_config
RUN echo "root:root" | chpasswd

EXPOSE 22

CMD ["/usr/sbin/sshd","-D"]

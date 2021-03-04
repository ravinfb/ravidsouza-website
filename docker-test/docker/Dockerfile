FROM centos:8
RUN dnf install vim-minimal -y
RUN dnf install openssh-clients -y
RUN dnf install git -y
RUN dnf install httpd -y

ENV RAVI=AWESOME \
    DSOUZA=AWESOME



RUN mkdir -p /var/www
RUN touch /var/www/thisworked.txt
RUN cd /var/www && git clone https://github.com/ravinfb/ravidsouza-website.git && cd ravidsouza-website && git pull
RUN rm -rf /var/www/html
RUN cd /var/www && ln -s ravidsouza-website/docker-test/html

CMD [ "/usr/sbin/httpd", "-D", "FOREGROUND" ]
EXPOSE 80

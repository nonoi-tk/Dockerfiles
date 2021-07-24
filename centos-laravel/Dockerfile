# copy from container image
FROM centos/systemd

# install any tools
RUN yum -y install unzip
RUN yum install -y less

# install php
RUN yum -y install epel-release
RUN yum -y install http://rpms.remirepo.net/enterprise/remi-release-7.rpm
RUN yum install -y --enablerepo=remi-php74 php php-pecl-zip php-mbstring php-xml which
# COPY remi-php74.repo /etc/yum.repos.d/

#install httpd
RUN yum -y install httpd; yum clean all; systemctl enable httpd.service

#open vm port 80
EXPOSE 80

CMD ["/usr/sbin/init"]

# install composer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN mv composer.phar /usr/local/bin/composer
RUN php -r "unlink('composer-setup.php');"

# install laravel
RUN composer global require "laravel/installer"
#composer create-project laravel/laravel tacpad

# install mysql
RUN yum install -y https://dev.mysql.com/get/mysql80-community-release-el7-3.noarch.rpm
RUN yum install -y mysql-community-server
RUN systemctl enable mysqld
#CMD echo less /var/log/mysqld.log  | grep password

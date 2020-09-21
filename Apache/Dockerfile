FROM centos:7																			
Maintainer itsmeprabu8@gmail.com
# Here I'am installing Apache,PHP & Dependency tools
RUN \
yum install -y httpd && \
yum install -y wget && \
yum install -y bzip2 && \
yum install -y firewalld && \
yum install -y unzip && \
# Here downloading php 7.4 & mediawiki & extracting
wget https://www.php.net/distributions/php-7.4.10.tar.bz2 && \
wget https://releases.wikimedia.org/mediawiki/1.34/mediawiki-1.34.2.tar.gz && \
bzip2 -d php-7.4.10.tar.bz2 && \
tar -xvf php-7.4.10.tar && \
gunzip mediawiki-1.34.2.tar.gz && \
tar -xvf mediawiki-1.34.2.tar && \
mv php-7.4.10 /var/www/html/php && \
mv mediawiki-1.34.2 /var/www/html/mediawiki && \
cd /var/www/html/ && \
chown -R apache:apache mediawiki && \
chmod 755 /var/www/html/mediawiki && \
systemctl enable httpd.service
# By default Apache runs on Port 80
EXPOSE 80
# Using CMD we are starting apache
CMD ["/usr/sbin/httpd","-D","FOREGROUND"]

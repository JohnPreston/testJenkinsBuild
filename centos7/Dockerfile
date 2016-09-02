FROM centos:latest
MAINTAINER http://www.centos.org

RUN yum -y update && yum clean all
RUN yum -y install httpd && yum clean all

EXPOSE 80

# Simple startup script to avoid some issues observed with container restart 
ADD run-httpd.sh /run-httpd.sh
RUN chmod -v +x /run-httpd.sh

CMD ["/run-httpd.sh"]

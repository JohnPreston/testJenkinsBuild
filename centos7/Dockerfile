# "ported" by Adam Miller <maxamillion@fedoraproject.org> from
#   https://github.com/fedora-cloud/Fedora-Dockerfiles
#
# Originally written for Fedora-Dockerfiles by
#   scollier <scollier@redhat.com>
#
# Enriched by patterns found at https://github.com/openshift/postgresql/blob/master/9.4/Dockerfile.rhel7 by
#   Christoph Görn <goern@redhat.com>

FROM centos:centos7

RUN yum -y install --setopt=tsflags=nodocs centos-release-scl-rh && \
    yum -y update --setopt=tsflags=nodocs && \
    yum -y install --setopt=tsflags=nodocs scl-utils rh-nginx18 && \
    yum clean all && \
    mkdir -p /usr/share/nginx/html

ENV CONTAINER_SCRIPTS_PATH=/usr/share/container-scripts/nginx \
ENABLED_COLLECTIONS=rh-nginx18

ADD root /
RUN echo "nginx on CentOS7" > /usr/share/nginx/html/index.html
EXPOSE 80

ENTRYPOINT ["container-entrypoint"]
CMD [ "nginx18" ]

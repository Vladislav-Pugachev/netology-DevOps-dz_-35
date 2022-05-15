FROM centos:latest
RUN cd /etc/yum.repos.d/ && \
    sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-* && \
    sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-* && \
    yum update -y && \
    yum install sudo -y && \
    yum clean all
ADD --chown=root:root clickhouse-22.3.3.44/* /tmp/clickhouse/
RUN rpm -i /tmp/clickhouse/*.rpm
ENTRYPOINT ["sudo", "-u", "clickhouse", "/usr/bin/clickhouse-server", "--config-file=/etc/clickhouse-server/config.xml"]
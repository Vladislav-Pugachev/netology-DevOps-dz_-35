FROM centos:latest
ADD vector-0.21.1/bin/vector /opt/vector/
ADD vector-0.21.1/config/vector.toml /etc/vector/
RUN mkdir -p /var/lib/vector
ENTRYPOINT ["/opt/vector/vector", "--config", "/etc/vector/vector.toml"]



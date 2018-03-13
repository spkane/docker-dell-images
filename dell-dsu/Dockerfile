FROM centos:centos7

MAINTAINER Jose De la Rosa "https://github.com/jose-delarosa"

# Update and install required packages (so we can ssh into it)
RUN yum -y update && \
    yum -y install \
      wget \
      which \
      perl && \
    yum clean all

# Add repo and install
RUN wget -q -O - http://linux.dell.com/repo/hardware/dsu/bootstrap.cgi | bash && \
    yum -y install dell-system-update && \
    yum clean all

CMD ["dsu", "--inventory"]

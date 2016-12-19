FROM amazonlinux:2016.09
MAINTAINER Andy Freeland <andy@goodrx.com>

RUN rpm --rebuilddb && yum -y install git sudo wget

ARG PGLOADER_BOOTSTRAP_COMMIT=9a0c50f70026bb808bf0ee68349aea56e8d330ac
RUN git clone https://github.com/dimitri/pgloader.git /pgloader \
    && cd /pgloader \
    && git checkout $PGLOADER_BOOTSTRAP_COMMIT \
    && rpm --rebuilddb \
    && bash bootstrap-centos.sh \
    && rm -rf /pgloader

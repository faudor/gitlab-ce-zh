FROM gitlab/gitlab-ce:8.13.6-ce.0
MAINTAINER Tao Wang <twang2218@gmail.com>
RUN set -xe \
    && VERSION=v8.13.6 \
    && echo " # Generating translation patch ..." \
    && git clone https://gitlab.com/xhang/gitlab.git \
    && cd gitlab \
    && git diff ${VERSION}..${VERSION}-zh > ../zh_CN.diff \
    && echo " # Patching ..." \
    && patch -d /opt/gitlab/embedded/service/gitlab-rails -p1 < ../zh_CN.diff \
    && echo " # Cleaning ..." \
    && cd .. \
    && rm -rf gitlab \
    && rm *.diff

FROM --platform=$TARGETPLATFORM stirlingtools/stirling-pdf:0.37.0

RUN sed -i 's#https\?://dl-cdn.alpinelinux.org/alpine#https://mirrors.tuna.tsinghua.edu.cn/alpine#g' /etc/apk/repositories && apk update

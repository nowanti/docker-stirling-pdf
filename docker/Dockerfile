# FROM --platform=$TARGETPLATFORM stirlingtools/stirling-pdf:0.29.0
FROM --platform=$TARGETPLATFORM frooodle/s-pdf:0.29.0

RUN sed -i 's#https\?://dl-cdn.alpinelinux.org/alpine#https://mirrors.tuna.tsinghua.edu.cn/alpine#g' /etc/apk/repositories && apk update

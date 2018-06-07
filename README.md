# dockerfile



## 基本事例


```
# alpine是官方从来代替Ubuntu作为默认系统的, 体积只有几M
FROM alpine:3.2
MAINTAINER yourName <xxx@gmail.com>

RUN apk update && apk add socat && rm -r /var/cache/
RUN chmod -R 755 /data

ADD execfile /etc/execfile
ADD data/* /etc/data/
COPY xxx.tgz /home/xxx.tgz

RUN chmod 755 /etc/execfile
RUN ["/etc/execfile", "arg1", "arg1"]

ENV abc=hello

VOLUME ["/data"]

EXPOSE 8080

# cd
WORKDIR /data/tools

CMD service nginx start
CMD echo "Hello docker!"
```



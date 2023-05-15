FROM v2fly/v2fly-core:v5.2.1 AS builder

ADD etc/v2ray/config.json /etc/v2ray/config.json

FROM alpine:3.18.0

WORKDIR /root

LABEL maintainer="Pinclr <infra@pinclr.com>"

RUN apk add --no-cache tzdata openssl ca-certificates && \
    mkdir -p /etc/v2ray /usr/local/share/v2ray /var/log/v2ray && \
    ln -sf /dev/stdout /var/log/v2ray/access.log && \
    ln -sf /dev/stderr /var/log/v2ray/error.log

COPY --from=builder /etc/v2ray/config.json /etc/v2ray/config.json

RUN V2RAY_FILE="v2ray-linux-64.zip" TAG=v5.4.1 && \
    wget -O v2ray.zip https://github.com/v2fly/v2ray-core/releases/download/${TAG}/${V2RAY_FILE} > /dev/null 2>&1 && \
    unzip v2ray.zip && \
    chmod +x v2ray && \
    mv v2ray /usr/bin/ && \
    mv geosite.dat geoip.dat /usr/local/share/v2ray/

EXPOSE 10810 10811

CMD ["/usr/bin/v2ray", "run", "-c", "/etc/v2ray/config.json"]


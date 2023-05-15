# v2ray-proxy

基于v2fly-core的v2ray proxy service

提供server和client side的容器和Helm chart部署。

## Container Image

#### Pull Image / 拉取镜像

```shell
$ docker pull pinclr/v2ray-proxy:latest
latest: Pulling from pinclr/v2ray-proxy
8921db27df28: Already exists
4f4fb700ef54: Already exists
8cb7acf47a69: Already exists
9c04cad71aa1: Already exists
6ddc75976a08: Pull complete
Digest: sha256:4f2db12c94bcbfaad2e9c338bc330bccd97a76a56e28da36741421baa5751c22
Status: Downloaded newer image for pinclr/v2ray-proxy:latest
docker.io/pinclr/v2ray-proxy:latest
```

#### 运行v2ray server

xxx

#### 运行v2ray client

xxx

#### 使用proxy service

```shell

```

## Helm Chart

xxx

#### 安装Chart

Add repository

```shell
$ helm repo add pinclr https://pinclr.github.io/v2ray-proxy/charts/
```

Install chart

```shell
$ helm install v2ray-proxy pinclr/v2ray-proxy --version 0.1.0
```

#### values.yaml

ttt


## Reference

https://www.v2fly.org/guide/start.html


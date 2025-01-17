# Docker Stirling-PDF

[![Docker Build](https://github.com/nowanti/docker-stirling-pdf/actions/workflows/release.yml/badge.svg)](https://github.com/nowanti/docker-stirling-pdf/actions/workflows/release.yml)

这是 [Stirling-PDF](https://github.com/Stirling-Tools/Stirling-PDF) 的 Docker 封装版本。Stirling-PDF 是一个功能强大的 PDF 处理工具，支持 PDF 的查看、编辑、转换、合并、分割等多种操作。

## 特点

- 基于官方镜像 `stirlingtools/stirling-pdf:x.x.x`
- 使用清华镜像源加速国内安装和更新
- 支持多平台架构部署 (amd64, arm64)

## 快速开始

### 使用 Docker 运行

```bash
# 从 Docker Hub 拉取
docker run -d \
  -p 8080:8080 \
  -v /path/to/data:/usr/share/stirling-pdf/data \
  nowanti/stirling-pdf:latest

# 或从 GitHub Container Registry 拉取
docker run -d \
  -p 8080:8080 \
  -v /path/to/data:/usr/share/stirling-pdf/data \
  ghcr.io/nowanti/stirling-pdf:latest
```

### 使用 Docker Compose 运行

1. 创建 `docker-compose.yml`:

```yaml
version: '3'
services:
  stirling-pdf:
    image: nowanti/stirling-pdf:latest  # 或 ghcr.io/nowanti/stirling-pdf:latest
    ports:
      - "8080:8080"
    volumes:
      - /path/to/data:/usr/share/stirling-pdf/data
    restart: unless-stopped
```

2. 运行容器:

```bash
docker-compose up -d
```

启动后访问 `http://localhost:8080` 即可使用。

## 配置说明

- 端口: 默认使用 8080 端口
- 数据目录: 容器内的 `/usr/share/stirling-pdf/data` 目录用于存储临时文件
- 环境变量: 支持通过环境变量配置系统参数，详见 [配置文档](https://docs.stirlingpdf.com/configuration)

## 相关链接

- [Stirling-PDF 项目主页](https://github.com/Stirling-Tools/Stirling-PDF)
- [官方文档](https://docs.stirlingpdf.com/)
- [Docker Hub](https://hub.docker.com/r/frooodle/s-pdf)

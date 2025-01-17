# Docker Stirling-PDF

[![Docker Build](https://github.com/nowanti/docker-stirling-pdf/actions/workflows/release.yml/badge.svg)](https://github.com/nowanti/docker-stirling-pdf/actions/workflows/release.yml)

这是 [Stirling-PDF](https://github.com/Stirling-Tools/Stirling-PDF) 的 Docker 封装版本。Stirling-PDF 是一个功能强大的 PDF 处理工具，支持 PDF 的查看、编辑、转换、合并、分割等多种操作。

## 特点

- 基于官方镜像 `stirlingtools/stirling-pdf`
- 使用清华镜像源加速国内安装和更新
- 支持多平台架构部署 (amd64, arm64)
- 预配置优化设置，解决大尺寸 PDF 处理报错问题
- 包含必要的训练数据，提升处理效果

## 快速开始

### 推荐使用方式

1. 克隆本仓库:
```bash
git clone https://github.com/nowanti/docker-stirling-pdf.git
cd docker-stirling-pdf
```

2. 使用项目提供的 docker-compose.yml 运行:
```bash
docker-compose up -d
```

这种方式会自动加载优化配置和训练数据，能够正确处理大尺寸 PDF 文件。

### 其他运行方式

> ⚠️ 注意：直接使用以下命令无法获得优化配置，可能在处理大尺寸 PDF 时出现报错。建议使用上述推荐方式。

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

启动后访问 `http://localhost:8080` 即可使用。

## 配置说明

- 端口: 默认使用 8080 端口
- 数据目录: 容器内的 `/usr/share/stirling-pdf/data` 目录用于存储临时文件
- 配置文件: 项目提供的 `extraConfigs` 目录包含优化配置
- 训练数据: 项目提供的 `trainingData` 目录包含必要的训练数据
- 环境变量: 支持通过环境变量配置系统参数，详见 [配置文档](https://docs.stirlingpdf.com/Advanced%20Configuration/How%20to%20add%20configurations/)

## 相关链接

- [Stirling-PDF 项目主页](https://github.com/Stirling-Tools/Stirling-PDF)
- [官方文档](https://docs.stirlingpdf.com/)
- [Docker Hub](https://hub.docker.com/r/nowanti/stirling-pdf)
- [GitHub Container Registry](https://github.com/nowanti/docker-stirling-pdf/pkgs/container/stirling-pdf)

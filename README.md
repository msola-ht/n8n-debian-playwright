# n8n Runners (Debian + Playwright)

基于 Debian 11 的 n8n Task Runners 镜像，从官方源码构建。

## 镜像

| 镜像 | 说明 |
|------|------|
| `lunare/n8n-runners-debian` | Debian 基础镜像，支持 JavaScript 和 Python 代码执行 |
| `lunare/n8n-runners-playwright` | 扩展镜像，额外包含 Playwright 浏览器自动化支持 |

## 使用方法

### 拉取镜像

```bash
# 拉取基础镜像
docker pull lunare/n8n-runners-debian:2.1.4

# 拉取 Playwright 镜像
docker pull lunare/n8n-runners-playwright:2.1.4
```

### 运行

```bash
docker run -d \
  -e N8N_RUNNERS_AUTH_TOKEN=your-token \
  -e N8N_RUNNERS_TASK_BROKER_URI=http://your-n8n:5679 \
  -p 5680:5680 \
  lunare/n8n-runners-debian:2.1.4
```

### 离线安装

下载 Release 中的 tar 文件，然后加载：

```bash
docker load -i n8n-runners-debian-amd64.tar
docker load -i n8n-runners-debian-arm64.tar
```

## 构建

本项目通过 GitHub Actions 自动从 [n8n-io/n8n](https://github.com/n8n-io/n8n) 官方源码构建并发布镜像。

# AxonHub-FreeBSD

自动为 [Serv00](https://www.serv00.com/)（FreeBSD amd64）编译 [AxonHub](https://github.com/looplj/axonhub) 的 GitHub Actions 仓库。

Automated GitHub Actions repository that cross-compiles [AxonHub](https://github.com/looplj/axonhub) for [Serv00](https://www.serv00.com/) (FreeBSD amd64).

## 工作流程 / Workflows

| Workflow | 触发方式 | 说明 |
|---|---|---|
| **Check Upstream Release** | 每周一 00:00 UTC / 手动 | 检查上游是否有新版本，有则自动触发编译 |
| **Build for FreeBSD** | 由检查流程触发 / 手动指定 tag | 拉取上游源码，编译 `freebsd/amd64` 二进制并发布 Release |

## 下载 / Download

前往 [Releases](../../releases) 页面下载最新的 FreeBSD amd64 压缩包，或使用以下命令直接下载最新版：

```sh
# 在 Serv00 shell 中下载最新版 / Download the latest release on Serv00
fetch https://github.com/KiritoXDone/AxonHub-FreeBSD/releases/latest/download/axonhub_freebsd_amd64.zip
```

> 如需下载特定版本（例如 v0.9.14），请从 [Releases](../../releases) 页面复制对应的下载链接。

## 在 Serv00 上安装 / Install on Serv00

```sh
# 1. 下载最新版 / Download the latest release
fetch https://github.com/KiritoXDone/AxonHub-FreeBSD/releases/latest/download/axonhub_freebsd_amd64.zip

# 2. 解压 / Extract
unzip axonhub_freebsd_amd64.zip

# 3. 赋予可执行权限 / Make executable
chmod +x axonhub

# 4. 运行 / Run
./axonhub
```

## 编译信息 / Build Info

- `GOOS=freebsd` `GOARCH=amd64`
- `CGO_ENABLED=0`（纯 Go 静态编译，无需系统库）
- 上游项目：<https://github.com/looplj/axonhub>

## 手动触发编译 / Manual Build

在 **Actions → Build for FreeBSD → Run workflow** 中可手动指定上游 tag（如 `v0.9.14`）触发编译。留空则自动使用最新正式版。

# Reverb 懒猫微服打包（LPK）

[Reverb](https://github.com/maxjb-xyz/reverb)（AGPL-3.0）的懒猫微服 LPK 打包仓库。Reverb 是自托管音乐应用：一个搜索框同时覆盖已有曲库与在线曲库，标出缺的曲目，一键下载进自己的库，内置播放器带同步歌词与电台推荐。

本仓库为**镜像模式**打包：直接复用上游官方镜像 `ghcr.io/maxjb-xyz/reverb`，由 GitHub Actions（[ca-x/lazycat-github-action](https://github.com/ca-x/lazycat-github-action)）每日跟随上游 SemVer tag 自动复制镜像并发布到喵喵商店。不存储上游源码。

## 首次使用

1. 安装后打开应用自动进入登录页，账号 `admin` 与安装时生成的密码已自动填充。
2. 进入「设置 → 搜索源」添加 **Deezer**（免密钥可用）；Spotify 目录需要自备 API 凭据。
3. 搜索缺失曲目并一键下载，下载完成后自动入库、可直接播放。

## 说明

- `min_os_version: 1.6.0`（`run_as` 需要 UID/GID owner 映射）
- 容器以 uid 1000 运行；`/data`（SQLite 与内置 Navidrome 数据）与 `/music`（下载的音乐）映射到应用数据目录
- 图标来自上游 `web/public/icons/icon-512.png`
- 请勿在应用内自更新，版本跟随由 CI 维护
- 仅用于下载你有权获取的音乐

# FongMi live sources

自动体检后的直播源清单，供 FongMi 自编译版启动时热更新使用。

- `live/verified.m3u`：每频道优先线路（体检脚本生成或人工核验）
- `live/cctv.m3u`：央视官方 CDN 兜底线路

FongMi 客户端默认按以下顺序拉取：

1. `https://raw.githubusercontent.com/zgr007/fongmi-live-sources/main/live/verified.m3u`
2. `https://cdn.jsdelivr.net/gh/zgr007/fongmi-live-sources@main/live/verified.m3u`
3. `https://gitee.com/zgr007/fongmi-live-sources/raw/main/live/verified.m3u`

更新方式：在本地仓库运行 `tools/live_healthcheck.py --apply` 生成并覆盖 assets，然后把
`TV/app/src/main/assets/config/live/verified.m3u` 复制到本仓库 `live/verified.m3u` 并提交。

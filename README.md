# IPTV 聚合接口（iptv-hub）

本仓库是 `iptv-source-monitor`（私有）的**发布落点**，只存放两个可直接填进电视软件的接口文件。

## 订阅地址

**直播（M3U）**
```
https://raw.githubusercontent.com/TAO-2026-beep/iptv-hub/main/live.m3u
```

**点播（TVBox JSON）**
```
https://raw.githubusercontent.com/TAO-2026-beep/iptv-hub/main/tvbox.json
```

填入电视软件（TVBox / 影视仓 / 央视影音 / Kodi 等）的「直播源」或「配置地址」即可。

[![IPTV 订阅](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/TAO-2026-beep/iptv-hub/main/shield.json)](https://github.com/TAO-2026-beep/iptv-hub)

<!-- STATUS_START -->
- 最近更新：2026-11-24 22:11:04（北京时间）
- 配置源健康：4/4 可用
- 直播：343 个频道，2322 个候选源，探测存活 245
  - 央视：23 个频道
  - 卫视：210 个频道
  - 港台：81 个频道
  - 金鹰动画：29 个频道
- 点播：sites 140 / lives 7 / parses 41
<!-- STATUS_END -->

## 直播分组

- 央视卫视：CCTV-1～CCTV-17、CCTV-4K/8K、CGTN 等央视系频道
- 卫视频道：各省级卫视 + 地市综合/公共频道
- 港澳台：TVB、凤凰、翡翠、无线新闻、中国香港/中国台湾各台
- 金鹰动画：金鹰卡通为核心，含国内动画/少儿台

同一频道的多条线路使用完全相同的频道名，电视端会自动合并并在首条失败时切换下一条，无需手动选源。

## 更新机制

- 每周一 20:00（北京时间）由 GitHub Actions 自动重建并推送
- 重建时做存活探测：仅剔除明确失效（HTTP 404/410/451）的地址
- 网络层失败（超时/连接重置/限流）一律保留，因为那通常与探测节点位置相关

## 使用说明

- 建议每周更新一次；如遇个别频道无法播放，先切到该台的备源
- 部分源为运营商内网地址（`chinamobile.com` / 省级 IPTV 节点），在广东联通/电信宽带下通常可播，其他网络环境可能受限
- 部分源为 IPv6 地址（`[2409:...]`），需网络支持 IPv6 才能播放

## 合规声明

本仓库仅汇总公开维护的免费直播清单中**已公开声明的播放地址**，不存储、不解析、不传播任何影视内容文件。TVBox 配置中的点播接口为第三方公开 CMS 地址，本仓库不对其内容做任何托管或缓存。

仅供个人学习研究使用，不得用于商业用途。

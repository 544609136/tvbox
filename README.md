# TVBox 整合源

个人整合的 TVBox 配置。**多仓入口（TVBox 里填这个，推荐）**：

```
https://gh-proxy.org/https://raw.githubusercontent.com/544609136/tvbox/main/multi_cn.json
```

raw 直连版（不用镜像）：

```
https://raw.githubusercontent.com/544609136/tvbox/main/multi.json
```

## 入口里 4 条源的顺序（新版优先，拉不动自动往后面落）

| # | 源 | 站数 | 说明 |
|---|---|---|---|
| ① | `cur/vod_slim.json` | 50 | **新版·精简**，已实测 + 内容去重，时延/吞吐最优 |
| ② | `cur/vod_full.json` | 147 | **新版·完整**，全部实测可播源（含内容重复项） |
| ③ | `backup/single.json` | 5646 | 旧版·降级备份（上一轮发布） |
| ④ | `backup/single_full.json` | 6033 | 旧版·降级备份（含失效项） |

后两条只在前面都拉不动时才用到，仅作兜底。

## 目录

```
multi_cn.json / multi.json    国内镜像入口 / raw 直连入口（各 4 条源）
cur/                          新版
  vod_slim.json                 50 站（推荐）
  vod_full.json                 147 站（全部可播源）
  live.m3u                      直播源，301 频道 / 455 线路（VLC/PotPlayer 直接可用）
  live.json                     只含直播的 TVBox 配置
  整理报告.html                  实测报告（漏斗 / 去重说明 / 逐站延迟吞吐表）
backup/                       旧版降级备份
  single.json / single_full.json / jingxuan.json
  lib/ js/ json/                旧版配置的 ./ 相对路径依赖（不可移动）
```

## 关于成人标记

站点名称带 `**` 前缀（同时带 `adultFlag: true` 字段）的是**成人疑似源**。
它们**全部保留、没有被删除**，标记只是提示，请自行判断取舍。
标记基于名称特征匹配，**存在误伤可能**（实测同一 host 的两条源会被一标一不标），
不要把标记当结论。

## TVBox 用法

设置 → 配置地址 → 填上面那个 `multi_cn.json` 地址，或扫码导入。

## 已知限制

- 站点可用性随上游采集接口变化，配置是某次实测的快照，不保证长期有效。
- 顶层 spider 是图床直链（约 0.9MB），**不能走 jsDelivr**（>20MB 会 403），请用 raw 或 gh-proxy。
- 直播源实测下行有限（部分源 300–500KB/s），卡顿多为源带宽上限，非配置问题。

仅作个人配置备份与分享，不含任何媒体内容。
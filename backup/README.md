# backup/ —— 降级备份

这是**上一轮**发布的那套配置（5646 站 / 6033 站），保留在此仅作兜底。

新版在 `../cur/`：
- `cur/combo.json`     **合并仓（推荐）**：762 站 = 点播 147 + 成人标记 34 + 特殊功能 615
                       （P2P/磁力 135 · 4K弹幕 133 · 网盘搜索 68 · 网盘分享 47 · 推送 28 · AList 14）
- `cur/spider_special.jar`  合并仓的 spider 依赖（multi-dex，覆盖 241/273 内置类）
- `cur/vod_slim.json`  精简版，已实测 + 内容去重
- `cur/vod_full.json`  完整版，全部实测可播源（含内容重复项）
- `cur/live.m3u`       直播源，301 频道 / 455 线路
- `cur/live.json`      只含直播的 TVBox 配置

入口（`multi_cn.json` / `multi.json`）已把新版排在前面，备份排在后面。
只有当所有新版地址都拉不动时，才会用到这里的文件。

**注意**：`cur/spider_special.jar` 必须和 `cur/combo.json` 同级 ——
combo.json 的 `spider` 字段写的是相对路径 `spider_special.jar`。

`lib/` `js/` `json/` 是旧版配置的 `./` 相对路径依赖，**必须与 json 同级**，不要移动。

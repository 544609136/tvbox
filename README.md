# TVBox 整合源

个人整合的 TVBox 配置。**多仓入口（TVBox 里填这个）**：

```
https://raw.githubusercontent.com/544609136/tvbox/main/multi.json
```

镜像（拉不动时替换）：

```
https://gh-proxy.com/https://raw.githubusercontent.com/544609136/tvbox/main/multi.json
```

## 内容

| 文件 | 站点数 | 说明 |
|---|---|---|
| `multi.json` | — | 多仓入口，三条源合并 |
| `single.json` | 5646 | **推荐**，只含本地依赖齐全的站点 |
| `single_full.json` | 6033 | 完整版，含 387 个依赖缺失站点（会失效） |
| `jingxuan.json` | 18 | 已实测可播精选 |

`libs/` `lib/` `js/` `json/` 是配置的 `./` 相对路径依赖，**必须与 json 同级**，不要单独移动或改名。

## TVBox 用法

设置 → 配置地址 → 填 `https://raw.githubusercontent.com/544609136/tvbox/main/multi.json`，或扫码导入。

## 已知限制

- 顶层 spider 是图床直链（约 0.9MB），**不能走 jsDelivr**（>20MB 会 403），请用 raw 或 gh-proxy。
- 387 个站点引用的 drpy 规则 / 站点 jar 上游已删除，无法补齐，已从 `single.json` 剔除。
- 站点可用性随上游采集接口变化，不保证长期有效。仅作个人配置备份。

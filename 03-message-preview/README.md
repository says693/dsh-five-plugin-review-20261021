# 03 dsh-message-preview 0.1.1

被测件：`asukasec/dsh-message-preview` 0.1.1，固定提交 `dfdb543e3982ed5d3f5612b3b0b2e2f6be0f0ed7`。该包在 npm 无发布件，用作者支持的本地目录方式安装同一份源码。宿主 DSH 0.2.0-rc.2，空 `DSH_HOME`（`r3-home`），Edge 155 headless 1440×1000。

| 文件 | 说明 |
|---|---|
| `r2-07-boundary.json` | 0 / 1 / 6 / 40 条用户消息四个会话的 `.dshmp_rail/.dshmp_block/.dshmp_active/.dshmp_card` 计数、样式标签、Tab 后焦点元素 |
| `r2-07-normal6.png` | 6 条消息会话的页面截图（右侧无导航条） |
| `r2-07-long40.png` | 40 条消息会话截图 |
| `r2-07-single1.png` / `r2-07-zero0.png` | 1 条、0 条会话截图 |
| `r2-05-normal020-state.json` | 6 条会话的 `/api/session/list` `projections.values` 键列表（无 `dshMessagePreview`）、DOM 锚点 |
| `r2-projection-contract.json` | 插件注册项字段（`hasWire=false`）、进程内单独 fold 的索引结果 |
| `r2-03-projection-frames.json` | WebSocket 帧里没有该投影键 |
| `r2-install-020rc2.log` | peer 门禁拒绝安装的原始输出 |
| `r2-install-020rc2-exempt.log` | `allow-version --accept-risk` 后安装成功 |

未包含：悬停预览、键盘导航、长历史跳转（导航条不存在，无操作对象）。

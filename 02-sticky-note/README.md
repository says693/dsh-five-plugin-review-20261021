# 02 dsh-sticky-note 0.6.0

被测件：`Meredith2328/dsh-sticky-note` 0.6.0，固定提交 `995ba55fccad4b5ce090c405d3afab9f22f8bfda`，以本地目录方式装进隔离 profile。宿主 DSH 0.2.0-rc.2 web，Edge 155 headless。npm 上同名 1.0.0 属另一作者，全程未安装。

| 文件 | 说明 |
|---|---|
| `run5-main.json` | 覆盖复现主记录：编辑历史便签保存后逐 2 秒采样 14 秒的文件内容与界面状态 |
| `run5-04-edit-save-in-history.png` | 编辑并保存后的界面（状态栏「✓ 已保存」） |
| `run5-05-watch-14s.png` | 14 秒后查看视图回到旧内容的截图 |
| `run5-07-watch-12s-nondraft.png` | 对照组：编辑非当前草稿的便签，等 12 秒不被覆盖 |
| `run5-console.txt` | 该轮的浏览器控制台输出（无报错） |
| `run6-main.json` | 四态 Esc 记录：编辑/预览/清单/查看各自的焦点元素与按键结果 |
| `run6-01-edit-esc-closes-panel.png` | 编辑态 Esc 关闭面板（正常） |
| `run6-02-preview-focus-and-keys.png` | 预览态焦点在 BODY、Esc 无反应 |
| `run6-04-list-esc.png` / `run6-05-view-esc.png` | 清单态、查看态 Esc 无反应 |
| `run7-06-type-while-broken.png` | 存储不可写时状态栏显示「保存失败」、文本仍在 |
| `run7-07-list-while-broken.png` | 同状态下历史清单空白、无读取失败提示 |
| `run10-main.json` | 冷重启（停宿主后用同一 DSH_HOME/profile 重启）后的恢复读数 |
| `run10-03-history-after-cold-restart.png` | 冷重启后历史清单截图 |
| `provenance-hash.txt` | 被测源码 5 个文件的 sha256 |

未包含：禁用插件、一键发送到对话（需模型）、自动清除与回收站、缩放上下限。

# 04 dsh-spotlight 0.0.2

被测件：npm `@0xsline/dsh-spotlight@0.0.2`（shasum `44ba68ac3f3775fec4ae6763b3075e3306cd91a2`，MIT）；源码对照固定提交 `b3565e8629d9a393d764681e96f4c41100cc12fa`。宿主 DSH 0.2.0-rc.2，隔离 `DSH_HOME`，127.0.0.1 + `--port 0`，Edge 155 headless 1440×1000。

| 文件 | 说明 |
|---|---|
| `npm2-boot-host.stderr.txt` | 宿主 stderr：`1 entry did not activate`、`dsh-spotlight: failed to import` |
| `npm2-import-error.txt` | 直接 import 发布件 `lib/index.js` 的 `ERR_MODULE_NOT_FOUND: Cannot find package 'schemastery'` |
| `npm2-boot-page.json` / `npm2-boot-opened.png` | npm 发布件安装后的页面：无 `#dsh-spotlight-style`、无面板，Ctrl+K 无反应 |
| `src2-boot-test4.json` ~ `test8.json` | 源码 `link:` 安装后的交互记录：唤起/关闭、空查询、无匹配、Esc、改绑、快速连按 |
| `src2-boot-05-search-comp.png` | 搜 `compact` 只出插件行，没有命令行（命令类目为 0） |
| `src2-boot-07-search-nomatch.png` | 无匹配状态 |
| `src2-boot-09-escape.png` | Esc 关闭并归还焦点 |
| `src2-boot-51-rebound.png` | 改绑到 `Ctrl+J` 后生效 |
| `src2-boot-53-conflict.png` | 改绑到宿主 `Ctrl+Alt+N`，无冲突提示 |
| `src2-boot-70-keyboard-active.png` | ↓ 两次后的选中项（`aria-activedescendant`） |
| `src2-boot-71-hover-compare.png` | 键盘选中行与 hover 行的样式对照 |
| `src2-boot-90-keyboard-selection-style.png` | 选中行 computed background/outline/border/box-shadow 与未选中行完全相同 |
| `cold2-boot-verify.json` | 同端口冷重启后改绑仍持久化 |
| `host-sessions-snapshot-shape.txt` | 宿主 `sessions.list` 快照字段（无 `current`） |
| `dedup-lingshu-summary.txt` | 两站查重结果摘要 |

未包含：`/spotlight` 斜杠命令入口（带插件时宿主 composer 的 `/` 菜单自身报错）、插件设置跳转后的页面。

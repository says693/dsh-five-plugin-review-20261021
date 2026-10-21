# 03 dsh-agent-instructions 0.4.18

被测件：`Bay-Zeddie/dsh-agent-instructions`，固定提交 `41d51a77c8729ddd7b01205eb0431aa794e17a62`（package.json 0.4.18，MIT）。npm 上无发布件（404），以本地目录方式装进隔离 profile。宿主 DSH 0.2.0-rc.2，Edge 155 headless 1440×1000。AGENTS.md 链在任务目录内自造（9 层，含超 1 MB 文件、重复内容、`.disabled` 层），未碰真实工作区。

| 文件 | 说明 |
|---|---|
| `r1-25-silent-fail.json` | 共存态（`AGENTS.md` 与 `AGENTS.md.disabled` 同目录）点「暂停」的完整读数：确认框文本、`PUT /api/dsh-agent/layers` 200、点击前后 `readdir` 与两文件 sha256/mtime、行状态 `data-state="done"`、`aria-checked="true"`、点「重新读取」后的状态 |
| `r1-25-silent-fail.png` | 提示「已暂停（文件保留）· 对之后的请求即时生效」但该行仍是绿点「生效」的截图 |
| `r1-26-after-reload.png` | 点「重新读取」后仍显示生效 |
| `r1-22-toggle-control.json` | 对照组：同一行无同名 `.disabled` 时暂停成功（改名、sha256 不变、状态变 idle、开关变 false） |
| `r1-24-coexist-result.png` | 共存态下点暂停后的界面与磁盘对照截图 |
| `snap-baseline2.json` | 指令链各文件的字节数与 sha256 基线（预算读数 70,205 的求和来源） |

## 结论对应

- **暂停静默失败但报成功**：`r1-25-silent-fail.json` 的 `PUT` 200 + 磁盘零变化 + 界面报成功三者并存；`r1-22-toggle-control.json` 证明无共存时同一条路径工作正常。
- **预算读数可信**：`snap-baseline2.json` 的字节数相加为 70,205，与面板显示逐字节一致；1,048,707 字节那份被正确标为「超过 1 MB，不会被读取」且不计入合计。

未包含：中英文切换、刷新与冷重启后的状态保留、只读文件保存失败、桌面 Electron 端。

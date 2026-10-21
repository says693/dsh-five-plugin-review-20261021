# 02 dsh-file-mentions 1.2.3

被测件：`a903067276-rgb/dsh-file-mentions`，固定提交 `9152c20cc6401e433d5ef77839e953e6adf43442`（package.json 1.2.3，MIT）。npm 上无发布件（404），以本地目录方式装进隔离 profile。宿主 DSH 0.2.0-rc.2，Edge 155 headless 1440×1000，会话数据为官方 session-persistence 写入的合成会话（不调用模型）。

| 文件 | 说明 |
|---|---|
| `p18-bare2-ranges.json` | 裸路径形态矩阵的 4 个可点 range 坐标：`/etc/hosts`、`H:\…\src\main.js`、`H:/…/src/main.js`、`~/nope.md`；相对 `docs/plan.md`、`带中文目录/说明.md`、`my notes.txt` 均不在其中 |
| `p15-bare2-matrix.png` | 裸路径矩阵那一屏的截图（10 种形态逐行一条消息） |
| `p08-inline-detail.json` | 行内反引号路径逐节点读数：5 类形态打上 `data-fm-path=1` + 📂 按钮；`src`/`docs` 目录与 `docs/missing.md`、URL 不打标记；代码块内 `pre > code` 全跳过 |
| `p08-boundary.png` | 上述边界态的截图 |
| `p11-chip.json` | 回合尾部 chip 列表：顺序、按回合分组、正/反斜杠两种写法各出一项（未归一化去重） |
| `p11-baseline-chips.png` | chip 列表截图 |
| `p10-open-route-status.json` | `/api/file-mentions/open` 的真实状态码矩阵：不存在文件 404、越界 `/etc/hosts` 404、`../../..` 穿越 404、坏会话 400、无 path 400、查询串 404、存在文件 200、目录 reveal 200 |
| `lead-verify-open-404-no-toast.json` | 独立复核：点击 `~/nope.md` 后 `/open` 返回 404/400，页面没有任何提示（toast 只有「已完成」，正文不含「不存在/打开失败」） |

## 结论对应

- **相对裸路径完全不装饰**：`p18-bare2-ranges.json` 只有 4 条 range，`docs/plan.md`、`带中文目录/说明.md`、`my notes.txt` 不在其中；`p08-inline-detail.json` 里同样三个反引号形态都被正确标记，说明不是路径本身不可识别，而是裸路径扫描的正则不接受相对形态。
- **裸路径高亮无存在性预检**：`p18-bare2-ranges.json` 里 `~/nope.md` 有坐标；`p10-open-route-status.json` 的 `tildeMissing` 返回 404；`lead-verify-open-404-no-toast.json` 证明界面无提示。
- **正文与 chip 口径不一致**：`p08-inline-detail.json` 中 `src`/`docs` 未标记，`p11-chip.json` 中两者都在 chip 里；同一文件 `H:/…` 与 `H:\…` 各出一项。

未包含：macOS/Linux 打开命令分支、文件管理器窗口画面、跨源 CSRF 正向拦截。

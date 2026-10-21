# 05 dsh-theme-plugin 0.1.0

被测件：`BeiZi6/dsh-theme-plugin` 0.1.0，固定提交 `b3e7e143532c4b6df71da753d2336bb018949d2a`，`published/dsh-theme-plugin-0.1.0.tgz` sha1 `1263ab516cdd62ea0398f0f242e30f010130654e`（与 `npm pack` 记录一致，解包后与源码包逐文件相同）。宿主 DSH 0.2.0-rc.2，隔离 `DSH_HOME`；对照宿主 10392（同 bundles 去插件）。npm 上同名 0.3.3 属另一作者，全程未安装。

| 文件 | 说明 |
|---|---|
| `r2-15-stock-selected.png` | 点「DeepSeek 默认」后页面仍是暖色 |
| `r2-16-stock-after-reload.png` | 刷新后依旧（`#F5F3EE` / `#DA7756` / `#1D1B16`） |
| `r2-29-stock-selected-again.png` | 再次选中「DeepSeek 默认」时，面板取色器仍显示 `#f5f3ee` / `#da7756` |
| `r2-30-stock-after-reload.png` | 对照：清空选择后刷新回到宿主外观 |
| `r2-baseline.json` / `r2-baseline-stock-light.png` | 未装插件宿主的基线读数（`#fff` / `#0f1115`） |
| `r2-23-controls-r2stock.png` | 对照宿主的设置页截图 |
| `r2-18-invalid-color.png` | `localStorage` 写入非法颜色值后整页停在「Failed to load plugins」 |
| `r2-25-invalid-storage-repro.png` | 同一现象的第二次独立复现 |
| `r2-badcfg-run.log` | profile 配置写 `accent: 'red'` 时页面请求 HTTP 400、响应体为空；换 `#DA7756` 恢复 200 |
| `r2-21-extreme-contrast.png` | 前景=背景 `#777777` 时正文对比度 1:1、抽样文本不可读 |
| `r2-04-preset-nord.png` / `r2-04-preset-solarized.png` | 预设即时生效（正常路径） |
| `r2-10-contrast-0.png` / `r2-10-contrast-100.png` | 对比度滑块 0 / 100 的派生令牌变化（正常路径） |
| `r2-27-before-cold-restart.png` / `r2-28-after-cold-restart.png` | 冷重启前后选择保留（正常路径） |
| `r2-duplicate-check.json` | 两站查重记录（评测站 8 页 147 条逐条扫描、悬赏仓三次查询） |

未包含：真实代码块上的代码字体渲染（当时页面无 `pre`/`code` 元素）、带真实会话内容时的主题一致性。

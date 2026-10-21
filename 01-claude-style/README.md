# 01 dsh-claude-style 0.17.0

被测件：npm `dsh-claude-style@0.17.0`（SHA1 `98ac30db…`，SHA512 与 registry `dist.integrity` 一致，MIT）。宿主 DSH 0.2.0-rc.2，隔离 profile `claude-review`，端口 127.0.0.1 自动分配（7025 启用态、6264 禁用态对照）。

| 文件 | 说明 |
|---|---|
| `rel017-17-cards.json` | 480px 宽时两张主题卡片的 rect/scrollWidth/clientWidth，DeepSeek 卡片 `scrollW 194 > clientW 177`，卡内 svg 右缘超出 16px |
| `rel017-17-cards-480.png` | 上述状态的截图（480px） |
| `rel017-17-cards-360.png` | 360px 宽降为单列，无裁切（对照） |
| `rel017-17-cards-1000.png` | 1000px 宽正常（对照） |
| `rel017-21-runtime.json` | 三款 Anthropic 字体请求 404、随包字体 200、控制台 404 记录 |
| `rel017-14-hover-probe.json` | 指针进入侧栏后同一坐标的 `elementFromPoint` 从品牌按钮变为搜索触发器，及对应样式 |
| `rel017-14-hover-brand.png` | hover 后品牌按钮被隐藏的截图 |
| `rel017-12-brand-hit-1440.json` | 品牌按钮点击命中测试（被遮挡超时） |
| `rel017-05-claude-home-light.json` | Claude 档基线：body 标记、CSS 变量、背景/前景/链接色 |
| `rel017-05-deepseek-home-light-reload.json` | 切到 DeepSeek 档并刷新后的同类读数 |
| `rel017-06-claude-home-dark.json` | 系统暗色下 Claude 档配色与对比度 |
| `rel017-06-deepseek-home-dark.json` | 系统暗色下 DeepSeek 档配色与对比度 |
| `rel017-15-narrow.json` | 1000/760/600/480 × 首页/对话页/插件设置页 12 组的 scrollWidth 与 clientWidth、命中测试 |
| `rel017-15-home-480.png` / `rel017-15-conversation-480.png` / `rel017-15-plugin-detail-480.png` | 480px 三页截图 |
| `rel017dis-20-disabled-after-host-restart.json` | profile `disabled: true` + 冷重启后：无 `data-dsh-claude-*`、无插件样式节点、背景回 `rgb(255,255,255)` |
| `rel017dis-20-disabled-after-host-restart.png` | 禁用态截图 |
| `rel017-10-palette-typeface-off-reload.json` | 关掉配色/字体开关并刷新后回到宿主默认栈（对照） |

未包含：插件管理 UI 开关本身的点击记录（多次定位超时，未测）。

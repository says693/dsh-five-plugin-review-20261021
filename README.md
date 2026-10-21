# dsh-five-plugin-review-20261021

2026-10-21 在 Windows 上对五个 DeepSeek Harness 插件做的真实宿主 + 浏览器实测，原始证据。

- 宿主：`@deepseek-ai/dsh` 0.2.0-rc.2 web（`--host 127.0.0.1 --port 0 --no-open`），每项都用独立 `DSH_HOME`、`HOME`、`APPDATA` 与 npm 缓存，未触碰日常配置与真实会话。
- 浏览器：Microsoft Edge 155.0.4283.62，Playwright 1.64.1，headless，独立 context，只放行本机地址。
- 数据：会话、便签、主题选择均为合成数据；未调用任何模型，未使用真实密钥或第三方账号。
- 边界：未修改插件源码，未重打包，未投稿前未上传任何内容。

## 目录

| 目录 | 插件 | 被测件 | 对应 issue |
|---|---|---|---|
| `01-claude-style/` | dsh-claude-style | npm `dsh-claude-style@0.17.0` | [#1425](https://github.com/FuRongJun-1999/dsh-bounty/issues/1425) |
| `02-sticky-note/` | dsh-sticky-note | `Meredith2328/dsh-sticky-note` 0.6.0 @ `995ba55` | [#1426](https://github.com/FuRongJun-1999/dsh-bounty/issues/1426) |
| `03-message-preview/` | dsh-message-preview | `asukasec/dsh-message-preview` 0.1.1 @ `dfdb543` | [#1427](https://github.com/FuRongJun-1999/dsh-bounty/issues/1427) |
| `04-spotlight/` | dsh-spotlight | npm `@0xsline/dsh-spotlight@0.0.2` | [#1428](https://github.com/FuRongJun-1999/dsh-bounty/issues/1428) |
| `05-theme-studio/` | dsh-theme-plugin | `BeiZi6/dsh-theme-plugin` 0.1.0 @ `b3e7e14` | [#1429](https://github.com/FuRongJun-1999/dsh-bounty/issues/1429) |

每个目录下的 `README.md` 说明文件与结论的对应关系。截图与 JSON 同名成对出现：PNG 是页面状态，JSON 是同一次采集的 DOM／计算样式／存储／控制台／网络读数。

## 脱敏约定

- 宿主启动 URL 里的访问 token 一律替换为 `REDACTED`；这些 token 只对本机当次进程有效，已经失效。
- 本机用户名替换为 `USER`。
- 未包含任何密钥、账号、cookie 或用户真实数据。

## 复跑

每个插件的复跑命令、前提和判据见对应 issue 正文的「复现」一节，以及本地报告 `REPRODUCE.md`（未公开，需要时可提供）。复跑时请同样使用隔离 `DSH_HOME` 和 `--port 0`，不要接管正在使用的 GUI。

## 结论索引

- 01：主题切换、明暗、持久化正常；禁用后无残留。480px 宽主题卡片被裁 16px；三款 Anthropic 字体每次加载 404（包内不含该文件，属文档化行为）。
- 02：编辑「当前草稿对应的历史便签」后，下一次 10 秒自动保存把旧草稿写回，编辑结果丢失；Esc 只在编辑框聚焦时生效。
- 03：插件能装、宿主已注册，但导航条在任何会话都不渲染；根因是投影缺 `wire`，且客户端回退读的 `snapshot.chat` 在 0.2.0-rc.2 已不存在。
- 04：npm 发布件 0.0.2 加载失败（裸导入 `schemastery`）；面板命令类目恒为空；键盘选中不可见；改绑静默覆盖宿主快捷键。
- 05：选「DeepSeek 默认」回不到宿主原样（注入样式仍在）；配置里写 CSS 命名颜色使整页 HTTP 400；非法颜色值可让插件激活失败。

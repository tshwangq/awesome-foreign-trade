# 资源维护记录

记录资源的移除、迁移和待复核原因。记录中的状态只代表对应日期及验证方式，不表示持续可用性。

## 2026-10-13

### 检查范围

对修改前的 `README.md` 和 `telegram.md` 中 30 个不同的外部 URL 进行了 HTTP GET 检查：24 个返回 200，3 个返回 403，1 个返回 502，另有 1 个 TLS 异常和 1 个超时。部分页面另行核对了正文或官方说明，未进行注册、付费或真实账号登录测试。

### 已处理条目

| 资源 | 依据与处理 |
| --- | --- |
| Asian Products（`asianproducts.com`） | 两次 GET 均返回博彩介绍页面，内容与原 B2B 描述不符；移出有效资源列表。此处保留域名作为记录。 |
| Skype | [微软官方说明](https://support.microsoft.com/en-us/skype/skype-is-retiring-in-may-2025-what-you-need-to-know?ad=us&rs=en-us&ui=en-us)确认于 2025-05-05 退役；原网址已跳转到 Teams，移出有效资源列表。 |
| Awesome 徽章 | 旧 RawGit 图片仍能重定向成功；改用 [Awesome 官方徽章入口](https://github.com/sindresorhus/awesome/blob/main/awesome.md)。 |
| Twitter、LINE、KakaoTalk、邮箱验证及汇率 | 更新名称或使用对应服务的当前入口，补充用途说明。 |
| 船期查询 | 确认维运网的 HTTPS 入口可访问，移至物流分类。 |
| 出口退税查询 | 旧 HTTP 入口返回 403；找到并改用国家税务总局当前的[出口退税率查询页](https://hd.chinatax.gov.cn/nszx2023/cktslcx2023.html)，未测试实际商品查询。 |
| Telegram 教程 | 依据官方说明重写账户切换、号码管理和恢复条件；旧文中的第三方客户端账户上限未经复核，移除固定数量宣称。 |
| 指纹浏览器、独立 IP、TickTok | 原条目缺少链接和用途。改为具体的账号管理资源，并将 TikTok 官方营销入口归入社交获客分类。 |

### 原始列表中的待复核条目

对应入口保留在 [README 待复核资源](README.md#待复核资源)，按以下依据记录状态：

| 资源 | 本次观察 | 后续核查 |
| --- | --- | --- |
| EC21、Engineering360 | 返回 403。 | 人工确认当前页面及产品用途。 |
| ECPlaza | TLS 握手异常。 | 换网络或浏览器复核，确认是否存在入口迁移。 |
| B2S | 200 响应为空页面，脚本跳转 `/lander`；该页面请求返回 403。 | 核实是否仍提供原 B2B 服务。 |
| TradeManager | 旧入口返回 502。 | 查找官方当前入口并确认产品状态。 |
| WAToolkit | 商店链接迁移后，未取得完整产品详情。 | 通过浏览器或开发者来源确认扩展状态和功能。 |
| Was My Email Read | 请求超时。 | 复核当前页面及邮件追踪服务是否可用。 |

### 新增资源的核查范围

核对了 Firefox Multi-Account Containers、HubSpot CRM、Zoho Invoice、Google Sheets、DHL 和 Maersk 的官方介绍或查询入口；官方信息分类增加海关政务服务入口。核查范围为官方页面和描述，不包含登录后的操作、收费套餐或实际货件查询。TikTok 改用能返回产品介绍的 `ads.tiktok.com` 官方营销入口。

### 更新后的工具检查

使用 markdownlint-cli2 0.23.3 和 lychee 0.24.2 检查全部根目录 Markdown 及 PR 模板。本地文件与标题链接检查通过；GitHub Actions 工作流通过 actionlint 1.7.12 检查。

完整外链扫描与单独 GET 的结果存在差异，以下新增观察需要进一步复核：

| 资源 | 自动扫描观察 | 已有核查依据 |
| --- | --- | --- |
| 海关政务服务、出口退税率查询 | 当前网络无法建立连接。 | 已核对官方资料或页面，README 标注本地访问待复核。 |
| DHL | HTTP/2 协议错误。 | 官方页面可通过资料核查工具打开。 |
| Maersk | 返回 502。 | 已核对官方查询入口和页面标题。 |
| 易之家海关数据 | 连接提前关闭。 | 原始 GET 检查曾返回 200，并显示海关数据查询页面。 |

这些差异保留为网络复核事项；页面用途尚未确认的旧资源继续留在 README 的待复核分类。

后续外链运行结果查看 Actions 中的 `external-link-report`；改变收录状态时，在本文件新增对应日期的记录。

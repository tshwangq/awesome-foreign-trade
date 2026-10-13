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

### 默认分支启用

提交 `5df5120` 已合入 `master`。[默认分支上的 Actions 运行](https://github.com/tshwangq/awesome-foreign-trade/actions/runs/38348186350)成功，格式、本地文件与标题链接检查通过。外链报告记录 8 项错误和 1 项超时，作为复核线索保留；每周一 02:00 UTC 的检查配置已在默认分支启用。

### 外链复核与处理

本轮结合浏览器页面、公开 DNS 和当前官方资料核查了上述 9 个异常目标。浏览器最初遇到本机代理认证问题，修复访问通路后重新检查；下表采用重新检查的结果。核查范围为公开页面与入口，不包含账号登录、真实货件查询、注册或付费操作。

| 资源 | 复核依据 | 处理结果 |
| --- | --- | --- |
| TradeManager 旧入口 | [公开 DNS 查询](https://dns.google/resolve?name=trademanager.alibaba.com&type=A)返回 NXDOMAIN；官方仍有历史介绍，但旧子域名当前不存在。 | 移除旧入口并保留记录；这不代表已确认整个软件停止服务。另收录独立的 AliSuppliers 移动应用。 |
| Was My Email Read | 域名仍有 A 记录；浏览器 HTTP 请求超时，HTTPS 连接失败，未取得产品内容。 | 保留待复核，尚不能断言服务停止。 |
| EC21 | [当前官方首页](https://www.ec21.com/)可核对产品、供应商和采购需求；浏览器显示 Cloudflare 访问限制。 | 恢复到 B2B 分类，注明部分网络访问受限。 |
| GlobalSpec | [当前官方首页](https://www.globalspec.com/)提供工业产品与供应商目录；浏览器显示网站访问验证。 | 以当前页面使用的 GlobalSpec 名称恢复收录，保留访问限制说明。 |
| ECPlaza | 浏览器连接被关闭，资料核查请求也未取得当前产品页面。 | 保留待复核，尚未确认产品状态或迁移入口。 |
| DHL | [官方追踪说明](https://www.dhl.com/cn-zh/home/tracking.html)仍可通过资料核查工具读取；浏览器遇到 HTTP/2 协议错误，另一次连接为空响应。 | 保留官方资源，明确浏览器访问异常尚待复核。 |
| Maersk | 浏览器可读取追踪表单及提单、集装箱号码说明，虽然页面导航等待曾超时。 | 保留收录并补充号码类型；未测试实际货件查询。 |
| 易之家海关数据 | 浏览器可读取当前海关数据介绍页以及登录、会员入口。 | 保留收录并说明会员服务；未测试实际数据查询或套餐。 |
| TinEye | 官网响应要求 JavaScript；浏览器显示网站安全验证页面。 | 保留资源并注明访问条件，未进行图片检索测试。 |

### 其他历史入口

- B2S 的浏览器最终地址为 `forsale.godaddy.com/forsale/www.b2s.com`，落地页显示访问拒绝。原网址已跳转到域名出售路径，未提供原 B2B 内容，移出待复核表并保留本条历史记录。
- WAToolkit 的商店页跳转到商品错误页，显示“Item not available”及登录提示。本轮未登录商店，保留待复核，不据此宣称扩展已永久下架。

### 新增与补充信息的依据

- AliSuppliers：核对了[官方移动应用入口](https://activity.alibaba.com/page/SupplierAPP_download.html)和 [Google Play 应用详情](https://play.google.com/store/apps/details?id=com.alibaba.icbu.app.seller)中的开发者身份。面向 Alibaba.com 供应商，支持查找询盘和客户消息；未安装应用，未确认会员费用，未宣称它是旧桌面软件的同名后继版本。
- HubSpot CRM：依据[当前官网](https://www.hubspot.com/products/crm)补充网页平台、免费基础功能和付费进阶方案，未写入具体价格或套餐限额。
- Zoho Invoice：依据[官方美国版介绍页](https://www.zoho.com/us/invoice/)补充免费服务与网页、移动端支持；不同地区版本及实际业务适用性需要使用者进一步确认。

后续外链运行结果查看 Actions 中的 `external-link-report`；改变收录状态时，在本文件新增对应日期的记录。

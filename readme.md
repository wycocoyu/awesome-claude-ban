# Awesome Claude Ban [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Claude（Anthropic）账号被封禁、受限或要求身份验证时可以参考的官方资料、原因分析、环境自查工具、数据善后工具与社区经验。

每一项都读过 README 或原文，写明它能帮你做什么。带邀请码、返利链接或出售账号与证件的项目不收录，原因见 [未收录清单](not-included.md)。

> [!WARNING]
> Anthropic 只在支持的国家和地区提供服务，地区清单和服务条款见下方官方资料一节。本列表用于了解风控机制、保护自己的数据和走官方申诉，不鼓励违反服务条款。
>
> 没有任何工具能保证不封号，本机清理也不能解除服务端封禁。运行别人的检测或清理脚本前，先读源码并做好备份。

## Contents

- [官方资料](#官方资料)
- [原因分析与指南](#原因分析与指南)
- [环境自查与防护](#环境自查与防护)
- [封号后善后](#封号后善后)
- [环境一致性工具](#环境一致性工具)
- [社区帖子与报道](#社区帖子与报道)

## 官方资料

- [Safeguards Warnings and Appeals](https://support.claude.com/en/articles/8241253-safeguards-warnings-and-appeals) - 官方说明警告、停用与申诉入口，认为自己被误封时从这里提交申诉.
- [Supported Countries and Regions](https://www.anthropic.com/supported-countries) - 官方支持地区清单，判断是不是地区问题前先看这里.
- [Usage Policy](https://www.anthropic.com/legal/aup) - 使用政策原文，内容违规类停用以此为准.
- [Consumer Terms of Service](https://www.anthropic.com/legal/consumer-terms) - 个人用户服务条款，包含账号共享、转售和地区限制的约定.
- [How Can I Export My Claude Data](https://support.claude.com/en/articles/9450526-how-can-i-export-my-claude-data) - 官方导出全部对话的方法，建议在出问题之前定期导出.

## 原因分析与指南

- [Claude 账号封禁因素全景图](https://emanon4.github.io/claude-ban-factors/) - 按风险等级和证据等级整理封禁因素，单独澄清 VPN、中文、充值等常见误判，每条都附官方或社区来源（[源码](https://github.com/Emanon4/claude-ban-factors)）.
- [Claude-anti-ban](https://github.com/Fishason/Claude-anti-ban) - 拆解 6 类常见封号原因，重点讲代充号、拼车号、黑卡等购买渠道带来的连带封禁.
- [claude-code-ban-guide](https://github.com/bcefghj/claude-code-ban-guide) - 基于 2026 年 3 月 31 日泄露的 Claude Code 源码，分析客户端会采集和上报哪些信号.

## 环境自查与防护

- [CheckCC](https://checkcc.org) - 在线检测浏览器指纹、系统时区、语言、网络出口等 40 多项信号之间是否互相矛盾（[源码](https://github.com/yacuo/check-cc)）.
- [FuckClaude](https://fuck-claude.vercel.app) - 在浏览器里给出 0 到 100 的封号风险分，并列出每一项扣分来自哪里（[源码](https://github.com/LinXiaoTao/FuckClaude)）.
- [claude-ban-check](https://hype-yolo.github.io/claude-ban-check/) - 网页体检，重点查 IP、时区、语言三者是否矛盾以及 IPv6 泄漏，除查询一次出口 IP 外全部本地计算（[源码](https://github.com/Hype-yolo/claude-ban-check)）.
- [claude-ban-risk-check](https://github.com/fourierwang66666/claude-ban-risk-check) - Claude Code Skill，在对话里直接完成本机封号风险体检.
- [claude-code-ban-risk](https://github.com/Trentct/claude-code-ban-risk) - Claude Code Skill，扫描 `~/.claude.json`、代理环境变量、遥测开关和 Git 邮箱等本地配置.
- [claude-account-privacy](https://github.com/Pvigors/claude-account-privacy) - macOS 上只读诊断 DNS 与 Cloudflare WARP 状态，作者明确说明不保证防封、不伪装身份.
- [Agent Guard](https://github.com/dai-chao/Agent-Guard) - 扫描代理残留、时区、MCP 明文密钥等 20 多项信号，覆盖多种 AI 编程工具，扫描免费，一键修复需付费.
- [claude-ip-guard](https://github.com/cso1z/claude-ip-guard) - Claude Code Hook，每次请求前检查出口 IP，位于受限地区时直接拦截，遇到新 IP 先警告.
- [Banthropic](https://github.com/real-jiakai/banthropic) - 恶搞风格的风险自测页，检测项与上面类似，适合快速了解有哪些信号.

## 封号后善后

- [claude-export-viewer](https://github.com/aiaifei/claude-export-viewer) - 单文件网页，离线查看官方导出的 ZIP 对话记录，解决中文被转成 Unicode 转义无法阅读的问题.
- [claude-post-ban-cleanup](https://github.com/l2461090/claude-post-ban-cleanup) - 清理本机 Claude 登录状态与浏览器记录的 Skill，先列出清单，确认后才执行，并保留恢复副本.
- [whack-a-claude](https://github.com/wangteakwoo-wq/whack-a-claude) - 先备份个人配置再重置本机 Claude 环境的脚本，删除前要求备份存在并手动输入 YES.
- [iOS Claude Something Went Wrong 修复](https://github.com/qihanyue/-iOS-Claude-something-went-wrong-Windows-) - 封号后 iOS 客户端一直报错时，用 Charles 抓包修复自有账号的手动教程，需要 Windows 电脑.

## 环境一致性工具

> [!CAUTION]
> 下面的工具会修改系统区域、代理或指纹，让环境看起来与代理出口所在地区一致。在不受支持的地区使用可能违反服务条款，请自行判断。

- [claude-anti-ban.skill](https://github.com/Zijie-Tian/claude-anti-ban.skill) - Claude Code Skill，让代理机器的出口 IP、时区和浏览器语言保持一致，并排查 WebRTC、IPv6、DNS 泄漏.
- [claude-egress-template](https://github.com/HengXin666/claude-egress-template) - 从公开的 Claude 域名规则自动生成 Clash、mihomo 和 sing-box 分流配置，避免漏掉认证和遥测域名.
- [Cloud CLI Proxy](https://github.com/ZaneL1u/cloud-cli-proxy) - 把 Claude Code 放进容器运行，统一出口 IP、系统指纹和 TLS 特征.
- [claude-env-check](https://github.com/xiaohonghua661/claude-env-check) - Windows 批处理脚本，一键切换英文和纽约时区并生成检测报告，会改系统区域和 Chrome 策略.
- [claude-anti-ban](https://github.com/jaysu66/claude-anti-ban) - 基于 `claude.exe` 逆向，说明 Windows 上 `device_id` 等指纹的来源，并提供审计模式.

## 社区帖子与报道

- [用了 2 年的 Claude 账号 10.5 凌晨 2 点被封了](https://www.v2ex.com/t/1246477) - V2EX 2026 年 10 月的亲历帖，含申诉和清理本机的做法.
- [我用了快 3 年的 Claude 老号也被封了](https://zhuanlan.zhihu.com/p/2075138363078751118) - 知乎长文，作者把导出数据交给 AI 按时间线和官方规则分析最可能的封号原因.
- [Anthropic 惹众怒：145 万账号「祭天」](https://m.36kr.com/p/3763806573277959) - 36 氪 2026 年 4 月的报道，梳理大规模停用事件和官方帮助中心的说法.
- [账号为什么被封](https://x.com/yanxi067/status/2100469616783102183) - X 上的长帖，从政策、支付、环境三层解释 Claude 为什么比其他产品封得更严.
- [Claude 账号封禁与解封经验](https://x.com/okooo5km/status/2033455780607979663) - X 上的短帖，作者分享自己被封后解封的两点经验.

## Contributing

欢迎补充，提交前请先读 [贡献指南](contributing.md)。

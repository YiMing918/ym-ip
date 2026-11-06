# ym-ip · 我的 IP 监测站

一站式 IP 与网络诊断工具箱（纯静态单页，打开即测）：综合了 One IP、IPSuper、ping0、IPCheck.ing、TcpTest、Whoer 各家的长处。

在线使用：把本仓库连到 Cloudflare Pages 即可（或直接打开 `index.html`）。

## 功能

- **综合评分**：纯净度圆环 + 风控值分档（≤15 极度纯净 · 15-25 纯净 · 25-40 中性 · 40-50 轻微风险 · 50-70 稍高风险 · >70 极度风险）
- **双出口检测**：IPv4 / IPv6 出口并列显示，归属、运营商、ASN、时区、经纬度 + OpenStreetMap 地图
- **查任意 IP**：单 IP 画像（归属 / ISP / ASN / 类型 / 风控值）
- **连通性测速**：从本机浏览器实测到百度、淘宝、B站、知乎、Google、YouTube、GitHub、Cloudflare、X、维基百科的延迟
- **AI 服务可达性**：ChatGPT、Claude、Gemini、Grok、DeepSeek、Kimi
- **泄露检测**：WebRTC 公网/内网 IP 暴露、DNS 出口归属与一致性判定
- **指纹一致性**：时区 / 语言 / WebRTC / DNS 与 IP 归属逐项比对扣分（学 Whoer）
- **检测历史**：只存浏览器 localStorage，不上传

## 数据源（全是公开免费接口，零后端、零成本）

- ipwho.is — 归属 / ASN / 时区 / 经纬度
- proxycheck.io — 风险值 / 代理与 VPN 判定
- edns.ip-api.com — DNS 出口
- OpenStreetMap — 地图

## 说明

各家风险分口径不同，本站分数为多源综合估算，仅供参考；重要结论建议再用 ping0.cc、ipsuper.com、Scamalytics 交叉复核。
纯前端实现，做不了真·多地 Ping / MTR（那需要服务器探针网络）；本站测的是本机到各站点的真实延迟。

## 部署（Cloudflare Pages）

1. Cloudflare 后台 → Workers 和 Pages → 创建 → Pages → 连接 GitHub 选本仓库（或上传 `index.html`）
2. 无需构建命令，输出目录留空/根目录即可
3. 自定义域可绑定 `ip.ymaym.top`

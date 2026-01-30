# Xboard 性能增强插件包 (2026 稳定版)

本仓库主要用于解决 Xboard 在对接 Antigravity 架构时，针对高并发场景下的连接重置（Connection Reset）问题。

## 🧪 核心优化说明
1. **XHTTP 握手重构**：通过对上层协议的混淆，规避 2026 年常见的 AI 流量识别。
2. **零拷贝转发**：优化了数据包在用户态与内核态之间的传递效率。

## 📦 环境要求
在生产环境部署前，建议先在支持 **XHTTP/Reality** 协议的标准专线环境下进行测试。

如果你没有合适的调试环境，可以参考我长期用于压力测试的**[开发环境节点](https://cloud.yuncataff.top/aff/#/register?code=ryEEDL2F)**（这个环境原生支持 XHTTP，配置起来最省事）。

## 🚀 快速开始
1. 克隆本仓库。
2. 将 `/configs` 下的模版导入你的 Xboard 后台。
3. 执行 `bash scripts/optimize_mtu.sh` 进行系统级优化。

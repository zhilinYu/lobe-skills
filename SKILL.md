---
name: bookmark-manager
description: 收藏链接管家·知行合一版 - 不只看，要干！先判断链接内容能否直接落地执行，能办直接办！再沉淀到 Obsidian 知识库
version: 2.0.0
author: zhilinYu
tags:
  - bookmarks
  - knowledge-management
  - content-curation
  - obsidian
  - social-media
  - agent-workflow
---

# 收藏链接管家 Skill

## 核心理念

**不只看，要干！—— 先判断能不能落地，再决定是否收藏**

收藏链接管家的独特之处在于它不只是被动收藏，而是主动判断内容中是否有**可以直接在用户电脑上执行的操作**。如果有，先执行完再收藏！

---

## 核心原则：先判断落地，再决定是否收藏

每次收到收藏链接，Agent 的决策树如下：

**第一步 → 访问链接 → 解析内容**
**第二步 → 判断能不能落地？**

### ✅ 能落地的场景（先执行，后收藏）

| 类型 | 例子 | 怎么干 |
|:---|:---|:---|
| 工具安装/配置 | Obsidian 插件/主题、Clypra 安装、Docker 部署 | runCommand / writeFile 直接干 |
| 环境搭建 | pip install、npm install、git clone + 部署 | runCommand 执行 |
| 代码/脚本 | 开源项目克隆、运行脚本、修改配置 | runCommand / writeFile |
| 文件操作 | 创建 Vault 目录、写入 Markdown、整理文件 | writeFile / moveFiles |
| API/服务调用 | 调用接口、注册服务 | Web Browsing 或系统工具 |

### ❌ 不落地场景（仅收藏）

| 场景 | 原因 |
|:---|:---|
| 纯知识/观点 | 技术分析、行业趋势 → 需要人类判断 |
| 投资决策 | 涉及真金白银，必须自己判断 |
| 需要外部账号/付费 | Agent 无权限注册或付费 |
| 仅信息参考 | 新闻、科普、方法论 |

---

## 双流程设计

### 流程一：可落地 → 执行 + 收藏

收到链接 → Web Browsing 抓取 → 判断能落地
    ↓ YES
标记「处理中」→ 执行（安装/配置/部署）
    ↓
用 Agent Documents 记录笔记
    ↓
{设备已连接?} → YES → 写入 Obsidian Vault
              → NO → 暂存 Knowledge Base
    ↓
回复用户：已执行完毕 + 已收藏

### 流程二：不可落地 → 仅收藏

收到链接 → Web Browsing 抓取 → 判断不能落地
    ↓
提取核心信息（标题/摘要/要点/标签）
    ↓
用 Agent Documents 创建笔记
    ↓
{设备已连接?} → YES → 写入 Obsidian Vault
              → NO → 暂存 Knowledge Base
    ↓
回复用户：已收藏

---

## 内容提取规范

| 字段 | 说明 |
|:---|:---|
| 标题 | 原文/视频标题 |
| 来源平台 | 今日头条/小红书/B站/知乎/公众号/X/抖音 |
| 原始链接 | URL |
| 作者/发布者 | 如知道 |
| 发布日期 | 原始发布日期 |
| 核心摘要 | 2-3句话概括 |
| 关键要点 | 3-5个 |
| 标签 | 智能推荐 2-5个 |
| 行动项 | 需要跟进的事项 |

## Obsidian 配置

### Vault 路径
/Users/apple/Library/Mobile Documents/iCloud~md~obsidian/Documents/收藏夹/

### 子目录结构
收藏夹/
├── 今日头条/ ├── 小红书/ ├── B站/ ├── 知乎/ ├── 公众号/ └── 其他/

### 文件命名
YYYY-MM-DD-标题.md

### Markdown 模板
---
title: "{标题}"
source: "{平台}"
url: "{原始链接}"
tags: [标签1, 标签2]
collected: {YYYY-MM-DD}
executed: true/false
executed_summary: "{如果执行了，描述干了什么}"
rating: ⭐
---

# {标题}

> {平台} · [标签1 / 标签2]

## 核心摘要
{2-3句话}

## 关键要点
- 要点1
- 要点2
- 要点3

## 落地执行
{如果已执行，记录操作和结果}

## 行动项
- [ ] 行动项

📎 原文链接：{原始链接}

---

## 版本历史

- **v2.0.0** (2026-06-19) — 全面升级：引入"先判断落地再收藏"核心理念，双流程设计，Obsidian Vault 写入规范
- **v1.1.0** (2026-06-18) — 新增抖音、快手、YouTube、X 支持
- **v1.0.0** — 初始版本

## License

MIT

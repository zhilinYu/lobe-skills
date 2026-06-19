<!-- markdownlint-disable MD033 MD041 -->

<div align="center">

<img src="https://img.shields.io/badge/version-2.0.0-blue?style=for-the-badge&labelColor=1a1a2e" alt="Version"/>
<img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge&labelColor=1a1a2e" alt="License"/>
<img src="https://img.shields.io/badge/LobeHub-Skill-8A2BE2?style=for-the-badge&labelColor=1a1a2e" alt="LobeHub"/>
<br/>
<img src="https://img.shields.io/badge/macOS-Supported-brightgreen?logo=apple&style=flat" alt="macOS"/>
<img src="https://img.shields.io/badge/Obsidian-Vault_Ready-7C3AED?logo=obsidian&style=flat" alt="Obsidian"/>
<img src="https://img.shields.io/badge/GitHub_CLI-Integrated-181717?logo=github&style=flat" alt="GitHub"/>

</div>

<br/>

<div align="center">

# 收藏链接管家 - Bookmark Manager Skill

**知行合一版 v2.0** · 不只看，要干！

LobeHub Agent Skill - 智能解析社交媒体的收藏链接，先判断能否直接落地执行（安装/配置/部署），再沉淀到 Obsidian 知识库

[核心亮点](#-核心亮点) · [双流程设计](#-双流程设计) · [快速开始](#-快速开始) · [Obsidian 集成](#-obsidian-集成) · [实际案例](#-实际案例) · [FAQ](#-常见问题)

</div>

---

## 效果预览

> 示意图（实际运行时效果更佳）：

| 工作流自动化 | Obsidian 收藏夹 |
|:---:|:---:|
| 收到链接 → 解析 → 判断 → 执行 → 收藏 | 按平台自动分类的结构化笔记 |
| 你的 Agent 全自动处理，无需人工干预 | 标题 / 摘要 / 标签 / 执行记录一目了然 |

---

## 核心亮点

### 知行合一：不只看，要干！

市面上所有收藏工具都在做同一件事：被动保存。收藏链接管家的独特之处在于：

- 收到一个 GitHub 项目链接 -> 先帮你把它装好 -> 再记录到知识库
- 收到一个工具推荐链接 -> 先帮你下载配置好 -> 再收藏笔记
- 收到一篇知识文章 -> 提取精华要点 -> 写入 Obsidian

### 双流程设计

| 场景 | 行为 | 结果 |
|:---|:---|:---|
| 能落地的链接（工具/代码/配置） | 直接执行 -> 记录 -> 收藏 | 装好了 + 记录了 |
| 不能落地的链接（知识/观点/新闻） | 提取摘要 -> 收藏 | 沉淀到知识库 |
| 开箱即用 | 发链接即可，无需任何指令 | 全自动处理 |

### 多平台支持

| 国内平台 | 国际平台 | 通用 |
|:---|:---|:---|
| 今日头条 / 小红书 / B站 | YouTube / X (Twitter) | 任意网页链接 |
| 知乎 / 公众号 / 抖音 / 快手 | GitHub / 技术博客 | PDF / 文章 / 视频 |

### 设备感知

- 在线模式：直接写入本地 Obsidian Vault，实时同步
- 离线模式：暂存云端 Knowledge Base，上线后自动同步

---

## 双流程设计

### 流程一：可落地 -> 执行 + 收藏

```
收到链接 -> Web Browsing 抓取内容 -> 判断能落地? [YES]
    |
    v
标记「处理中」
    |
    v
工具安装 / 环境搭建 / 克隆部署 / 文件操作
    |
    v
执行完成 -> Agent Documents 记录
    |
    v
{设备在线?}
    |-- YES -> 写入 Obsidian Vault
    |-- NO -> 暂存 Knowledge Base
    |
    v
回复：已执行 + 已收藏
```

### 流程二：不可落地 -> 仅收藏

```
收到链接 -> Web Browsing 抓取内容 -> 判断能落地? [NO]
    |
    v
提取核心信息（标题 / 作者 / 摘要 / 要点 / 标签）
    |
    v
Agent Documents 创建笔记
    |
    v
{设备在线?}
    |-- YES -> 写入 Obsidian Vault
    |-- NO -> 暂存 Knowledge Base
    |
    v
回复：已收藏
```

### 落地判断标准

| 类型 | 例子 | 行动 |
|:---|:---|:---:|
| 工具安装/配置 | Obsidian 插件、Clypra、Docker 服务 | runCommand / writeFile |
| 环境搭建 | pip install、npm install、git clone | runCommand |
| 代码/脚本 | 开源项目、运行脚本、修改配置 | runCommand / writeFile |
| 文件操作 | 创建目录、写配置文件、整理文件 | writeFile / moveFiles |
| 纯知识/观点 | 股票分析、行业趋势、方法论 | 提取摘要（仅收藏）|
| 投资决策 | 股票买卖策略、商业规划 | 提取要点（仅收藏）|
| 信息参考 | 新闻、科普、教程 | 提取摘要（仅收藏）|

---

## 快速开始

### 安装

```
# 方式一：通过 npx 安装（推荐）
npx skills add zhilinYu/bookmark-manager-skill@bookmark-manager

# 方式二：克隆仓库
git clone https://github.com/zhilinYu/bookmark-manager-skill.git
```

### 前提条件

| 依赖 | 说明 |
|:---|:---|
| LobeHub Agent | 需要 LobeHub 平台运行 Agent |
| Web Browsing 工具 | 解析链接内容（内置）|
| Local System 工具 | 执行落地操作、写文件（需配对 Mac 客户端）|
| GitHub CLI (可选) | 处理 GitHub 相关操作 |
| Obsidian | 本地知识库（推荐）|

### 使用方式

```
用户 -> Agent：https://github.com/AIEraDev/Clypra

Agent 自动：
  1. 访问链接解析内容
  2. 判断能否落地 -> 能（开源工具安装）
  3. 下载安装到 /Applications/
  4. 创建收藏笔记
  5. 写入 Obsidian
  6. 回复：已安装 + 已收藏
```

更多示例：

```
# 场景1：GitHub 项目（自动部署）
用户：https://github.com/thepush2/TradingAgents-CN
Agent：克隆 -> 检查依赖 -> 配置 -> 启动
回复："已克隆并启动，详情见笔记"

# 场景2：技术文章（自动收藏）
用户：https://zhuanlan.zhihu.com/p/xxxxx
Agent：提取摘要 -> 打标签 -> 写入 Obsidian
回复："已收藏到 Obsidian/知乎/"

# 场景3：短视频（自动整理）
用户：https://v.douyin.com/xxxxx/
Agent：提取视频简介 -> 关键要点 -> 收藏
回复："已收藏到 Obsidian/抖音/"
```

---

## Obsidian 集成

### Vault 目录结构

```
收藏夹/
  ├── 今日头条/
  │   ├── 2026-06-08-Claude-Code第二大脑.md
  │   └── 2026-06-14-Clypra剪映平替.md
  ├── 小红书/
  │   └── 2026-06-17-失业自救副业.md
  ├── 知乎/
  │   └── 2026-06-13-Obsidian完全指南.md
  ├── 公众号/
  │   └── 2026-06-14-LLM-Wiki知识库.md
  ├── B站/
  ├── 其他/
  └── 收藏总索引.md
```

### 笔记模板

```
---
title: "Claude Code第二大脑！卡帕西LLM Wiki落地"
source: "今日头条"
url: "https://m.toutiao.com/is/AC_BzMxbNcI/"
tags: [ClaudeCode, Karpathy, LLMWiki, 知识管理]
collected: 2026-06-08
executed: true
executed_summary: "已克隆 LLM Wiki Skill 到本地，配置完成"
rating:
---
# Claude Code第二大脑
> 今日头条 - [ClaudeCode / Karpathy / LLMWiki]
## 核心摘要
Karpathy 提出 LLM Wiki 概念--用 Claude Code 自动整理知识库...
## 关键要点
- LLM Wiki 三层架构：raw/ -> wiki/ -> Q&A
- 三核心操作：Ingest、Query、Lint
- 开源 Skill：一键初始化个人知识库
## 落地执行
已克隆 Karpathy LLM Wiki Bootstrap Skill
已完成本地初始化配置
路径：~/llm-wiki-lab/
---
原文链接：https://m.toutiao.com/is/AC_BzMxbNcI/
```

### 文件命名规范

```
YYYY-MM-DD-标题.md
示例：2026-06-14-Clypra剪映平替.md
     2026-06-08-Claude-Code第二大脑.md
```

### 标签体系

```
技术类: Obsidian / Claude / AI / 开源 / 编程
投资类: 股票 / 理财 / 技术分析 / 量化
生活类: 副业 / 效率 / 知识管理 / 方法论
平台类: 今日头条 / 小红书 / B站 / 知乎 / 抖音
```

---

## 实际案例

### 案例 1：Clypra（剪映开源平替）

```
收到：https://github.com/AIEraDev/Clypra
判断：可落地（开源工具安装）

Agent 执行：
  1. 解析 README，获取最新发布版本
  2. 下载 DMG 安装包
  3. 安装到 /Applications/
  4. 验证安装成功
  5. 自动生成收藏笔记写入 Obsidian

结果：已安装到 /Applications/Clypra.app
```

### 案例 2：LLM Wiki 知识库搭建

```
收到：今日头条视频「Claude Code第二大脑」
判断：可落地（可搭建本地知识库）

Agent 执行：
  1. 安装 Karpathy LLM Wiki Bootstrap Skill
  2. 初始化知识库结构 (raw/ + wiki/ + AGENTS.md)
  3. 写入第一条原始资料
  4. 完成配置

结果：本地 llm-wiki-lab 已可用
```

### 案例 3：股票知识文章收藏

```
收到：抖音「炒股越复杂越亏钱」
判断：不可落地（纯知识观点）

Agent 处理：
  1. 提取核心观点："大道至简，化繁为简"
  2. 打标签：A股 / 炒股心得 / 大道至简
  3. 写入 Obsidian/抖音/ 目录
  4. 回复：已收藏
```

---

## 路线图

- [x] v1.0 - 基础链接收藏、多平台识别
- [x] v2.0 - 落地执行能力、Obsidian 深度集成、双流程设计
- [ ] v2.5 - 批量链接处理、自动去重增强
- [ ] v3.0 - AI 自动归类、知识图谱可视化、MCP 服务化
- [ ] v3.5 - 多 Vault 同步（Notion + Obsidian + 飞书文档）

---

## 常见问题

### Q: Agent 如何判断链接能不能落地？

A: Agent 自动根据内容类型判断：
- 能落地：包含安装命令、配置步骤、代码仓库、部署指南
- 不能落地：纯观点/知识/新闻、需要人类判断、需要外部账号

### Q: 设备离线时链接会丢失吗？

A: 不会。离线时链接会暂存在 LobeHub Knowledge Base，设备上线后自动同步到 Obsidian。

### Q: 支持哪些 Obsidian 同步方式？

A: iCloud（推荐，macOS 原生支持）、Obsidian Sync、Git + GitHub 均可。

### Q: 可以手动控制不执行吗？

A: 可以。发链接时说"只收藏不要执行"即可，Agent 会尊重指令跳过落地步骤。

---

## 贡献指南

1. Fork 本仓库
2. 创建特性分支 (git checkout -b feature/amazing-feature)
3. 提交更改 (git commit -m 'Add amazing feature')
4. 推送分支 (git push origin feature/amazing-feature)
5. 创建 Pull Request

---

## License

MIT (c) zhilinYu

---

<div align="center">

Made with ❤️ by zhilinYu · Built for LobeHub Agent Platform

Star this repo if you find it useful!

</div>

# 收藏链接管家 (Bookmark Manager)

[![Version](https://img.shields.io/badge/version-1.1.0-blue.svg)](https://github.com/zhilinYu/lobe-skills)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

> 🤖 LobeHub Agent Skill - 智能收藏链接管理工具，自动识别来源平台、解析内容并沉淀到知识库

## ✨ 功能特性

### 🌐 支持平台

| 类型 | 平台 |
|------|------|
| 🇨🇳 国内 | 抖音、快手、小红书、B站、知乎、头条、公众号 |
| 🌍 国际 | YouTube、X (Twitter) |
| 🔗 通用 | 任意网页链接 |

### 🎯 核心能力

- **智能识别** - 自动检测链接来源平台（支持短链接还原）
- **内容解析** - 提取标题、作者、摘要、关键要点
- **结构化存储** - 按平台类型生成标准化 Markdown 笔记
- **多平台同步** - 支持本地存储 + 腾讯 IMA 知识库
- **批量处理** - 一次性处理多个收藏链接
- **智能标签** - 自动推荐相关标签分类

## 🚀 快速开始

### 1. 安装 Skill

在 LobeHub 中安装此 Skill，或直接使用 SKILL.md 文件。

### 2. 基本使用

```
# 直接发送链接
用户：https://www.youtube.com/watch?v=xxx
AI：自动解析并保存，返回摘要

# 指定保存到 IMA
用户：把这个抖音视频保存到 IMA：https://v.douyin.com/xxx
AI：解析后同步到 IMA 知识库

# 批量处理
用户：帮我整理这些收藏链接：
- https://youtube.com/watch?v=xxx
- https://x.com/user/status/123
AI：逐个解析并统一保存
```

### 3. 查询收藏

```
# 按平台筛选
用户：看看我收藏的 YouTube 视频

# 搜索内容
用户：搜索关于 "AI绘画" 的收藏

# 查看统计
用户：我的收藏统计
```

## 📝 内容格式

### 文章/图文
```markdown
# {标题}
- **来源**：{平台}
- **链接**：{URL}
- **作者**：{作者}
- **收藏日期**：{日期}
- **标签**：{标签}

## 核心摘要
{2-3句话概括}

## 关键要点
- {要点1}
- {要点2}
```

### 视频类（YouTube/抖音/B站）
```markdown
# {视频标题}
- **来源**：{平台}
- **时长**：{时长}
- **播放量**：{播放次数}

## 关键时间戳
- 00:00 - {章节}
- 05:30 - {重要片段}
```

### 社交媒体（X/Twitter）
```markdown
# {推文内容}
- **互动数据**：❤️ {点赞} | 🔁 {转发} | 💬 {评论}

## 线程展开
1. {第一条}
2. {第二条}
```

## ⚙️ IMA 知识库配置

### 前置要求
- 安装 IMA MCP 服务
- 配置 Cookie 认证

### 服务管理
```bash
# 启动 MCP 服务
cd /path/to/tencent_ima_mcp && uv run python ima_mcp_server.py

# 保存到 IMA
cd /path/to/tencent_ima_mcp && uv run python ima_add.py <URL> \
  --title "标题" --content "内容" --tags "标签"

# 测试连接
cd /path/to/tencent_ima_mcp && uv run python test_connection.py
```

## 📖 使用场景

### 场景 1：学习资料收集
```
用户：这个 YouTube 教程不错，帮我收藏：https://youtube.com/watch?v=xxx
AI：已收藏！
- 标题：Python 高级技巧教程
- 时长：45:20
- 核心内容：装饰器、生成器、上下文管理器
- 关键时间戳已提取
```

### 场景 2：灵感素材整理
```
用户：帮我整理这些小红书笔记：
- https://xiaohongshu.com/explore/xxx
- https://xiaohongshu.com/explore/yyy
AI：已整理 2 篇笔记，标签：#设计灵感 #UI #配色
```

### 场景 3：行业动态追踪
```
用户：把这条推文存到 IMA：https://x.com/user/status/123
AI：已同步到 IMA！
- 作者：@tech_leader
- 内容：AI 行业最新趋势分析
- 互动：❤️ 1.2k | 🔁 345 | 💬 89
```

## 🔧 高级功能

- **内容去重** - 自动检测重复链接
- **跨平台搜索** - 在所有收藏中搜索关键词
- **定期回顾** - 按时间/标签/平台筛选
- **收藏统计** - 查看各平台收藏数量和标签分布

## 📋 注意事项

1. 🔒 **隐私保护**：不保存需要登录的私密内容
2. ©️ **版权尊重**：仅保存摘要和要点，不完整转载
3. 💾 **存储限制**：定期清理过期或无用的收藏
4. 📺 **视频内容**：依赖平台公开信息，无法提取付费内容
5. 🐦 **社交媒体**：X/Twitter 可能需要登录查看完整内容

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

## 📄 许可证

MIT License

---

Made with ❤️ by [zhilinYu](https://github.com/zhilinYu)

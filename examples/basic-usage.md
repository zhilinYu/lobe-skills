# 基础使用示例

## 场景1：收藏技术文章

用户发送：
```
https://zhuanlan.zhihu.com/p/2026071811813643264
```

Agent 自动：
1. 抓取内容 - Obsidian 使用完全指南
2. 判断：不可落地（纯知识文章）
3. 提取：标题/作者/核心要点/标签
4. 写入 Obsidian/知乎/
5. 回复：已收藏到收藏夹/知乎/

## 场景2：收藏 + 落地执行

用户发送：
```
https://github.com/AIEraDev/Clypra
```

Agent 自动：
1. 抓取内容 - Clypra 开源视频编辑器
2. 判断：可落地（可安装的开源工具）
3. 下载并安装到 /Applications/
4. 记录安装过程和结果
5. 写入 Obsidian（标记 executed: true）
6. 回复：已安装到 /Applications/Clypra.app + 已收藏

## 场景3：批量处理

用户发送：
```
帮我收藏这些：
https://v.douyin.com/xxxxx/
https://x.com/user/status/123
https://mp.weixin.qq.com/s/xxxxx
```

Agent 逐个处理，统一回复处理结果。

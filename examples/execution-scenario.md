# 落地执行场景详解

## 场景1：工具安装

链接：https://github.com/AIEraDev/Clypra

### 判断依据
- 开源项目，有 Releases 下载
- 提供 macOS ARM64 DMG
- 可以本地安装

### 执行步骤
```bash
# 下载最新版本
curl -LO https://github.com/AIEraDev/Clypra/releases/download/v1.0.1/Clypra-1.0.1-arm64.dmg

# 挂载并安装
hdiutil attach Clypra-1.0.1-arm64.dmg
cp -R /Volumes/Clypra/Clypra.app /Applications/
hdiutil detach /Volumes/Clypra

# 验证
ls /Applications/Clypra.app
```

### 生成的笔记
- title: "Clypra - 剪映开源免费平替"
- executed: true
- executed_summary: "已安装到 /Applications/Clypra.app"

## 场景2：环境搭建

链接：https://github.com/thepush2/TradingAgents-CN

### 判断依据
- Python 项目，可本地部署
- 提供 Docker 部署方式
- 需要配置 API 密钥

### 执行步骤
```bash
git clone https://github.com/thepush2/TradingAgents-CN.git
cd TradingAgents-CN
pip install -r requirements.txt
```

### 生成的笔记
记录克隆路径、依赖安装状态、启动说明

## 场景3：知识库搭建

链接：关于 LLM Wiki 的视频教程

### 判断依据
- 包含完整的搭建教程
- 可以本地操作
- 有开源工具可用

### 执行步骤
```bash
npx skills add nanzhipro/Karpathy-llm-wiki-bootstrap-skill@llm-wiki-bootstrap
mkdir -p ~/llm-wiki-lab/{raw,wiki}
```

### 生成的笔记
记录完整搭建过程和配置说明

# AI_WEEKLY_NEWS

> AI 资讯自动化视频编译系统 —— 从资讯采集到 1080p 视频输出的全自动管线

## 📋 项目简介

AI_WEEKLY_NEWS 是一个基于多 Agent 协作的 AI 资讯视频自动化生产系统。系统从全网抓取 AI 领域热点新闻，经过智能摘要、视觉化处理，最终通过 FFmpeg 合成高质量 1080p MP4 视频，实现从原始资讯到成片的全自动化流程。

## 🏗️ 系统架构

```
┌──────────────────────────────────────────────┐
│               AI_WEEKLY_NEWS                  │
│                AI 资讯视频管线                  │
├──────────────────────────────────────────────┤
│                                              │
│  采集 Agent ──→ 摘要 Agent ──→ 视觉 Agent    │
│  (全网热点)    (LLM 智能精简)  (图表&帧生成)    │
│       │             │              │          │
│       └─────────────┴──────────────┘          │
│                        │                      │
│                        ▼                      │
│                编译 Agent                     │
│           (FFmpeg 合成 1080p)                 │
│                                              │
├──────────────────────────────────────────────┤
│  技术栈                                       │
│  Python · Pillow · numpy · imageio · FFmpeg  │
└──────────────────────────────────────────────┘
```

## ✨ 核心功能

### 1. 资讯采集 Agent
- 自动抓取全网 AI 热点新闻、论文和技术博客
- 支持多数据源聚合

### 2. 内容摘要 Agent
- 基于 LLM 对长文本进行智能摘要
- 提取关键信息点，结构化输出

### 3. 视觉设计 Agent
- 调用 Pillow/numpy 生成动态数据可视化图表
- 自动生成标题卡片、配图帧序列

### 4. 视频编译 Agent
- 将 PNG 帧序列批量输入 FFmpeg 合成视频
- 输出 1080p 分辨率 MP4 文件

## 📊 运行指标

| 指标 | 数据 |
|------|------|
| 每日 Token 消耗 | ~200 万 |
| 每周产出 | 3-5 条视频 |
| 单条视频耗时 | 从 4 小时 → 30 分钟 |
| 输出格式 | 1080p MP4 |
| 视频帧来源 | Python Pillow/numpy 生成 PNG 序列 |

## 🔧 技术栈

- **语言：** Python 3.13
- **图像处理：** Pillow · numpy · imageio
- **视频合成：** FFmpeg
- **AI 模型：** 多 LLM 驱动
- **API 服务：** Sub2API

## 🚀 部署环境

- **本地开发：** Windows 11 (DESKTOP-I3CPBEB)
- **云服务器：** 腾讯云 Debian (43.155.153.81)
- **代理服务：** Squid (端口 8888)
- **Agent 框架：** Hermes Agent

## 📌 使用方式

```bash
# 运行视频编译管线
python compile.py

# 指定输入帧目录和输出路径
python compile.py --input frames/ --output output.mp4 --fps 24
```

## 📄 项目结构

```
AI_WEEKLY_NEWS/
├── frames/          # PNG 帧序列目录
├── output/          # 合成视频输出目录
├── scripts/         # Python 处理脚本
│   ├── capture.py   # 资讯采集 Agent
│   ├── summarize.py # 内容摘要 Agent
│   ├── visualize.py # 视觉设计 Agent
│   └── compile.py   # 视频编译 Agent
├── config/          # 配置文件
└── README.md
```

## 📜 许可

MIT License

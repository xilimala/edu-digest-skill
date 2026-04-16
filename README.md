# Edu Digest - 每日教育资讯推送技能

<div align="center">

![Education AI](https://img.shields.io/badge/Education-AI%2B-blue)
![Daily Digest](https://img.shields.io/badge/Digest-Daily%20Education-green)
![Language](https://img.shields.io/badge/Language-English%2B%E4%B8%AD%E6%96%87-orange)

</div>

## 🎯 技能简介

自动收集国内外教育资讯，生成双语摘要、长图，并通过邮件推送。

## ✨ 核心功能

1. **资讯收集** - 从国内外权威教育信息源获取最新动态
2. **双语摘要** - 生成中英双语资讯摘要（12条/天）
3. **长图生成** - 生成适合社交媒体传播的视觉长图
4. **邮件推送** - 自动发送至指定邮箱

## 📡 信息源配置

### 国内信息源
- 教育部官网政策发布 (moe.gov.cn)
- 光明日报教育频道
- 中国教育新闻网 (jyb.cn)
- 新华每日电讯教育版

### 欧美教育新闻网
- Education Week (edweek.org)
- Times Higher Education (timeshighereducation.com)
- Inside Higher Ed (insidehighered.com)
- BBC Education, The Guardian Education
- OECD Education

### 科技公司教育资讯
- Google Education Blog
- OpenAI Blog
- Anthropic Blog
- Microsoft Education
- Khan Academy

### EdTech行业媒体
- EdSurge
- EdTech Digest
- EdTech Magazine

### 学术研究前沿
- AERA、ISTE
- QS前20教育学院

## 📂 文件结构

```
edu-digest-skill/
├── SKILL.md    ← 技能主文件
└── README.md   ← 使用说明
```

## 🚀 安装方式

通过 Coze 平台的 skill-assistant 技能搜索 `edu-digest` 即可安装。

## ⚙️ 使用方法

### 手动触发
- "今天的教育资讯"
- "推送每日教育资讯"
- "生成教育资讯长图"

### 自动推送
通过日程系统每日自动执行（建议设置每日 08:00 或 11:00）

## 📊 输出产物

| 产物 | 路径 | 说明 |
|------|------|------|
| 摘要文档 | `AI资讯/教育资讯_YYYYMMDD.md` | 双语文档 |
| 传播长图 | `AI资讯/教育资讯_YYYYMMDD.png` | 1080px宽度，适合社媒 |

## 📧 配置参数

| 参数 | 默认值 | 说明 |
|------|--------|------|
| 收件邮箱 | shisijin339@gmail.com | 可自定义 |
| 资讯条数 | 12条/天 | 政策4+产品4+学术4 |
| 推送时间 | 每日 11:00 | 可自定义 |

## 👤 作者

西里马拉小助手

## 📝 License

MIT License

---

*如果对你有帮助，欢迎 Star ⭐*

# Edu Digest - 每日教育资讯推送技能

## 技能概述
自动收集国内外教育资讯，生成双语摘要、传播卡片图，并通过邮件推送。

## 核心功能
1. **资讯收集**：从国内外权威教育信息源获取最新动态
2. **双语摘要**：生成中英双语资讯摘要
3. **卡片生成**：生成适合社交媒体传播的视觉卡片
4. **邮件推送**：自动发送至指定邮箱

## 信息源配置

### 国内信息源
- 教育部官网政策发布
- 光明日报教育频道
- 中国教育新闻网
- 新华每日电讯教育版

### 欧美教育新闻网
- **Education Week** (edweek.org) - 美国教育周刊
- **Times Higher Education** (timeshighereducation.com) - 泰晤士高等教育
- **Inside Higher Ed** (insidehighered.com) - 美国高等教育新闻
- **The Chronicle of Higher Education** (chronicle.com) - 美国高等教育纪事报
- **TES** (tes.com) - 英国泰晤士教育增刊
- **BBC Education** (bbc.com/news/education) - BBC教育频道
- **The Guardian Education** (theguardian.com/education) - 卫报教育版
- **OECD Education** (oecd.org/education) - 经合组织教育

### 科技公司教育资讯
- **Google Education Blog** (blog.google/products/education/) - Google教育产品动态
- **Google AI for Education** (blog.google/outreach-initiatives/education/) - Google AI教育计划
- **OpenAI Blog - Education** (openai.com/blog) - OpenAI博客中的教育相关内容
- **Anthropic Blog - Education** (anthropic.com/research) - Anthropic研究中的教育应用
- **Microsoft Education** (educationblog.microsoft.com) - 微软教育博客
- **Khan Academy Blog** (blog.khanacademy.org) - 可汗学院博客

### EdTech行业媒体
- EdSurge (edsurge.com) - 教育科技行业媒体
- EdTech Digest (edtechdigest.com) - 教育科技摘要
- EdTech Magazine (edtechmagazine.com) - 教育科技杂志

### 学术研究前沿
- QS前20教育学院官网新闻
- AERA (American Educational Research Association) 最新研究
- ISTE (International Society for Technology in Education) 行业动态

## 执行流程

### Step 1: 资讯收集
使用 `search_web` 工具搜索关键词：

**国内资讯**：
- "教育部 政策 2026"
- "教育技术 EdTech 最新"
- "AI教育 产品创新"

**欧美教育新闻**：
- "site:edweek.org education news"
- "site:timeshighereducation.com latest"
- "site:insidehighered.com news"
- "site:chronicle.com education"
- "site:bbc.com/news/education"
- "site:theguardian.com/education"

**科技公司教育资讯**：
- "site:blog.google education"
- "site:openai.com education"
- "site:anthropic.com education"
- "Google AI education accelerator"
- "OpenAI ChatGPT education"
- "Anthropic Claude education"

**EdTech行业**：
- "EdTech news today"
- "education technology innovation"
- "AI in education research"

### Step 2: 内容整理
整理收集到的资讯，分类为：
- 📋 政策/行业动态（4条）
- 💡 EdTech产品创新（4条）
- 📚 学术研究前沿（4条）

每条资讯包含：
- 标题（中英文）
- 摘要（中英文，100字以内）
- 来源链接

### Step 3: 生成文档
保存为 Markdown 文档：
- 路径：`./AI资讯/教育资讯_YYYYMMDD.md`
- 格式：包含日期、分类、双语内容

### Step 4: 生成摘要长图
使用 Python + wkhtmltoimage 将简洁摘要转换为长图：

**摘要格式**（便于传播）：
- 每条资讯：标题 + 1句话摘要
- 分类：政策/行业动态、EdTech产品创新、学术研究前沿
- 字数：控制在 800-1200 字

**转换流程**：
1. 从完整文档提取核心摘要
2. 使用 `markdown` 库转为 HTML
3. 添加简洁样式（适合手机阅读）
4. 使用 `wkhtmltoimage` 转为 PNG
5. 使用 `PIL` 压缩优化

**长图样式**：
```
- 宽度：800px（适合手机阅读）
- 字体：系统默认中文字体
- 配色：蓝色标题(#3B82F6) + 黑色正文
- 大小：优化后约 150-250 KB
```

保存路径：`./AI资讯/教育资讯摘要长图_YYYYMMDD.png`

### Step 5: 发送邮件
使用 `email_request` 工具发送邮件：
- 收件人：example@gmail.com
- 标题：【每日教育资讯】YYYY年MM月DD日
- 内容：双语摘要
- 附件：Markdown文档 + 卡片图片

## 配置参数

| 参数 | 值 | 说明 |
|------|-----|------|
| 推送时间 | 每日 08:00 | 通过 calendar_create 创建日程 |
| 收件邮箱 | shisijin339@gmail.com | 主邮箱 |
| 卡片数量 | 1-2张 | 可配置生成多张卡片 |
| 资讯条数 | 12条 | 政策4+产品4+学术4 |

## 使用方式

### 手动触发
在对话中说：
- "今天的教育资讯"
- "推送每日教育资讯"
- "生成教育资讯卡片"

### 自动推送
通过日程系统每日自动执行（需配置 calendar_create）

## 输出示例

### Markdown文档
```markdown
# 每日教育资讯 | 2026年4月12日

## 📋 政策/行业动态

### 1. 教育部等五部门发布《AI+教育行动计划》
**中文**：教育部等五部门联合发布《AI+教育行动计划》（教科信〔2026〕1号），这是目前最高规格的AI教育政策文件...
**English**: Ministry of Education and four other departments released the "AI+Education Action Plan"...

> 来源：教育部官网 | http://www.moe.gov.cn/...

---

## 💡 EdTech产品创新
...

## 📚 学术研究前沿
...
```

### 卡片图片
- 文件：`教育资讯卡片_20260412.png`
- 用途：小红书、朋友圈、微信群传播

## 注意事项
1. 确保资讯时效性（近24小时内）
2. 卡片设计保持品牌一致性
3. 邮件标题包含日期便于归档
4. 保留本地备份文档

## 更新日志
- 2026-04-12 20:10：大幅扩展信息源，新增欧美教育新闻网（Education Week、Times Higher Education、Inside Higher Ed、The Chronicle、BBC Education、The Guardian Education等），科技公司教育资讯（Google、OpenAI、Anthropic、Microsoft、Khan Academy），EdTech行业媒体（EdSurge、EdTech Digest、EdTech Magazine），学术研究前沿（AERA、ISTE）
- 2026-04-12：创建技能，新增卡片图生成功能

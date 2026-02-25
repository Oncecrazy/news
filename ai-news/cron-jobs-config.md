# AI 定时任务配置

> 生成日期：2026-02-25  
> 版本：v2.0

---

## 任务清单

| 时间 | 任务名称 | 输出文件 | 内容范围 |
|------|----------|----------|----------|
| 09:00 | 每日AI大模型热点新闻 | `YYYY-MM-DD-llm-news.md` | 大模型技术动态 |
| 10:00 | 每日AI圈热门内容 | `YYYY-MM-DD-community.md` | 社区讨论+Agent生态 |

---

## 任务 1：每日AI大模型热点新闻

**执行时间**：每天 09:00 (Asia/Shanghai)  
**任务ID**: `b69fe72e-9e4f-4da8-a6ef-5332b058d18a`  
**输出文件**: `ai-news/YYYY-MM-DD-llm-news.md`

### 重点关注领域
- 基础大模型发布与更新（GPT、Claude、Gemini、Llama等）
- 开源模型进展（Hugging Face、Mistral、DeepSeek等）
- 多模态模型突破（图像、视频、音频生成）
- 模型性能评测与基准测试
- 大模型安全与对齐研究
- 算力与训练基础设施
- 模型应用落地案例

### 热点站点来源（优先搜索）

| 类型 | 来源 |
|------|------|
| **官方渠道** | OpenAI Blog、Anthropic News、Google AI Blog、DeepMind Blog |
| **技术社区** | Hugging Face Papers、Reddit r/LocalLLaMA、Reddit r/MachineLearning |
| **行业媒体** | The Verge AI、TechCrunch AI、MIT Technology Review、IEEE Spectrum |
| **中文来源** | 机器之心、量子位、AI科技评论、InfoQ AI |
| **学术动态** | arXiv cs.CL、Papers With Code、Google Scholar |

### 输出格式

```markdown
# AI 大模型热点新闻 - YYYY-MM-DD

## 1. 新闻标题
**来源**: [来源名称](链接)

**内容摘要**: 
简要内容...

**AI解读**:
技术意义、行业影响、值得关注的原因...

---

## 2. 下一条...
```

---

## 任务 2：每日AI圈热门内容

**执行时间**：每天 10:00 (Asia/Shanghai)  
**任务ID**: `87a4d701-8326-4e83-b109-2ae805213a35`  
**输出文件**: `ai-news/YYYY-MM-DD-community.md`

### 重点关注平台
1. X(Twitter)上的AI讨论热点
2. Reddit的AI相关热门帖子
3. B站AI相关热门视频/内容
4. 小红书AI相关热门笔记
5. **OpenClaw / AI Agent生态**：MCP协议动态、OpenClaw更新、Claude Code/Aider等开源Agent工具进展

### 输出格式

```markdown
# AI 圈热门内容 - YYYY-MM-DD

## 1. 内容标题
**来源**: [平台名称](链接)

**内容摘要**: 
简要内容...

**AI解读**:
为什么值得关注，有什么实用价值...

---

## 2. 下一条...
```

---

## GitHub 自动提交

两个任务执行后会自动运行：

```bash
cd /root/.openclaw/workspace && \
git add ai-news/ && \
git commit -m "Add AI news for YYYY-MM-DD" && \
git push
```

**目标仓库**: https://github.com/Oncecrazy/news

---

## 更新日志

| 日期 | 版本 | 变更内容 |
|------|------|----------|
| 2026-02-25 | v1.0 | 初始创建两个定时任务 |
| 2026-02-25 | v2.0 | 扩充9:00任务，专注AI大模型，增加热点站点来源 |

---

## 管理命令

```bash
# 查看所有定时任务
openclaw cron list

# 手动触发任务
openclaw cron run <job-id>

# 禁用/启用任务
openclaw cron update <job-id> --enabled=false
openclaw cron update <job-id> --enabled=true

# 删除任务
openclaw cron remove <job-id>
```

---

*由 OpenClaw 自动生成*

# AI 日报

每日工作日自动生成的 AI 技术日报，聚焦 LLM 推理系统与 AI Agent 前沿动态。

## 日报结构

每篇日报包含以下 6 个版块：

| # | 版块 | 说明 |
|---|------|------|
| 1 | 推理服务论文 | LLM inference serving 领域最新学术论文（标题 + 总结 + 链接） |
| 2 | KV Cache 复用论文 | KV cache reuse 领域最新学术论文（标题 + 总结 + 链接） |
| 3 | 推理 Infra 论文 | inference infrastructure / disaggregation 领域最新学术论文（标题 + 总结 + 链接） |
| 4 | 技术新闻（3篇） | 与上述论文主题相关的技术新闻、行业动态、工程博客 |
| 5 | Vibe Coding 实践 | 一条 vibe coding 最佳实践或经验技巧 |
| 6 | AI Agent 技术新闻 | AI agent 领域的最新技术新闻 |

## 论文聚焦领域

- **推理服务**：LLM 推理调度、请求批处理、SLO 保障、多轮对话服务、agentic serving
- **KV Cache 复用**：非前缀 KV cache 复用、前缀缓存、KV 压缩与拼接、RAG 场景缓存优化
- **推理基础设施**：prefill-decode 分离、attention-FFN 分离、跨引擎状态共享、分布式推理架构

## 目录结构

```
YYYY/
├── MM/
│   └── YYYY-MM-DD.html    # 每日日报（单文件 HTML 页面）
```

按 年/月/日.html 三层组织，例如 `2026/07/2026-07-31.html`。页面由 [answer-me-with-html](https://github.com/QingYunA/answer-me-with-html) 的 `am` CLI 渲染，自带样式与深色模式，单个文件即可打开，不依赖外部资源。2026-10-30 及更早的日报是纯文本 `.md`。

## 自动生成

工作日早晨 5:30 自动生成，由 AI Agent 收集 arXiv 论文和互联网技术新闻后撰写，并自动提交至本仓库。技能 `answer-me-with-html` 只在生成日报的 cron job 中加载，日常会话不触发。

## 提交规则

- **一日报一提交**：每次提交新增且仅新增一份日报，提交与日报一一对应。
- 不得在一次提交中包含多份日报，也不得分多次提交修改同一份日报。
- 如需修正已提交的日报，使用 `git commit --amend` 或 `git rebase` 合并改动，保持一日报一提交的对应关系，然后 force-push。

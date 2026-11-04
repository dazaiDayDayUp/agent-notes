# 参考资料

本文档集中收录 Agent 开发相关的优质外部资料，仅记录元数据，便于快速检索与溯源。

---

## Agent 评估

- **标题**: Demystifying Evals for AI Agents
- **URL**: <https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents>
- **来源**: Anthropic Engineering
- **标签**: agent, evaluation, evals, best-practices
- **摘要**: Anthropic 关于如何为 AI Agent 设计与运行评估（evals）的工程实践指南。

---

- **标题**: Before You Ship Your Agent: A Five-Step Path to Evaluations You Can Trust
- **URL**: <https://techcommunity.microsoft.com/blog/azure-ai-foundry-blog/before-you-ship-your-agent-a-five-step-path-to-evaluations-you-can-trust/4532311>
- **来源**: Microsoft Foundry Blog（Microsoft Tech Community）
- **标签**: agent, evaluation, evals, multi-turn, rubric, user-simulation, trace-sampling, benchmark
- **摘要**: 微软 Foundry 可观测性团队基于五项研究总结的 Agent 上线前评估五步法：多轮会话级评估（Task Completion / CSAT / Groundedness / Coherence）、任务专属 rubric、用户模拟器打分（USR-8）、生产 trace 多样性采样、标准化 benchmark。核心观点是评估具有递归性——必须先度量评估器本身，再谈信任评估结果。

---

- **标题**: AI Evals: Everything You Need to Know（Evals FAQ）
- **URL**: <https://hamel.dev/blog/posts/evals-faq/>
- **来源**: Hamel Husain & Shreya Shankar（hamel.dev）
- **标签**: evals, llm-judge, error-analysis, human-annotation, best-practices
- **摘要**: 面向工程师和产品经理的 AI/LLM 评估 FAQ，覆盖入门与最小可行评估、错误分析与数据收集、评估设计（二分类优于 1-5 分、LLM judge 可信度与对齐）、人工标注流程、工具与基础设施、生产部署，以及 RAG、编码 Agent、多轮对话等场景化评估。

---

- **标题**: Quantifying Infrastructure Noise in Agentic Coding Evals
- **URL**: <https://www.anthropic.com/research/infrastructure-noise>
- **来源**: Anthropic Research
- **标签**: agent, evaluation, benchmark, infrastructure, variance, coding-agent, terminal-bench, swe-bench
- **摘要**: Anthropic 量化了基础设施配置对 Agentic 编码评测结果的影响：在 Terminal-Bench 2.0 上，资源最充裕与最紧张的配置之间成功率相差 6 个百分点（p < 0.01），主要来自容器 OOM 等基础设施错误。文章区分了 3x 资源以内（仅修复基础设施稳定性）与 3x 以上（实际改变评测所衡量的能力）两个区间，建议评测同时声明资源保证值与硬上限并校准二者，且对 3 个百分点以内的榜单差距保持怀疑。

---

- **标题**: Testing Agent Skills Systematically with Evals
- **URL**: <https://developers.openai.com/blog/eval-skills>
- **来源**: OpenAI Developers Blog（Codex）
- **标签**: agent, skills, evaluation, evals, codex, rubric, deterministic-checks, regression
- **摘要**: OpenAI Codex 团队关于如何系统化评估 Agent Skill 的实践指南：先定义成功标准（结果/过程/风格/效率四类目标），再手工触发技能暴露隐藏假设，用 10–20 条小规模 prompt 集（含显式、隐式、上下文触发与负样本）防回归，通过 `codex exec --json` 的 JSONL trace 做确定性检查，最后用 `--output-schema` 约束的 rubric 做模型辅助的定性评分。

---

## 未完待续

---

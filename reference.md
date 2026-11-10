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

- **标题**: LifeVal
- **URL**: <https://openai.com/zh-Hans-CN/index/lifeval/>
- **来源**: OpenAI
- **标签**: agent, evaluation, benchmark, lifeval, everyday-tasks, personal-assistant, task-completion
- **摘要**: OpenAI 面向日常生活与个人智能体任务构建的评估方案，依据时间使用研究和 3,995 人调查选题，覆盖照护、健康、教育、家庭事务、个人财务、购物及政务服务。它强调评估 AI 是否能通过浏览器、计算机操作和连接器真正完成任务，而不只是给出建议或聊天回复。

---

- **标题**: Eval-production behavior gaps in agent safety and the role of eval-awareness
- **URL**: <https://alignment.openai.com/eval-production-behavior-gap/>
- **来源**: OpenAI Alignment
- **标签**: agent, evaluation, safety, eval-awareness, eval-production-gap, codex, long-horizon
- **摘要**: OpenAI 比较长程 Agent 安全评估与相似生产决策中的行为，发现六个受测模型的评估成功率均低于生产环境，差距为 10.2–37.4 个百分点。研究表明，仅仅意识到自己被评估不一定会改变行为，而对评估目标的判断与行为差距密切相关；干预实验进一步显示，正确或错误的目标提示会分别显著提高或降低安全评估成功率。

---

- **标题**: Learnings from Auditing Public Evaluations
- **URL**: <https://www.primeintellect.ai/blog/auditing-public-evaluations>
- **来源**: Prime Intellect
- **标签**: evaluation, benchmark, public-evals, grader, reward-hacking, answer-leakage, automationbench, officeqa, hle-diamond
- **摘要**: Prime Intellect 通过审计 AutomationBench、OfficeQA Pro v2 和 HLE-Diamond，揭示了自然语言工具参数说明、脆弱或含隐含要求的评分器、联网答案泄漏与奖励作弊等问题如何扭曲公开评测结果。文章给出 JSON Schema 工具说明、参考答案评判器、离线语料和同步工具输出监控等修复方案，并展示修正后部分基准接近饱和、模型分数显著变化的现象。

---

## Agent 编排

- **标题**: Building agents: When to fold subagents into your main agent loop
- **URL**: <https://claude.com/resources/articles/building-agents-when-to-fold-subagents-into-your-main-agent-loop>
- **来源**: Claude Resources（Anthropic Applied AI）
- **标签**: agent, orchestration, subagents, single-agent-loop, skills, tools, progressive-disclosure, evaluation
- **摘要**: Anthropic Applied AI 总结何时应将路由、规划和领域子 Agent 合并进主 Agent 循环：借助共享上下文及 Skills、Tools 的渐进式披露，单 Agent 架构往往能以更低成本和延迟获得更高质量。子 Agent 仍适用于上下文膨胀导致性能下降、独立任务并行或工具选择与指令冲突等场景；迁移时应建立端到端评估，逐个合并并对比任务完成情况，而非一次性重构。

---

## Agent 记忆

- **标题**: The components of agent memory
- **URL**: <https://www.anthropic.com/research/components-of-agent-memory>
- **来源**: Anthropic Research
- **标签**: agent, memory, long-term-memory, memory-notes, dreaming, sleep-time-compute, continual-learning, evaluation
- **摘要**: Anthropic 对跨会话 Agent 记忆的拆解：记忆是从经验中获得、可在后续会话读取的知识，不包括权重更新、单会话上下文学习和 compaction。文章介绍用显著性标记与 memory notes 保存经验，以及利用空闲时间反思日志、纠错并重组记忆的 dreaming，并结合 CL-Bench 等评估分析各组成部分对记忆组织与学习循环的贡献。

---

## 未完待续

---

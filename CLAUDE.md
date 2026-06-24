# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 仓库性质

这是一个 **Agent 开发面试准备知识库**，内容是 Markdown 笔记，不是可运行的代码项目。没有构建、测试或 lint 流程。所有内容用中文撰写。

## 文件组织约定

- 每个主题对应一个文件，命名格式为 `NN-topic-name.md`（两位数字编号 + 短横线连接的英文主题名），如 `01-memory-management.md`。
- 新建主题文件时，**以 `template.md` 为模板**：顶部一级标题写主题名，紧跟一句 `>` 引用概括核心内容，正文用 `## Q1：标题` / `## Q2：标题` 的问答块，每个问答含「问题描述」与「参考回答」，块之间用 `---` 分隔。
- 文件内一级标题（`#`）使用英文主题名，与文件名中的 `topic-name` 保持一致。

## 添加新主题时必须同步更新 README

`README.md` 中的「主题清单」表格是手工维护的注册表。每新增一个 `NN-topic-name.md`，都要在该表格追加一行（编号、主题、文件名），否则索引与实际文件会脱节。

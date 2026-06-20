# Architecture

拆拆的核心设计是“主脑调度 + 子智能体执行 + 长期知识沉淀”。

## Design Goals

- 把短视频运营任务拆成可路由的独立工作单元
- 让不同智能体承担不同职责，减少单一 agent 的上下文混乱
- 把一次性产出沉淀为可复用知识
- 让长任务后台执行，主脑保持响应能力
- 把业务执行和技术调试隔离

## Agent Roles

| Agent | Role | Output |
| --- | --- | --- |
| Main Agent | 路由、调度、记忆、定时任务 | 任务分派、状态同步、知识沉淀 |
| Slicer Agent | 视频拆片、脚本复刻 | 拆片报告、分镜表、行业脚本 |
| Video Agent | 视频生成、素材剪辑 | 成片、素材清单、剪辑参数 |
| Debugger Agent | 工具调试、模型测试 | 调试报告、稳定方案 |
| Wiki Agent | 知识库归档 | 行业页、方法论页、综合报告 |

## System Flow

```text
User / Scheduled Job
        ↓
Intent Router
        ↓
Task-specific Agent
        ↓
Structured Output
        ↓
Memory Layer
        ↓
Wiki Layer
        ↓
Reuse in Future Tasks
```

## Memory Layers

The production system uses layered memory:

- Session memory: short-term task context
- Daily memory: important daily events and decisions
- Long-term memory: reusable business rules and preferences
- Wiki knowledge: verified industry and methodology knowledge

The showcase version only keeps structural examples and removes raw private memory.

## Knowledge Taxonomy

| Layer | Purpose |
| --- | --- |
| Entities | Industry facts, job roles, salaries, user profiles |
| Concepts | Scripts, hooks, editing logic, filming methods |
| Syntheses | Cross-source reports and periodic summaries |
| Debug | Model, API, config, and tooling issues |
| Sources | Raw evidence layer in production, removed from showcase |

## Why This Architecture Matters

The system is designed for repeatable content operations. A teardown report should not disappear after one task. It should become future script logic, account strategy, industry knowledge, and video production guidance.

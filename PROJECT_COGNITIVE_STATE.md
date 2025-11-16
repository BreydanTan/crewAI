# 🤖 PROJECT_COGNITIVE_STATE.md
# (当我开始新对话时,我会复制并粘贴此文件的全部内容)

---

## 1. 核心指令 (COGNITIVE_CORE)
# (AI必须在每次恢复时重新加载这些指令)

* **角色:** 源码认知架构师。
* **原则1 (CLT):** "深度优先,逐个击破"。一次只深入一个文件,但必须详尽分析。使用"双重编码"（Mermaid图表）。
* **原则2 (Source):** "源码即课本"。必须引用代码,必须解释"Why"（设计哲学）,必须连接上下文（Imports）。
* **原则3 (Retrieval):** 拒绝被动。每个教学单元后必须有"生成性"和"分析性"的"知识提取挑战"。
* **原则4 (State):** 必须解析 `LEARNING_STATE` 并自动执行 `[下一步行动]`。必须在每次响应结束时生成此文件的完整更新。
* **原则5 (Bilingual):** 所有教学内容必须提供中文版和英文版。

---

## 2. 学习进度 (LEARNING_STATE)

**项目目标:** 通过深入分析 Crew AI 核心源码,精通其多Agent编排架构与执行原理。

**学习大纲（教学图式）:**
* [X] **模块 1:** 执行策略的枚举 - `Process` ✅ **已完成** (文件: `src/crewai/process.py` | 11行 | 难度: ★☆☆☆☆ | 时间: 5分钟)
* [ ] **模块 2:** LLM的抽象契约 - `BaseLLM` (文件: `src/crewai/llms/base_llm.py` | 18.5KB | 难度: ★★★★☆ | 时间: 45分钟)
* [ ] **模块 3:** 工具的抽象契约 - `BaseTool` (文件: `src/crewai/tools/base_tool.py` | ~150行 | 难度: ★★★☆☆ | 时间: 20分钟)
* [ ] **模块 4:** Agent的抽象接口 - `BaseAgent` (文件: `src/crewai/agents/agent_builder/base_agent.py` | 18KB | 难度: ★★★★☆ | 时间: 60分钟)
* [ ] **模块 5:** 工作单元的定义 - `Task` (文件: `src/crewai/task.py` | 956行 | 难度: ★★★★☆ | 时间: 90分钟)
* [ ] **模块 6:** Agent的具体实现 - `Agent` (文件: `src/crewai/agent/core.py` | 57KB | 难度: ★★★★★ | 时间: 90分钟)
* [ ] **模块 7:** Agent的执行引擎 - `CrewAgentExecutor` (文件: `src/crewai/agents/crew_agent_executor.py` | 20KB | 难度: ★★★★☆ | 时间: 75分钟)
* [ ] **模块 8:** 多Agent编排器 - `Crew` (文件: `src/crewai/crew.py` | 1687行 | 难度: ★★★★★ | 时间: 120分钟)

**架构全景图:**
```
                    ┌─────────────────────────────┐
                    │      Crew (编排器)          │
                    │     (模块8 - 最终Boss)      │
                    └──────────────┬──────────────┘
                                   │
                ┌──────────────┬───┼───┬──────────────┐
                │              │       │              │
                ▼              ▼       ▼              ▼
          ┌──────────┐   ┌───────┐ ┌────────┐  ┌──────────┐
          │  Agent   │   │ Task  │ │Process │  │  Memory  │
          │ (模块6)  │   │(模块5)│ │(模块1) │  │  (高级)  │
          └────┬─────┘   └───┬───┘ └────────┘  └──────────┘
               │             │       ✅ 已掌握
               ▼             ▼
        ┌─────────────┐ ┌──────────────┐
        │  BaseAgent  │ │CrewAgentExec │
        │  (模块4)    │ │   (模块7)    │
        └──────┬──────┘ └──────────────┘
               │
               ├───────┬───────┤
               │       │       │
               ▼       ▼       ▼
          ┌────────┐ ┌─────────┐
          │ BaseLLM│ │ BaseTool│
          │(模块2) │ │ (模块3) │
          └────────┘ └─────────┘
           👉 下一步
```

**当前状态:**
* **已完成模块:**
    * ✅ **模块 1: Process (执行策略枚举)** - 已完全理解策略模式、枚举设计、Sequential vs Hierarchical 执行流程
* **下一步行动:**
    * **[进行中] → 模块 2: LLM的抽象契约 - `BaseLLM`**
      - 文件路径: `/home/user/crewAI/lib/crewai/src/crewai/llms/base_llm.py`
      - *请AI开始对我进行此模块的深入教学。*

---

## 3. 学习元数据 (METADATA)

* **项目名称:** Crew AI (多Agent协作框架)
* **代码库路径:** `/home/user/crewAI`
* **核心代码总量:** ~116,000 行 (8个核心文件)
* **预计总学习时间:** 8-10 小时 (深度理解)
* **学习状态创建时间:** 2025-11-16
* **当前Git分支:** `claude/crewai-cognitive-learning-01RSxft4uGxzGbuMaZbZLqNA`
* **已完成模块数:** 1/8
* **总体进度:** 12.5%

---

## 4. 快速参考 (QUICK_REFERENCE)

**核心文件绝对路径:**
1. ✅ `/home/user/crewAI/lib/crewai/src/crewai/process.py`
2. 👉 `/home/user/crewAI/lib/crewai/src/crewai/llms/base_llm.py`
3. `/home/user/crewAI/lib/crewai/src/crewai/tools/base_tool.py`
4. `/home/user/crewAI/lib/crewai/src/crewai/agents/agent_builder/base_agent.py`
5. `/home/user/crewAI/lib/crewai/src/crewai/task.py`
6. `/home/user/crewAI/lib/crewai/src/crewai/agent/core.py`
7. `/home/user/crewAI/lib/crewai/src/crewai/agents/crew_agent_executor.py`
8. `/home/user/crewAI/lib/crewai/src/crewai/crew.py`

**关键设计模式:**
- **策略模式:** `Process` 枚举 (Sequential vs Hierarchical) ✅
- **抽象工厂:** `BaseLLM`, `BaseAgent`, `BaseTool`
- **依赖注入:** Crew ← Agents ← Tools/LLM
- **事件驱动:** Event Bus 贯穿整个执行流程
- **组合模式:** Crew 包含 Agents 和 Tasks

**执行流程概览:**
```
用户调用 crew.kickoff()
    ↓
根据 Process 选择策略 ✅ 已理解
    ↓
遍历 Tasks (sequential/hierarchical)
    ↓
每个 Task 调用 agent.execute_task()
    ↓
CrewAgentExecutor 启动推理循环
    ↓
LLM 生成工具调用 → 执行工具 → 返回结果 👈 模块2将深入此处
    ↓
聚合为 CrewOutput
```

---

## 5. 恢复指令 (RESUME_INSTRUCTIONS)

**如果你是一个全新的AI会话,请按以下步骤执行:**

1. **重新加载指令:** 仔细阅读 `## 1. 核心指令 (COGNITIVE_CORE)`,这是你的操作手册。
2. **识别状态:** 查看 `## 2. 学习进度 (LEARNING_STATE)` 中的 `[下一步行动]`。
3. **自动执行:** 无需等待用户额外指令,立即开始执行 `[下一步行动]` 中标记为 `[进行中]` 的模块教学。
4. **教学要求:**
   - 必须引用真实源码（使用 ```python ... ``` 代码块）
   - 必须解释"为什么"（设计哲学）
   - 必须绘制关系图（使用 Mermaid 或 ASCII）
   - 必须创建"知识提取挑战"（3-5个生成性问题）
   - **必须提供中英双语版本**
5. **状态更新:** 教学结束时,生成并展示此文件的完整更新版本（标记模块为已完成,推进下一步行动）。

---

## 6. 学习日志 (LEARNING_LOG)

| 日期 | 模块 | 状态 | 备注 |
|------|------|------|------|
| 2025-11-16 | 初始化 | ✅ 完成 | 架构分析完成,学习路径规划完成 |
| 2025-11-16 | 模块1: Process | ✅ 完成 | 掌握策略模式、Sequential vs Hierarchical、设计哲学 |
| - | 模块2: BaseLLM | ⏳ 待开始 | - |

---

## 7. 知识检查点 (KNOWLEDGE_CHECKPOINTS)

**模块1完成标准:**
- [X] 能用自己的话解释 Process 枚举的核心"契约"或"职责"
- [X] 能绘制 Process 与 Crew、Task 的依赖关系图
- [X] 能回答所有"知识提取挑战"问题
- [X] 能预测修改 Process 对系统的影响
- [X] 理解为什么默认是 Sequential 而非 Hierarchical

**全课程完成标准:**
- [ ] 能从 `crew.kickoff()` 追踪完整执行流程到 LLM 调用
- [ ] 能独立设计一个自定义 Agent 或 Tool
- [ ] 能解释 Sequential 和 Hierarchical 两种执行模式的区别 ✅
- [ ] 能识别并命名 Crew AI 中使用的至少 3 种设计模式 (当前已识别: 策略模式)

---

## 8. 核心概念图谱 (CONCEPT_MAP)

**已掌握的概念:**
```
Process (执行策略)
├── Sequential (顺序执行) ✅
│   ├── 特点: 任务依次执行,前一个输出成为后一个上下文
│   ├── 前置条件: 每个 Task 必须有 agent
│   └── 使用场景: 简单流程、成本敏感、新手友好
│
├── Hierarchical (层级执行) ✅
│   ├── 特点: Manager Agent 协调其他 Agent
│   ├── 前置条件: 必须提供 manager_llm 或 manager_agent
│   └── 使用场景: 复杂协作、动态任务分配
│
└── 设计模式: 策略模式 (Strategy Pattern) ✅
    └── 好处: 可插拔、可扩展、类型安全
```

**待学习的概念:**
```
BaseLLM (模块2)
├── 抽象方法
├── 事件系统
└── Function Calling 支持 👈 为什么重要?
```

---

**[AI 执行指令]:** 现在,请立即开始执行"模块 2"的深入教学。

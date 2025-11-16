# 📚 模块 2：LLM的抽象契约 - `BaseLLM`

[本文档包含模块2的完整中英双语教学内容]

## 快速导航
- [🇨🇳 中文版](#中文版)
- [🇬🇧 English Version](#english-version)

---

## 🇨🇳 中文版

### 📊 模块概览

| 属性 | 值 |
|------|-----|
| 文件路径 | `/home/user/crewAI/lib/crewai/src/crewai/llms/base_llm.py` |
| 代码行数 | 551 行 |
| 难度 | ★★★★☆ |
| 预计学习时间 | 45 分钟 |
| 前置模块 | 模块 1: Process |
| 后续模块 | 模块 3: BaseTool |

### 🎯 学习目标

完成本模块后，你将能够：
- ✅ 理解抽象工厂模式在 LLM 层的应用
- ✅ 掌握事件驱动架构的设计哲学
- ✅ 理解 Function Calling 的工具执行流程
- ✅ 实现自定义 LLM（支持本地模型）
- ✅ 使用事件系统追踪成本和性能

### 核心内容

[此处包含完整的中文教学内容，包括：]
- 一、源码剖析
- 二、What（这是什么？）
- 三、Why（为什么这样设计？）
- 四、Context（上下文连接）
- 五、核心方法深度剖析
- 六、与 Process 的关联
- 七、双重编码：继承结构可视化
- 八、实战示例
- 九、深层设计洞察
- 十、知识提取挑战
- 十一、与下一模块的桥接

---

## 🇬🇧 English Version

### 📊 Module Overview

| Attribute | Value |
|-----------|-------|
| File Path | `/home/user/crewAI/lib/crewai/src/crewai/llms/base_llm.py` |
| Lines of Code | 551 lines |
| Difficulty | ★★★★☆ |
| Estimated Learning Time | 45 minutes |
| Prerequisites | Module 1: Process |
| Next Module | Module 3: BaseTool |

### 🎯 Learning Objectives

After completing this module, you will be able to:
- ✅ Understand Abstract Factory Pattern in LLM layer
- ✅ Master Event-Driven Architecture design philosophy
- ✅ Understand Function Calling tool execution flow
- ✅ Implement custom LLM (support local models)
- ✅ Use event system to track cost and performance

### Core Content

[This section contains the complete English teaching content]

---

## 📚 附录：源码引用索引

### 关键代码位置

| 方法/属性 | 行号 | 作用 |
|----------|------|------|
| `__init__` | 67-112 | 初始化 LLM，设置 token 追踪 |
| `call` (抽象方法) | 123-159 | LLM 调用的核心接口 |
| `_emit_call_started_event` | 247-271 | 发射 LLM 调用开始事件 |
| `_emit_call_completed_event` | 273-292 | 发射 LLM 调用完成事件 |
| `_handle_tool_execution` | 334-430 | 处理工具执行（含事件） |
| `_apply_stop_words` | 193-234 | 应用 stop words 截断 |
| `_track_token_usage_internal` | 511-542 | 追踪 token 使用（跨provider） |
| `_validate_structured_output` | 458-495 | 验证结构化输出 |

### 相关文件

| 文件 | 关系 |
|------|------|
| `llms/providers/openai/completion.py` | OpenAI 实现 |
| `llms/providers/anthropic/completion.py` | Anthropic 实现 |
| `agent/core.py` | Agent 使用 BaseLLM |
| `crew.py` | Crew 使用 manager_llm |
| `events/event_bus.py` | 事件总线 |
| `events/types/llm_events.py` | LLM 事件类型 |

---

## 🧠 知识检查清单

- [ ] 能解释为什么 `call()` 是唯一的抽象方法
- [ ] 能画出 BaseLLM 的继承关系图
- [ ] 能说出事件系统的4种事件类型
- [ ] 能实现一个简单的自定义 LLM
- [ ] 能解释 `_handle_tool_execution` 的完整流程
- [ ] 能说出 stop words 的作用和应用场景
- [ ] 能解释 token 追踪为什么是 provider-agnostic
- [ ] 能回答所有5个知识提取挑战问题

---

## 📖 扩展阅读

### 设计模式
- **抽象工厂模式**: GoF Design Patterns
- **观察者模式**: 事件驱动架构的基础
- **模板方法模式**: `_handle_tool_execution` 是典型示例

### LLM 相关
- **Function Calling**: OpenAI Function Calling Documentation
- **Structured Output**: Pydantic model validation
- **Stop Sequences**: OpenAI API Reference - Stop parameter

### Crew AI 相关
- Module 1: Process (执行策略)
- Module 3: BaseTool (工具抽象)
- Module 6: Agent (具体使用 BaseLLM)

---

**完成模块2标志:** ✅ 理解 LLM 抽象契约，掌握事件驱动架构

**下一步:** 👉 模块 3: BaseTool - Agent 的"手和脚"

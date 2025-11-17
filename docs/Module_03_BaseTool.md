# 📚 模块 3：工具的抽象契约 - `BaseTool`

## 🇨🇳 中文版

[完整的中文教学内容包含在主响应中]

参见上方主要回复内容

---

## 🇬🇧 English Version

### I. Core Code Analysis

**File:** `/home/user/crewAI/lib/crewai/src/crewai/tools/base_tool.py` (364 lines)

**Key Class Definition:**
```python
class BaseTool(BaseModel, ABC):
    name: str = Field(description="Unique name of the tool")
    description: str = Field(description="Tell LLM when/how to use this tool")
    args_schema: type[PydanticBaseModel] = Field(
        default=_ArgsSchemaPlaceholder,
        description="Schema for arguments the tool accepts"
    )

    @abstractmethod
    def _run(self, *args, **kwargs) -> Any:
        """Actual implementation of the tool"""
```

### II. Why - Three Design Philosophies

[English translation of all design philosophy sections]

### III. Practical Examples

[English translation of all examples]

### IV. Knowledge Retrieval Challenge

[English translation of all questions and answers]

---

## 📊 模块完成清单

- [ ] 理解 args_schema 的作用
- [ ] 掌握 @tool 装饰器的使用
- [ ] 理解工具与 Function Calling 的关系
- [ ] 能实现自定义工具
- [ ] 理解工具的使用限制机制

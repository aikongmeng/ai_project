# Qoder Agent SDK 使用指南 


官方文档：https://docs.qoder.com/zh/cli/sdk/overview

## 一、先理解架构

```
你的应用 (TypeScript / Python)
        │  Qoder Agent SDK：任务、选项、事件、控制指令
        ▼
     qodercli（Agent 运行时：任务规划、模型通信、执行工具）
        ├── Qoder 模型服务
        └── 文件、命令、MCP 工具、子 Agent
```

要点：**SDK 是面向应用的接口，Qoder CLI 是运行时**。正式发布的 SDK 包已内置兼容的 `qodercli`，一般不用单独装；若你想自己管理运行时，可以指定 `qodercli` 可执行文件路径。

## 二、选择并安装

| | TypeScript | Python |
|---|---|---|
| 包名 | `@qoder-ai/qoder-agent-sdk` | `qoder-agent-sdk` |
| 环境 | Node.js 18+ | Python 3.10+ |
| 一次性任务 | `query()` | `query()` |
| 多轮会话 | 向 `query()` 传入异步消息流 | `QoderSDKClient` |

```bash
npm install @qoder-ai/qoder-agent-sdk
# 或
pip install qoder-agent-sdk
```

## 三、集成的四个步骤

**1. 描述任务** —— 发送提示词，按需设置工作目录、模型、系统提示词、轮次上限。

**2. 划定边界** —— 选定可用工具（工具白名单）和权限模式；需要应用侧批准的操作，通过**审批回调**交给你的应用决定。

**3. 消费消息流** —— 处理模型回复、工具活动、进度事件，以及最终的 `result` 消息。

**4. 按需控制会话** —— 长期运行的集成可以追加消息、中断执行、调整部分运行时设置、查询会话状态。

## 四、两种调用形态

**一次性任务**：直接给 `query()` 传字符串。

```ts
import { query } from '@qoder-ai/qoder-agent-sdk';

const stream = query({
  prompt: '给 src/utils.ts 补上单元测试',
  cwd: '/path/to/repo',
  // 可选：model、systemPrompt、maxTurns、工具白名单、权限模式、审批回调
});

for await (const msg of stream) {
  if (msg.type === 'result') console.log(msg);
}
```

```python
from qoder_agent_sdk import query

stream = query(prompt="汇总本周三个系统的数据生成周报", cwd="/path/to/work")
for msg in stream:
    ...
```

**多轮会话**（下一轮输入依赖上一轮输出）：
- TypeScript：向 `query()` 传入异步消息流
- Python：使用 `QoderSDKClient`

> 以上为基于文档描述的代码示意，具体字段请以文档「快速开始」中的完整可运行示例为准。

## 五、可配置能力一览

- **输入输出**：一次性/多轮输入、图片输入、结构化消息、增量流式事件
- **工具**：内置文件与命令工具、自定义工具、外部或进程内 MCP 服务
- **Agent 行为**：系统提示词与输出风格、模型、Skills、插件、可复用 Agent 定义、子 Agent
- **安全与控制**：工具白名单、权限模式、审批回调、Hooks、中断、轮次上限
- **代码安全**：对 Agent 自身改动的静态检查、仓库级轻量扫描与深度扫描
- **记忆**：用户级/项目级原生记忆，或由应用接管（**仅 TypeScript**）
- **会话管理**：工作目录、持久会话、恢复与派生、检查点、外部会话存储、用量与上下文信息
- **任务执行**：后台任务、任务列表与取消、单任务中断

## 六、执行边界（务必留意）

- SDK 与 Qoder CLI 默认走**本地通道**，但 CLI 需要访问 Qoder 模型服务，**提示词和推理所需上下文会发送到该服务**。
- 文件写入和命令执行都发生在 **Qoder CLI 所在的环境**里，`cwd` 要明确设置，可执行动作用权限收紧。
- 模型不直接读写文件或执行命令，只发出工具调用请求，由 CLI 按策略校验后执行。
- **跳过权限校验的模式，只适用于已有外部隔离手段的环境**（如 CI 容器、沙箱）。

---

想深入的话，可以按需看文档的「工作原理」（启动过程、通信协议、Agent 循环）、「快速开始」（两种语言的可运行示例）和「SDK 参考」（TS/Python 概念对照、语言差异）。

有具体的应用场景（比如做 IDE 插件、CI 集成、还是内部办公 Agent），我可以帮你把集成代码的结构设计出来。

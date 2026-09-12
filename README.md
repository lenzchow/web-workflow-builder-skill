# Web Workflow Builder Prompt

一套用于 AI 网页设计与开发的可复用 Prompt。

这套 Prompt 将网页开发拆成两层：

- **设计工作流层**：沉淀视觉语言、布局原则、交互模式和数据展示方法。
- **项目实现层**：根据当前项目的技术架构，通过代码实现渲染能力，并使用 Markdown 管理当前页面内容和配置。

使用时先由 Skill 根据页面需求选择风格 Prompt，再读取对应的设计模板生成网页。风格 Prompt 复用设计思路，页面 Markdown 根据本次业务目标变化，程序代码提供当前项目所需的实现能力。

它解决的问题是：避免每次生成网页都从零开始，也避免把某个项目的固定页面结构、框架或组件库误认为通用规范。

## 文件说明

| 文件 | 用途 |
| --- | --- |
| `prompts/markdown-driven-web-prompt.md` | 将网页内容、结构和可配置表现交给 Markdown 管理的开发规范 |
| `prompts/markdown-web-builder-skill-prompt.md` | 将上述工作流整理为可重复使用 Agent Skill 的创建规范 |

后续可以继续增加不同风格的 Prompt，例如 `trading-style-web-prompt`、`editorial-style-web-prompt` 或 `saas-style-web-prompt`。Skill 根据用户需求选择风格，而不是固定使用单一模板。

## 使用方式

1. 先建立或维护一个风格 Prompt，沉淀网页设计、架构和 UI 思路。
2. 生成网页时调用 Skill，由 Skill 根据需求选择风格 Prompt。
3. 新网页需要在建立代码的同时建立页面 Markdown。
4. 复用已有架构时，可以复用并调整当前项目的 Markdown。
5. 每个新项目先识别自身的框架、构建工具和组件库，再选择对应的渲染实现。
6. 设计规范跨项目复用，页面 Markdown 根据当前业务目标自由变化。

## 核心原则

> 代码定义可用能力，Markdown 配置当前页面；设计思路可以复用，具体页面不能写死。

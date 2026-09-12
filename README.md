# Web Workflow Builder Prompt

一套用于 AI 网页设计与开发的可复用 Prompt。

这套 Prompt 将网页开发拆成两层：

- **设计工作流层**：沉淀视觉语言、布局原则、交互模式和数据展示方法。
- **项目实现层**：根据当前项目的技术架构，通过代码实现渲染能力，并使用 Markdown 管理当前页面内容和配置。

它解决的问题是：避免每次生成网页都从零开始，也避免把某个项目的固定页面结构、框架或组件库误认为通用规范。

## 文件说明

| 文件 | 用途 |
| --- | --- |
| `prompts/markdown-driven-web-prompt.md` | 将网页内容、结构和可配置表现交给 Markdown 管理的开发规范 |
| `prompts/markdown-web-builder-skill-prompt.md` | 将上述工作流整理为可重复使用 Agent Skill 的创建规范 |

## 使用方式

1. 新建网页前，先使用第一个 Prompt 明确代码与 Markdown 的职责。
2. 需要把工作流封装成 Agent Skill 时，再使用第二个 Prompt。
3. 每个新项目先识别自身的框架、构建工具和组件库，再选择对应的渲染实现。
4. 设计规范跨项目复用，页面 Markdown 根据当前业务目标自由变化。

## 核心原则

> 代码定义可用能力，Markdown 配置当前页面；设计思路可以复用，具体页面不能写死。


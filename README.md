# Web Workflow Builder Prompt

一套用于 AI 网页设计与开发的可复用 Prompt 和风格模板资源。

这套 Prompt 将网页开发拆成四个角色：

- **Skill**：根据页面需求与用户确认结果选择风格 Prompt，并组织生成流程。
- **Web Prompt**：保存可复用的页面设计、架构和 UI 风格，位于 Skill 的 `references/web-prompts/`。
- **页面 Markdown**：生成在目标项目中，用于保存当前页面内容和配置，方便后续微调。
- **程序代码**：生成在目标项目中，根据项目技术架构实现渲染能力、业务逻辑和交互。

使用时先调用 Skill，与用户确认页面风格，再选择对应的 web-prompt。Skill 读取风格模板后，在目标项目中同时生成或调整程序代码和页面 Markdown。

它解决的问题是：避免每次生成网页都从零开始，也避免把某个项目的固定页面结构、框架或组件库误认为通用规范。

## 文件说明

| 文件 | 用途 |
| --- | --- |
| `prompts/markdown-driven-web-prompt.md` | 代码、web-prompt 与页面 Markdown 协同工作的网页开发规范 |
| `prompts/markdown-web-builder-skill-prompt.md` | 将上述流程整理为可重复使用 Agent Skill 的创建规范 |
| `references/web-prompts/` | 可选择的页面风格 Prompt 模板 |
| `references/markdown-spec.md` | 页面 Markdown 使用边界和语法规范 |
| `references/workflow.md` | Skill 生成网页的执行流程 |
| `references/self-checklist.md` | 页面生成后的自检清单 |
| `scripts/README.md` | 说明实际 Skill 脚本与目标项目文件的边界 |

后续可以继续增加不同风格的 web-prompt，例如 `trading-style-web-prompt`、`editorial-style-web-prompt` 或 `saas-style-web-prompt`。这些风格模板属于 Skill 的资源，不是目标项目生成的页面文件。

## 使用方式

1. 在 Skill 的 `references/web-prompts/` 中建立或维护风格 Prompt。
2. 生成网页时调用 Skill，由 Skill 与用户确认风格并选择对应模板。
3. 新网页需要在目标项目中同时建立代码和页面 Markdown。
4. 复用已有架构时，优先复用并调整目标项目已有的代码和 Markdown。
5. 每个项目先识别自身的框架、构建工具和组件库，再选择对应的渲染实现。
6. 风格 Prompt 跨项目复用，页面 Markdown 和程序代码只属于目标项目。

## 核心原则

> 代码定义可用能力，Markdown 配置当前页面；设计思路可以复用，具体页面不能写死。

# F-design

[![Release](https://img.shields.io/github/v/release/yeyuancc0-glitch/f-design)](https://github.com/yeyuancc0-glitch/f-design/releases)
[![License](https://img.shields.io/github/license/yeyuancc0-glitch/f-design)](LICENSE)

整合多个设计规范和设计类 Skill，开发者只需安装这一个 Skill，即可覆盖需求分析、UI/UX、响应式布局、动效、无障碍与浏览器验收。

F-design 不是 Codex 专属扩展。它采用开放的 [Agent Skills](https://agentskills.io/) 目录结构，以 `SKILL.md` 为入口，并将完整规范拆分到 `references/` 中。任何能够发现并加载 Agent Skills 的 AI 编程工具，都可以按照自身的 Skill 目录规则安装使用。

## 适合什么工作

- 从零规划、设计并实现网站、Web App、产品页或交互原型
- 根据参考图还原页面结构、图片关系、响应式构图和动效
- 优化已经写好的网页，而不只是重新生成一套代码
- 建立页面与状态清单、视觉系统、色彩角色和组件状态
- 为桌面端和移动端分别审查构图，同时保持内容与功能一致
- 评估成熟的 GitHub 开源组件，并适配当前项目风格
- 补齐图片过渡、交互动效、降级策略和性能检查
- 执行无障碍、溢出、遮挡、首屏任务和真实浏览器验收

## 核心原则

- **先问再分析：** 重要设计任务先进行简短的引导式提问；每个方向题都允许自由填写，并单独询问额外要求。
- **不依赖其他设计 Skill：** F-design 的设计、组件、响应式、色彩、图片、动效和质量规范均已包含在本仓库中。
- **移动端不是缩小版：** 移动端需要重新排序、收纳和定位内容，并单独检查首屏、触控、键盘和安全区域。
- **图片属于构图：** 图片的主体、裁切、焦点、边缘、层级和过渡需要与页面结构一起设计。
- **动效必须交付：** 动效需要有明确目的、触发条件、终止状态、性能策略和 `prefers-reduced-motion` 结果。
- **组件选择有证据：** 优先复用项目现有组件；需要外部组件时检查维护状态、许可证、无障碍、兼容性和主题适配能力。
- **卡片必须有理由：** 不把仪表盘卡片布局当作默认答案，不嵌套卡片，优先使用直接布局、列表、分隔线和内容区带。
- **浏览器结果才算完成：** 构建和静态检查不能替代真实页面、关键交互与多视口截图验证。

## 兼容的宿主

F-design 的必要入口是根目录下的 `SKILL.md`。`references/` 是执行时按需读取的规范，`agents/openai.yaml` 是 OpenAI/Codex 的增强元数据；不识别该文件的宿主可以忽略它。

| 宿主 | 用户级安装位置或方式 | 项目级安装位置 |
|---|---|---|
| Codex | `~/.agents/skills/f-design` | 使用当前 Codex 安装所发现的项目 Skill 目录 |
| [Claude Code](https://code.claude.com/docs/en/skills) | `~/.claude/skills/f-design` | `.claude/skills/f-design` |
| [Qoder CLI](https://docs.qoder.com/cli/Skills) | `~/.qoder/skills/f-design` | `.qoder/skills/f-design` |
| [QoderWork](https://docs.qoder.com/qoderwork/skills) | `~/.qoderwork/skills/f-design`，也可以在对话中粘贴仓库地址让其安装 | 通过当前版本的 Skill 管理界面配置 |
| [VS Code / GitHub Copilot](https://code.visualstudio.com/docs/agent-customization/agent-skills) | `~/.agents/skills/f-design` 或 `~/.copilot/skills/f-design` | `.github/skills/f-design`、`.agents/skills/f-design` |
| 其他 Agent Skills 兼容工具 | 将完整仓库放进该工具文档指定的个人 Skills 目录 | 将完整仓库放进该工具文档指定的项目 Skills 目录 |

不同工具的目录、刷新命令和显式调用语法可能随版本变化，请以对应宿主的当前官方文档为准。F-design 会使用宿主已有的文件、终端、浏览器、图像生成或联网工具；宿主未提供某项能力时，代理应明确报告限制，而不是假装完成。

## 安装

### 通用方式

将仓库克隆为 Skill 目录中的一个完整 `f-design` 文件夹：

```bash
git clone https://github.com/yeyuancc0-glitch/f-design.git <你的-Skills-目录>/f-design
```

不要只下载 `SKILL.md`。完整工作流还会读取 `references/` 中的文件，因此必须保留整个目录结构。

### Codex

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/yeyuancc0-glitch/f-design.git ~/.agents/skills/f-design
```

安装后刷新或重新启动 Codex。如果当前版本显示了不同的个人 Skill 根目录，以实际发现路径为准。

### Claude Code

个人使用：

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/yeyuancc0-glitch/f-design.git ~/.claude/skills/f-design
```

随 Git 项目共享：

```bash
git submodule add https://github.com/yeyuancc0-glitch/f-design.git .claude/skills/f-design
```

不使用 Git submodule 时，也可以下载完整仓库并将其内容复制到 `.claude/skills/f-design`。

Claude Code 可以根据任务描述自动加载，也可以输入 `/f-design` 显式调用。Claude Code 会监测已存在的 Skill 目录变化；如果是在会话启动后首次创建顶层 Skills 目录，重新启动一次 Claude Code。

### Qoder CLI

```bash
mkdir -p ~/.qoder/skills
git clone https://github.com/yeyuancc0-glitch/f-design.git ~/.qoder/skills/f-design
```

已有会话可执行 `/skills reload`，再通过 `/skills` 检查是否成功发现。

### QoderWork

可以直接在对话中发送：

```text
请从 https://github.com/yeyuancc0-glitch/f-design 下载完整 Skill，并安装到 ~/.qoderwork/skills/f-design
```

也可以使用 Skill 管理页面上传或安装。上传时要包含 `SKILL.md`、`references/` 和其他支持文件。

### VS Code / GitHub Copilot

个人使用：

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/yeyuancc0-glitch/f-design.git ~/.agents/skills/f-design
```

随 Git 项目共享：

```bash
git submodule add https://github.com/yeyuancc0-glitch/f-design.git .github/skills/f-design
```

不使用 Git submodule 时，也可以下载完整仓库并将其内容复制到 `.github/skills/f-design` 或 `.agents/skills/f-design`。

## 如何调用

多数兼容宿主可以根据任务描述自动匹配 Skill。也可以直接在提示词中指定：

```text
使用 F-design，为这个项目设计并实现一个响应式官网首页。
```

```text
使用 F-design 审查当前网页，优化布局、排版、移动端、图片过渡和动效，并在浏览器中验证。
```

Claude Code、Qoder 等支持 Skill 快捷调用的宿主可以使用：

```text
/f-design 优化当前产品的登录与注册流程
```

Codex 中也可以使用：

```text
$f-design 根据这组参考图实现桌面端和移动端页面
```

对于较完整的新建或改版任务，F-design 通常会先询问产品目标、视觉方向、配色、图片、动效和额外要求，再开始实质分析与实现。用户也可以明确回复“你决定”，让代理记录假设后继续执行。

## 工作流程

1. 读取项目事实、现有规范、组件、资源和运行方式。
2. 补齐未明确的产品、风格、色彩、图片、动效和额外需求。
3. 建立产品简报、页面与状态清单，以及桌面/移动端共享的内容基线。
4. 确定视觉系统、色彩角色、组件状态、图片语言和响应式规则。
5. 评估项目现有组件与必要的成熟开源组件。
6. 分阶段实现结构、系统、组件、媒体、响应式和无障碍。
7. 在真实浏览器中审查功能、布局和多视口结果。
8. 实现并验证交互动效、参考图过渡和 reduced-motion 降级。
9. 完成构建、测试、截图对比和交付说明。

F-design 对每个阶段保留执行状态，避免把“写进规范”误当成“已经实现”。

## 优化已有网页

F-design 不只用于从零生成页面。面对已经存在的界面时，它会：

1. 启动真实项目并记录桌面、平板和手机基线。
2. 区分信息架构、层级、布局、排版、色彩、组件、移动端、无障碍、动效和性能问题。
3. 优先修复任务阻塞、遮挡溢出、移动端首屏和无障碍缺陷。
4. 在保留项目身份与功能的前提下做针对性修改。
5. 使用相同视口比较修改前后结果，并重新走关键交互。

## 目录结构

```text
f-design/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── discovery-and-architecture.md
    ├── design-reference-synthesis.md
    ├── visual-system.md
    ├── color-system-and-states.md
    ├── responsive-mobile.md
    ├── open-source-components.md
    ├── media-and-image-transitions.md
    ├── motion-and-interaction.md
    ├── existing-surface-optimization.md
    ├── evidence-and-execution.md
    ├── implementation.md
    ├── reference-images.md
    └── quality-gates.md
```

## 更新

进入实际安装目录执行：

```bash
git pull --ff-only
```

更新后按照宿主规则刷新 Skills 或新建会话。

## 兼容性说明

- F-design 不绑定 React、Vue、Svelte、Next.js 或特定 CSS 方案，会优先沿用当前项目技术栈。
- Skill 不自带浏览器、图像生成器或动画运行库，而是调用宿主和项目已有能力。
- `SKILL.md` 的 `name` 与目录名必须保持为 `f-design`，否则部分宿主可能无法发现。
- 安装第三方 Skill 前应先审查其内容与权限。本仓库不包含自动执行脚本或预设密钥。

## 许可证与来源

F-design 使用 [Apache License 2.0](LICENSE) 发布。

本项目是对公开设计工程资料的独立整合与再组织。第三方项目、许可证及致谢见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。这些来源不是运行时依赖，用户无需额外安装。

## English

F-design is a self-contained frontend product design and delivery skill built on the open Agent Skills structure. It is not limited to Codex: any compatible host that can discover a `SKILL.md` folder and load its referenced files can use it. The workflow covers discovery, UI/UX, responsive composition, component research, imagery, motion, accessibility, existing-interface optimization, and browser QA.

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
- 从产品真实材料、语言和场景中建立视觉身份，并用“表现力、信息密度、动效能量”三项刻度控制方向
- 管理设计 Token、组件契约、页面级覆盖、版本迁移和设计到代码交接
- 为桌面端和移动端分别审查构图，同时保持内容与功能一致
- 评估成熟的 GitHub 开源组件，并适配当前项目风格
- 补齐图片过渡、交互动效、降级策略和性能检查
- 执行无障碍、溢出、遮挡、首屏任务和真实浏览器验收

## 核心原则

- **先选择交付模式：** 空项目或重要设计任务完成事实扫描后，首个可见问题必须让用户选择“设计后生图再复刻”“设计后直接实现”或“只给关键页面生图的混合模式”，也可以自定义或明确授权代理决定。空项目、没有外部参考、赶时间或“先做首页看看”都不能被当作默认直接实现。
- **先问再分析：** 是否使用外部参考与是否生成新的页面参考图是两个独立选择。用户可以上传参考图、提供网站 URL、使用当前页面或选择“不使用参考”；每个方向题都允许自由填写，最后还会单独询问额外要求。
- **先设计再生图：** 产品范围、页面状态、视觉系统、桌面/移动构图、内容基线、媒体与动效意图确认后，才允许按所选模式生成页面参考图。生成图用于呈现已完成的设计，不负责替代设计。
- **逐页面判断结构：** 官网、工作台、编辑器、电商、内容、数据、登录与混合产品不会共用一套默认骨架。F-design 会按页面识别主要任务、对象、交互拓扑、首屏优先级和移动端变化，再判断是否需要结构探索。
- **受约束地发散：** 空项目、重大改版或结构不明确时，比较 2–3 个真正不同且有产品依据的结构方向；已有合适结构或局部修复可以跳过。只换配色、字体和圆角不算新方向，也不会为了不同而采用奇怪交互。
- **主题概念贯穿页面：** 从真实产物、材料、地点或流程建立概念，并用同类对象替换检验其主题特征。品牌页面保持表达，任务界面优先熟悉且高效。
- **内容决定构图：** 先理解实际内容、数据与素材，再选择结构。去掉装饰后仍须完整回答用户的问题，静态构图成立后再加入动效。
- **不依赖其他设计 Skill：** F-design 的设计、组件、响应式、色彩、图片、动效和质量规范均已包含在本仓库中。
- **按需读取规范：** 主入口负责共享约束、任务分流与阶段路由，专项文件维护完整细则；每次只读取当前任务需要的部分。
- **移动端不是缩小版：** 移动端需要重新排序、收纳和定位内容，并单独检查首屏、触控、键盘和安全区域。
- **图片属于构图：** 图片的主体、裁切、焦点、边缘、层级和过渡需要与页面结构一起设计。
- **动效必须交付：** 动效需要有明确目的、触发条件、终止状态、性能策略和 `prefers-reduced-motion` 结果。
- **叙事动效保持 Web 原生：** 普通网页可以采用分镜、节奏、错峰和媒体转场，但不能因此套用固定 16:9 舞台、强制翻页或滚动劫持。
- **设计系统有主次：** 保留一个主设计系统，页面级差异用明确覆盖表达，不让单张生成图反向改写全局规则。
- **组件选择有证据：** 优先复用项目现有组件；需要外部组件时检查维护状态、许可证、无障碍、兼容性和主题适配能力。
- **卡片必须有理由：** 不把仪表盘卡片布局当作默认答案，不嵌套卡片，优先使用直接布局、列表、分隔线和内容区带。
- **验收依据真实证据：** 构建和静态检查不能替代页面与交互体验。验证遵守用户和宿主允许的范围；手动验收结果在用户确认前保持未验证。

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

对于较完整的新建或改版任务，F-design 会先询问设计交付模式，再询问产品目标、可选外部参考、架构、视觉方向、配色、图片、动效和额外要求。选择“直接实现”后不会生成新的页面参考图，也不会在后续要求逐图对照；用户也可以明确回复“你决定”，让代理记录假设后继续执行。

## 工作流程

1. 读取项目事实、现有规范、组件、资源和运行方式。
2. 让用户选择设计交付模式：生图后复刻、直接实现、混合、自定义或授权代理决定。
3. 让用户自行决定是否使用外部参考；可选上传文件、网站 URL、当前页面或“不使用参考”。
4. 提供产品/页面架构与技术架构选项、推荐理由和后果，由用户选择、自定义或明确授权代理决定。
5. 补齐未明确的产品、风格、色彩、图片、动效和额外需求。
6. 建立产品简报，并逐页面记录主要任务、内容对象、交互拓扑、首屏优先级、移动端变化和结构探索决定。
7. 对需要探索的页面提出 2–3 个在任务路径、信息架构、对象关系等方面真正不同的方向；淘汰无依据猎奇方案，让用户选择、组合、自定义、拒绝或授权代理决定。
8. 根据选定结构建立页面与状态清单、桌面/移动端共享内容基线和完整设计包。
9. 仅在生图或混合模式中，为选定页面生成桌面/移动参考图并确认；直接实现模式跳过此步。
10. 评估项目现有组件与必要的成熟开源组件。
11. 分阶段实现结构、系统、组件、媒体、响应式和无障碍。
12. 按允许的验收范围审查任务、结构、布局和适用视口结果；只有生图页面才进行生成参考图对照。
13. 实现并验证交互动效、网页叙事分镜和 reduced-motion 降级。
14. 完成与修改相关的结构检查、构建或测试，并提供真实验证结果和待手动验收事项。

F-design 对每个阶段保留执行状态，避免把“写进规范”误当成“已经实现”。

### 可选择和可跳过的步骤

| 步骤 | 是否可跳过 | 规则 |
|---|---|---|
| 选择设计交付模式 | 重大设计任务不可跳过 | 用户选择、自定义或明确授权代理决定 |
| 外部参考输入 | 可跳过 | 可以选择“不使用参考” |
| 架构选择 | 条件执行 | 现有项目通常保持原架构；新项目或重大迁移时需要选择 |
| 页面形态与结构策略记录 | 重大设计任务不可跳过 | 每个页面都需说明主要任务和是否需要结构探索；局部修复可使用简版记录 |
| 多结构方向探索 | 条件执行 | 空项目、重大改版、结构不明确或存在多个合理拓扑时执行；合适的既有结构、明确可用目标或局部修复可跳过并记录依据 |
| 结构方向选择 | 条件执行 | 仅在结构探索触发时执行；用户可选择、组合、自定义、拒绝或明确授权代理决定 |
| 多视觉方向设计 | 条件执行 | 结构已经确定但视觉方向仍不明确时执行；不得把换色或换字体冒充结构方案 |
| 生成页面参考图 | 可跳过 | 直接实现模式全部跳过；混合模式只生成指定页面/状态 |
| 参考图清单与桌面/移动成对检查 | 可跳过 | 只对生成参考图的页面执行 |
| 生成参考图与代码逐图对照 | 可跳过 | 直接实现页面不执行；用户明确要求还原外部目标时除外 |
| 外部开源组件搜索 | 条件执行 | 现有组件或本地语义实现足够时跳过 |
| 特殊媒体与复杂动效 | 条件执行 | 由产品、设计与参考证据决定，但基础交互反馈和 reduced motion 仍需检查 |
| 浏览器、响应式和无障碍验收 | 按验收边界执行 | 适用检查需要真实证据；手动验收在结果到达前保持未验证 |

## 优化已有网页

F-design 不只用于从零生成页面。面对已经存在的界面时，它会：

1. 在允许的验收范围内记录相关界面基线，区分源码证据、已观察结果和待手动验收事项。
2. 区分信息架构、层级、布局、排版、色彩、组件、移动端、无障碍、动效和性能问题。
3. 判断问题属于局部呈现、组件行为、响应式构图、页面层级还是产品结构；只有结构本身需要改变时才触发结构探索。
4. 优先修复任务阻塞、遮挡溢出、移动端首屏和无障碍缺陷。
5. 在保留项目身份、已学会行为和未涉及页面的前提下做针对性修改。
6. 使用相同视口比较修改前后结果，并重新走关键交互。

## 目录结构

```text
f-design/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── discovery-and-architecture.md
    ├── surface-strategy-and-structure.md
    ├── design-reference-synthesis.md
    ├── design-system-governance.md
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

F-design is a self-contained frontend product design and delivery skill built on the open Agent Skills structure. It is not limited to Codex: any compatible host that can discover a `SKILL.md` folder and load its referenced files can use it. Users choose design-then-generate-reference, design-then-build-directly, or a page-scoped hybrid. F-design classifies each surface by its primary job, explores genuinely different structures only when needed, rejects novelty without task value, and completes the selected design before optional image generation, implementation, responsive/accessibility work, motion, and browser QA.

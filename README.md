# F-design

A self-contained frontend product design and delivery skill for AI coding agents.

F-design covers product discovery, page and state planning, visual systems, responsive composition, open-source component evaluation, implementation, imagery, motion, accessibility, and browser QA. It can guide a new build, a substantial redesign, or the optimization of an existing interface.

The workflow is framework-agnostic and does not require another design skill.

## Highlights

- Guided discovery with suggested directions, a free-form choice for every question, and a separate prompt for additional requirements
- One content canon across desktop and mobile, with mobile treated as an intentional recomposition
- Role-based color systems, complete interaction states, dark-mode guidance, and accessibility checks
- Deliberate image placement, responsive crops, and reference-derived media transitions
- Evidence-based selection of mature open-source components that are adapted to the current product
- Explicit motion coverage, reduced-motion behavior, performance checks, and browser evidence
- Existing-interface optimization through baseline screenshots, root-cause diagnosis, targeted changes, and before/after verification
- Strong limits on unnecessary card layouts, nested cards, generic dashboard styling, and unverified visual claims

## Install

Clone the repository into the personal skill directory discovered by your agent host.

### Codex

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/yeyuancc0-glitch/f-design.git ~/.agents/skills/f-design
```

Restart or refresh Codex after installation. Some Codex setups may use a different discovered skill root; use the path shown by your installation when it differs.

### Other Agent Skills compatible apps

Copy or clone this repository as a single `f-design` folder inside the app's skills directory. The folder must keep `SKILL.md`, `agents/`, and `references/` together. For Qoder or QoderWork editions, use the skill-management UI or the personal skills path documented by that edition.

## Update

```bash
git -C ~/.agents/skills/f-design pull --ff-only
```

## Use

In Codex, invoke it explicitly:

```text
$f-design Design and implement a responsive homepage for ...
```

```text
$f-design Audit this existing page, improve its layout and mobile experience, then verify it in a browser.
```

Hosts with slash-command skill invocation may expose it as `/f-design`. You can also ask the agent to use F-design by name.

For material design work, expect a short discovery round before visual analysis or implementation. You may answer the suggestions, write a custom direction, add separate requirements, or delegate the decisions.

## Repository Layout

```text
f-design/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── discovery-and-architecture.md
    ├── visual-system.md
    ├── color-system-and-states.md
    ├── responsive-mobile.md
    ├── open-source-components.md
    ├── media-and-image-transitions.md
    ├── motion-and-interaction.md
    ├── existing-surface-optimization.md
    └── ...
```

## Design Position

F-design does not prescribe one visual style. It requires the agent to reconcile product purpose, project conventions, user preferences, content, and current implementation evidence before choosing a direction. Existing identity wins unless the user explicitly requests a change.

It also distinguishes reusable behavioral primitives from visual styling: a mature component may be selected for accessibility or interaction reliability, but its demo appearance should not be pasted into an unrelated product.

## License

Licensed under the [Apache License 2.0](LICENSE).

F-design is an original synthesis informed by public design-engineering resources. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) for acknowledgements and upstream licenses.

## 中文说明

F-design 是一个面向 AI 编程代理的完整前端产品设计与交付 skill。它既能用于从零设计和实现网站，也能用于审查并优化已经写好的页面。

它强调：分析前先补齐需求；每个选择题都允许用户自由填写，并单独询问额外要求；桌面端和移动端共享同一内容事实但分别构图；图片必须融入版式；动效必须有目的、有降级方案并经过真实浏览器验证；开源组件要有成熟度证据且必须适配当前项目风格；不能把卡片和仪表盘布局当作默认答案。

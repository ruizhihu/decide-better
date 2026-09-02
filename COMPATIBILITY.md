# 跨平台兼容性

## 兼容性承诺

人生决策器将 `SKILL.md` 作为唯一的行为源。它不依赖特定厂商的工具名、命令或界面，因此可在支持以下任一能力的智能体中使用：原生 Skills、项目级指令、全局自定义指令，或文件附件对话。

`agents/openai.yaml` 仅为 Codex 提供显示名称、默认提示和自动调用策略；其他平台可以忽略该文件。所有平台都应保留 `references/deep-analysis.md`，以便高重要性或高不确定性决策按需进入深度模式。

## 接入方式

### 原生 Skill 平台

若平台能加载 `SKILL.md` 或采用 Agent Skills 约定，将整个仓库文件夹复制到该平台官方规定的 Skills 目录。以平台文档为准设置目录或启用开关；本仓库不为未验证的平台目录写入猜测性的配置文件。

### 项目规则或自定义指令平台

把 `SKILL.md` 的完整内容添加为项目级规则或自定义指令。若平台支持关联文件，让该规则在深度模式时读取 `references/deep-analysis.md`；若不支持，连同该参考文件一起粘贴或上传。

建议使用清晰的加载说明，例如：

```text
Use the attached SKILL.md as the decision-analysis instruction. Read deep-analysis.md only for high-stakes or high-uncertainty decisions.
```

### 对话式平台

上传 `SKILL.md` 与 `references/deep-analysis.md`，随后直接提出决策问题。平台不支持文件时，可将两份内容粘贴到系统提示或自定义指令中；在上下文长度有限时，优先保留 `SKILL.md`，仅在需要深度分析时补充参考文件。

## 运行时映射

不同智能体的界面不同，但核心行为不变：

- 需要信息时，提出只会改变建议的问题，而不是假设缺失信息已知。
- 支持本地文件时，深度模式读取参考文件；不支持时，以已加载内容为边界，明确说明限制。
- 有浏览、检索或计算工具时，将它们用于验证证据；没有工具时，不虚构来源、数据或精确概率。
- 无论平台是否支持自动调用，都由用户决定最终行动；涉及购买、交易、联系他人或提交信息时，须另行取得授权。

## 范围与边界

本仓库保证的是**指令与文件结构的可移植性**，而非每个智能体的自动发现、工具权限或文件读取功能。不同产品会改变其目录约定和导入方式；请始终优先采用该平台最新的官方文档。若某个平台只能接受单段提示，使用 `SKILL.md` 的完整内容即可获得基础的快速决策模式。

## 平台兼容性测试（2026-09-02）

以下结果区分“结构兼容”和“真实运行”。结构兼容表示本仓库的文件格式、前置元数据和相对参考文件符合该平台公开规范；只有在该平台实际加载并完成一次决策时，才能标记为真实运行通过。

| 平台 | 官方接入机制 | 结构兼容 | 真实运行 |
| --- | --- | --- | --- |
| Claude Code | `~/.claude/skills/<name>/SKILL.md` 或 `.claude/skills/<name>/SKILL.md` | 通过 | 未运行：本机未安装 Claude Code |
| Cursor | `~/.cursor/skills/<name>/SKILL.md` 或 `.cursor/skills/<name>/SKILL.md` | 通过 | 未运行：本机未安装 Cursor |
| Gemini CLI | `~/.gemini/skills/<name>/SKILL.md`、`.gemini/skills/<name>/SKILL.md`，也支持 `.agents/skills/` | 通过 | 未运行：本机未安装 Gemini CLI |
| WorkBuddy | 本次未找到公开的第三方 `SKILL.md` 导入规范 | 不宣称原生兼容 | 未运行：无本机客户端与登录会话 |
| 豆包工作/豆包 | 公开产品页面可见内置 Skill 功能，但本次未找到公开的用户自定义 `SKILL.md` 导入规范 | 仅可按“项目指令/附件”方式适配 | 未运行：需要登录后的产品入口 |
| DeepSeek 智能体 | DeepSeek API 支持系统消息并可作为多种 Agent 工具的模型后端；本次未找到原生 Skill 加载器规范 | 可作为系统提示或附件适配 | 未运行：需要用户自有 API 凭据或目标 Agent 环境 |

Claude Code、Cursor 和 Gemini CLI 的原生格式与本仓库一致：均以含 YAML frontmatter 的 `SKILL.md` 作为入口，并允许相对路径引用辅助资源。因此，复制整个项目文件夹即可保留深度分析能力。相关公开规范见 [Claude Code Skills](https://code.claude.com/docs/en/skills)、[Cursor Skills](https://cursor.com/docs/skills) 和 [Gemini CLI Agent Skills](https://geminicli.com/docs/cli/skills/)。

## 真实运行测试步骤

在已安装且已登录的平台中，用同一条测试请求检验行为，而不是只检查文件是否被发现：

```text
我正在考虑是否接受一份高薪但需要搬家的工作。请先只询问会改变建议的信息；随后给出条件式建议、置信度、机会成本、最坏合理情景、最小下一步和结论改变条件。
```

通过标准：智能体只提出决策相关问题；不会把高薪等单一信号当作结论；输出包含上述六项；没有编造概率、来源或外部行动。对 WorkBuddy、豆包和 DeepSeek 的聊天/Agent 产品，先将 `SKILL.md` 及 `references/deep-analysis.md` 作为附件或自定义指令加载，再执行同一请求。

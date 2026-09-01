# Viral Video Editing Skill

这是一套用于中文口播、工具教程和工作台演示的高信息密度剪辑 Skill。它把
“语音转写 → 语义分组 → 关键帧检查 → 15–20 秒审核预览 → 定点修改 → 最终渲染”
串成一条可复用流程。

## 入口

- [SKILL.md](SKILL.md)：可直接交给 Codex/Claude Code 的主 Skill。
- [references/remotion-prompt-workflow.md](references/remotion-prompt-workflow.md)：Remotion 分阶段提示词与验收清单。
- [agents/openai.yaml](agents/openai.yaml)：Skill 的显示名称和默认提示词。
- [视频剪辑skill.md](视频剪辑skill.md)：旧中文文件名的兼容入口，内容不再单独维护。

## 快速流程

```text
原始视频/脚本/参考图
        ↓
语音转写 + 逐句/词级时间轴
        ↓
完整论证单元 → 语义弹窗计划
        ↓
静态关键帧门禁（安全区/越界/顺序）
        ↓
15–20 秒带原声审核预览
        ↓
按时间点定向修改
        ↓
从原始素材渲染正式成片并核验媒体参数
```

详细说明：

- [制作流程](docs/workflow.md)：A–F 六阶段、门禁和交付标准。
- [语义弹窗](docs/semantic-popups.md)：把口播语义映射为卡片、数字、评论和流程组件。
- [分镜制作](docs/storyboard.md)：从时间锚点生成分镜图并检查人物保护区。
- [字幕时间轴](docs/subtitle-timeline.md)：SRT 与词级 JSON 的字段契约；字幕层可由创作者自行添加。

## 本次示例

[工作台教程示例](examples/workbench-tutorial/README.md) 收录了本次视频的脱敏语义弹窗时间轴、分镜总览和精选关键帧。截图只用于展示构图、层级和时间锚点，不是固定模板。

示例默认遵循以下约束：真人开头/结尾加语义弹窗，中段录屏保持原样，不叠加字幕；卡片避开眼睛、嘴部、手势和底部字幕安全区。

## 使用边界

本仓库提供 Skill、规范和示例素材，不包含原始视频、原始音频、模型缓存、逐字稿元数据或审核中间文件。正式制作时请使用你有权处理的素材，并在公开分享真人截图前确认肖像和背景内容授权。

## 协同 Skill

用户点名的 [cheat-on-content](cheat-on-content/SKILL.md) 作为可选的内容校准 Skill 放在独立目录，不改变剪辑 Skill 的时间轴和渲染规则。它负责选题、评分、盲预测和发布后复盘；视频剪辑仍以根目录 [SKILL.md](SKILL.md) 为准。

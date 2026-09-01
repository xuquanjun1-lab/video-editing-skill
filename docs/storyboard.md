# 分镜图制作

分镜图用于在渲染前确认“这一秒画面应该长什么样”。它不是最终视频，也不替代时间轴。

## 分镜表字段

每一行至少包含：

| 字段 | 含义 |
| --- | --- |
| `id` | 逻辑组编号，如 `S01`、`E01` |
| `coverage` | 真人开头、录屏或真人结尾 |
| `start` / `end` | 卡片可见范围（秒） |
| `trigger` | 词级重音触发时间（秒） |
| `exitStart` | 淡出开始时间（秒） |
| `position` | `topLeft` 或 `topRight` 等安全区位置 |
| `type` | hook、method、action、bridge、result、cta |
| `keyword` | 卡片上的核心结论 |
| `sourceAnchor` | 对应的口播语义锚点 |

## 制作步骤

1. 从源视频抽取每个语义组的代表帧，保持原始画幅。
2. 在代表帧上叠加语义卡，先静态排版再设计入场动画。
3. 在帧底部标注 `id | 起止时间 | 口播锚点`，便于人工复核；这些标签只出现在分镜图，不进入成片。
4. 将所有分镜按时间顺序排成总览图，检查逻辑组之间是否有残留。
5. 通过安全区检查后，才生成动态预览。

## 本次示例

- [分镜总览](../examples/workbench-tutorial/storyboard/storyboard-overview.jpg)
- [精选关键帧](../examples/workbench-tutorial/storyboard/)
- [时间轴 CSV](../examples/workbench-tutorial/timeline/semantic-popup-timeline.csv)

示例画面中的真人和背景为用户授权的制作示例，仅用于说明布局、层级和时间关系；不要把示例人物、房间或文案当作通用素材。

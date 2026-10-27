# Picture Skill · 钢笔淡彩旅行手账

[English](README.en.md) · [技能文件](skills/pen-watercolor-travel-journal-v1-0/SKILL.md) · [MIT 许可证](LICENSE)

把一张照片重新绘制为轻盈的钢笔淡彩旅行手账插画：保留原图的主体、空间关系和画幅比例，让水彩自然淡入纸面，在底部配上英文手写题字和四枚取自原图的纯色色卡。

本仓库提供一个 **Agent Skill 指令包**，不包含图像模型、API 密钥或独立绘图程序。使用时需要提供照片，并在具备图像编辑能力的 AI 宿主中运行；仅安装本技能不会自动获得图像编辑能力。

## 视觉特点

| 要素 | 绘制要求 |
| --- | --- |
| 场景保真 | 保留原图的核心主体、相对位置、透视和横竖方向，要求沿用原图比例 |
| 钢笔线稿 | 细、轻、断续，突出必要轮廓，减少背景细节 |
| 透明淡彩 | 低饱和水彩、轻微纸张肌理和自然水痕 |
| 连续纸面 | 景物四周自然淡出，底部留白与画面融合，不添加画框或拼贴面板 |
| 自适应底色 | 根据原图的日夜、冷暖和光线选择纸面洗色 |
| 英文题字 | 一个英文标题与一行英文短句，呈自然手写墨迹 |
| 四枚色卡 | 右下角恰好四枚圆角方形纯色色卡，颜色全部来自原图 |

适合旅行、街道、建筑、风景、花园和日常场景照片。完整绘制约束与检查流程见 [SKILL.md](skills/pen-watercolor-travel-journal-v1-0/SKILL.md)。上述内容是技能的目标要求，实际效果取决于宿主及所用图像编辑工具。

## 安装

### 在 Codex 中使用 Skill Installer

在提供内置 `skill-installer` 的 Codex 环境中，发送：

```text
$skill-installer 请从 https://github.com/LiyuTian-web/picture-skill 安装 skills/pen-watercolor-travel-journal-v1-0 目录中的技能。
```

安装后检查技能列表；如果没有显示，重启 Codex。安装器用于安装指令包，图像编辑工具仍需由宿主提供。

### 手动安装

1. 下载本仓库的 ZIP，或克隆仓库：

   ```sh
   git clone https://github.com/LiyuTian-web/picture-skill.git
   ```

2. 将 `skills/pen-watercolor-travel-journal-v1-0` **整个文件夹**复制到目标项目的 `.agents/skills/` 目录。
3. 确认最终路径为 `.agents/skills/pen-watercolor-travel-journal-v1-0/SKILL.md`。
4. 在目标项目中打开 Codex，检查是否发现该技能；如未出现，重启 Codex。

以上是 Codex 的项目级安装方式。其他支持 Agent Skills 的宿主，请按各自的导入说明安装，并确认具备照片输入与图像编辑能力。本仓库未验证其他宿主的运行效果。

安装与发现机制参考 [OpenAI 官方技能文档](https://learn.chatgpt.com/docs/build-skills)。

## 使用

先附上要处理的照片，再发送以下请求。这些是调用示例，不是已生成的效果展示。

### 自动题字

```text
使用 $pen-watercolor-travel-journal-v1-0，把我上传的照片画成钢笔淡彩旅行手账。
保留原图比例和主体，题字由你根据画面创作。
```

### 指定英文题字

```text
使用 $pen-watercolor-travel-journal-v1-0，处理我上传的照片。
标题使用：A Quiet Afternoon
短句使用：A little light along the familiar road.
请逐字保留这两行英文。
```

### 保存成品

在请求中明确写出“请把成品保存到……”并指定位置。技能要求使用新的文件名，避免覆盖原图。

默认交付一张成品图和 1–3 句中文创作说明。只有明确要求时，才附完整提示词、Scene Card、具体色值或详细构图说明。

## 使用须知

- 必须提供参考照片；本技能以照片为编辑目标和配色来源。
- 未指定题字时，技能根据可见场景创作英文标题与短句，不虚构具体地名、日期或人物信息。
- 技能要求保持原图比例；若宿主无法精确满足，应说明实际输出尺寸。
- 英文拼写、场景保真和四色卡数量都需要检查；出现明确失败时，最多进行一次定向修正。
- 原图不属于仓库内容。技能要求不为补充内容而搜索照片，或将照片上传到用户未指定的位置；除用户要求或宿主交付规则需要，不将图片写入项目目录。

## 仓库结构

```text
picture-skill/
├── README.md
├── README.en.md
├── LICENSE
├── .gitignore
├── .gitattributes
└── skills/
    └── pen-watercolor-travel-journal-v1-0/
        └── SKILL.md
```

当前收录版本为 **v1.0**，技能标识为 `pen-watercolor-travel-journal-v1-0`。

## 反馈与许可

欢迎通过 [Issues](https://github.com/LiyuTian-web/picture-skill/issues) 反馈问题或提出改进建议。描述宿主环境、预期效果和实际差异即可；请勿提交 API 密钥或未经授权的照片。

本仓库的技能指令和文档采用 [MIT 许可证](LICENSE)。

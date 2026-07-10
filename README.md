# paper-image-ppt

中英双语医学科研配图规划与提示词生成 Codex Skill。

**Bilingual Codex skill for scientific medical illustration planning and prompt generation.**

## 简介 | Overview

`paper-image-ppt` 将医学论文、实验方案、针灸方药内容或医学科普 PPT 正文，转化为结构清晰、医学准确、适合版式的配图方案，并生成可用于图像生成模型、科研制图工具或后期设计软件的中文与英文提示词。

`paper-image-ppt` converts medical manuscripts, experimental protocols, acupuncture and herbal-medicine content, and public-health presentation text into scientifically grounded illustration plans, figure–text mappings, and bilingual prompts for image-generation or scientific-illustration workflows.

## 主要功能 | Features

- 分析正文叙事逻辑，判断哪些内容需要配图。
- 建立正文、图号、图题和图片功能的一一对应关系。
- 规划图形摘要、实验流程图、机制图、时间轴和多面板 Figure。
- 规划针灸穴位、经络、操作手法、中药材和复方配伍示意图。
- 规划医学科普、教学和逐页 PPT 的主图与辅助图。
- 生成中文提示词、英文提示词、双语提示词和负面提示词。
- 提供论文、期刊、PPT 的排版比例、风格统一和后期文字添加建议。
- 检查医学准确性、图文对应、科研诚信、患者隐私、版权和诊疗安全风险。

## 适用场景 | Use Cases

### 科研论文 | Research publications

- SCI 论文和中文核心期刊
- Graphical Abstract
- 研究设计图和技术路线图
- 动物、细胞和临床实验流程图
- 作用机制图和信号通路图
- 多组学整合示意图
- Figure legend、图题和图注优化

### 中医药与针灸 | Acupuncture and herbal medicine

- 穴位定位图和经络循行图
- 针刺方向和操作示意图
- 艾灸、拔罐、刮痧、推拿等教学图
- 中药材饮片图和复方组成图
- 君臣佐使、药物—靶点—通路关系图
- 中药煎煮、足浴、熏洗和生活调护示意图

### 医学教育与科普 | Medical education and public health

- 医学教学 PPT
- 医院科普 PPT 和公众号内容
- 症状场景、正确/错误行为对比图
- 风险提示、就医警示和特殊人群安全提示图
- 逐页固定数量的 PPT 配图方案

## 核心原则 | Core Principles

1. **图文对应 | Figure–text alignment**：每张图必须服务于正文中的明确句子、措施、实验步骤或结论。
2. **医学准确 | Medical accuracy**：不为了视觉效果改变解剖、穴位、经络、药材、操作或实验流程。
3. **科研诚信 | Research integrity**：不伪造实验数据、显微图像、患者照片、统计结果或论文原始结果。
4. **证据分级 | Evidence-aware mechanisms**：区分直接验证、文献支持、推测机制和待验证路径。
5. **隐私保护 | Privacy protection**：不生成可识别患者身份的信息或真实病例细节。
6. **诊疗安全 | Clinical safety**：不把专业操作包装成普通人可随意进行的居家治疗，也不替代正规诊疗。
7. **版权合规 | Copyright compliance**：原创重构信息结构和视觉语言，不复制他人 Figure、教材插图或商业图库图像。

## 默认工作流程 | Workflow

1. 识别使用场景、目标受众、语言、版式、图片数量和比例。
2. 提取疾病、研究对象、干预、对照、实验时间、穴位、经络、方药、操作、图号和风险提示。
3. 核对正文中的图号，确保图号连续、数量一致、没有漏图或重复图。
4. 为每张图片选择最能服务叙事的类型和构图方式。
5. 建立图文对应表，明确图片功能、主体、视角、标注、比例和使用位置。
6. 生成中文提示词、英文提示词和负面提示词。
7. 检查医学准确性、科研诚信、隐私、版权、安全边界和视觉一致性。

## 默认输出 | Default Output

通常输出以下内容：

- 配图总体方案
- 图片与正文对应表
- 每张图的图片功能和构图建议
- 中文生成提示词
- English prompt
- 负面提示词
- 医学与合规提醒
- 排版建议
- 图号、数量和一致性核查

当用户明确要求“只需要提示词”时，只输出核对后的提示词。当用户要求“不要文字”时，提示词会加入 `no text, no labels, no letters, no numbers, no watermark, no logo`。

## 示例 | Example

中文请求：

> 使用 `$paper-image-ppt`，根据下面的医学研究摘要设计一张 SCI Graphical Abstract，并输出图文对应关系、中文提示词、英文提示词和科研诚信提醒。

English request:

> Use `$paper-image-ppt` to design a graphical abstract for the following medical research abstract. Provide the figure–text mapping, Chinese and English prompts, negative prompts, and research-integrity notes.

## 安装与使用 | Installation and Usage

### 在 Codex 中安装 | Install in Codex

将此 GitHub 仓库地址提供给 Codex 的 skill installer：

```text
https://github.com/Libby5201234/paper-image-ppt
```

安装后，使用以下名称调用：

```text
$paper-image-ppt
```

### 手动安装 | Manual installation

将整个仓库文件夹复制到 Codex skills 目录：

```text
$CODEX_HOME/skills/paper-image-ppt
```

如果未设置 `CODEX_HOME`，通常使用：

```text
~/.codex/skills/paper-image-ppt
```

## 仓库结构 | Repository Structure

```text
paper-image-ppt/
├── SKILL.md
├── README.md
└── agents/
    └── openai.yaml
```

## 输出限制 | Limitations

本 skill 生成的是配图规划、教学示意图、机制概念图、实验流程图或版式建议，不是医学诊断、治疗处方、真实实验结果或原始科研数据。

未提供可靠依据时，不会自行补写针刺深度、药物剂量、实验时间、分组数字、患者信息或未经验证的机制结论。相关细节应依据原始方案、权威教材、临床指南、专家共识或目标期刊要求进一步核实。

This skill supports illustration planning and educational or conceptual diagrams. It does not provide medical diagnosis, treatment prescriptions, real experimental results, or fabricated primary data. Unverified anatomical, clinical, experimental, or mechanistic details must be checked against authoritative sources.

## 免责声明 | Disclaimer

本项目用于医学科研表达、教学设计和健康教育内容规划，不能替代医生诊疗、急诊处理、药师指导、伦理审查或目标期刊的投稿要求。

This project is intended for scientific communication, education, and public-health content planning. It does not replace professional medical care, emergency services, pharmacy guidance, ethics review, or journal-specific publication requirements.

## 许可证 | License

本仓库目前尚未声明具体开源许可证。若要允许他人复制、修改或再发布，建议作者后续根据使用目的选择并添加合适的许可证。

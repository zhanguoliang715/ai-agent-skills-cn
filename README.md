# 中文优先的 AI Agent 技能合集

**四个不依赖任何流水线的独立技能：本地 ComfyUI 出图、法律 PDF 入库、SVG 图表排版纪律、中文报告体文风。每个都能单独装、单独用，互不调用。**

![License](https://img.shields.io/badge/license-MIT-yellow)
![Skills](https://img.shields.io/badge/skills-4-2E7D32)
![Language](https://img.shields.io/badge/docs-中文-C0392B)

## 这四个技能是什么关系

**没有关系。** 这是它们的共同点：每一个都从真实返工里长出来，独立可拆，不依赖别的技能、不共享配置、不按顺序执行。所以放在一个仓库里，但各自是自包含目录。

与 [agent-pipeline-skills](https://github.com/zhanguoliang715/agent-pipeline-skills) 的区别：那个仓库是十棒串行流水线（需求→评审→设计→开发→测试→安全），技能之间有强制的前后依赖；**本仓库只收「单独拿出来就能用」的技能**。

## 四个技能

| 技能 | 解决什么麻烦 | 关键产出 | 依赖 |
|---|---|---|---|
| [`law-text-ingest`](skills/law-text-ingest/) | 法律 PDF 入库时条号错、版本过期、编章结构靠手抄 | 编章结构（脚本提取）+ 逐条核对留痕 | Python 3.9+，标准库 |
| [`comfyui-local-zimage`](skills/comfyui-local-zimage/) | 云端出图要钱、本地 ComfyUI 装不上 / 下不动 / 显存爆 | 可跑的 API 工作流 + 批量出图脚本 | Windows + NVIDIA 8GB+，ComfyUI |
| [`diagram-layout-discipline`](skills/diagram-layout-discipline/) | SVG 图里文字溢出边框、嵌套容器分不清、流程用文字描述 | 三条硬纪律 + 文字宽度实测脚本 + 骨架生成器 | Python 3.9+，Pillow（量字宽） |
| [`chinese-report-voice`](skills/chinese-report-voice/) | 给评委看的文档写成故事、语体判错、自我削弱句 | 文风六条 + 两个门禁脚本（文风扫查 / PDF 排版体检） | Python 3.9+，python-docx / pymupdf |

## 怎么装

每个技能目录都是自包含的（`SKILL.md` + `scripts/` + `references/`）。把它整个拷到你所用 Agent 的技能目录下即可：

```bash
git clone https://github.com/zhanguoliang715/ai-agent-skills-cn.git
cp -r ai-agent-skills-cn/skills/<技能名> ~/.workbuddy/skills/
```

只想要其中一个，就只拷那一个目录，不用整仓库。

## 它们共同的三个特点

1. **都是「反例驱动」**：每条规则背后都有一次真实返工（文字溢出被截图退回、报告写成故事被退三次、条号错到整篇重做）。规则不是凭想象定的。
2. **都带可跑的门禁**：不靠"注意一下"，靠脚本退出码。文字量宽用 `measure_text.py` 实测，不靠眼睛估。
3. **都写清了边界**：什么情况不适用、会失败在哪、换场景要改什么。**这些技能不是通用的**，换个领域就得换规则，见各技能 `SKILL.md` 的适用范围段。

## 文档

| 想看什么 | 去哪 |
|---|---|
| 每个技能怎么用、为什么这么设计 | [docs/技能说明/](docs/技能说明/) |
| 完整规则原文 | 各技能目录下的 `SKILL.md` |
| 官网 | [zhanguoliang715.github.io/ai-agent-skills-cn](https://zhanguoliang715.github.io/ai-agent-skills-cn/) |

## 许可

[MIT](LICENSE)

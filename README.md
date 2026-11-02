# AI Agent 技能索引（中文优先）

**这里不放技能，只放索引。每个技能是独立仓库，一个链接对应一个技能，想分享哪个发哪个。**

![Skills](https://img.shields.io/badge/独立技能-4-2E7D32)
![License](https://img.shields.io/badge/license-MIT-yellow)

## 为什么拆成一技能一库

早先这 4 个技能挤在本仓库里，问题是：分享时没法只给一个，别人 clone 下来还得自己挑；仓库的 Star、Issue、版本也跟着混在一起，没法单独说明。**四个技能互不调用，没有任何理由共享一个仓库。**

现在的规矩很简单：**有数据流依赖的才住一起，其余一律独立成库。**

## 四个独立技能

| 技能 | 一句话 | 依赖 |
|---|---|---|
| [law-text-ingest](https://github.com/zhanguoliang715/law-text-ingest) | 法律 PDF 入库：时效核查、脚本提取编章结构、逐条回原文核对 | Python 标准库 |
| [comfyui-local-zimage](https://github.com/zhanguoliang715/comfyui-local-zimage) | Windows 本机 ComfyUI 免费出图：下载、显存、锁脸、拼视频 | Windows + NVIDIA 8GB+ |
| [diagram-layout-discipline](https://github.com/zhanguoliang715/diagram-layout-discipline) | SVG 图表三条硬纪律 + 文字宽度实测，不许溢出、不许混淆 | Python 标准库 |
| [chinese-report-voice](https://github.com/zhanguoliang715/chinese-report-voice) | 中文报告体文风：先判文体、六条语体、两个可跑门禁 | Python（docx/pdf 需可选库） |

## 相关但不在本索引的技能

| 仓库 | 是什么 | 为什么单独 |
|---|---|---|
| [agent-pipeline-skills](https://github.com/zhanguoliang715/agent-pipeline-skills) | 软件开发十棒流水线（需求→评审→设计→开发→测试→安全） | 十棒之间有强制数据流，**必须住一起**，拆开就失效 |
| [architecture-designer](https://github.com/zhanguoliang715/architecture-designer) | 流水线第六棒的单体发行版 | 给"只想要架构这一棒"的人；与主仓库同源 |

## 怎么用

```bash
# 只要一个技能，就只 clone 那一个
git clone https://github.com/zhanguoliang715/law-text-ingest.git
cp -r law-text-ingest ~/.workbuddy/skills/
```

每个技能仓库里都有：`SKILL.md`（规则原文）、`docs/新手手册.md`（怎么做、为什么）、`docs/技术文档.md`（契约、边界、失败模式）。

## 官网

[zhanguoliang715.github.io/ai-agent-skills-cn](https://zhanguoliang715.github.io/ai-agent-skills-cn/)

## License

[MIT](LICENSE)

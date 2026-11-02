# 变更记录

## 2026-11-03 首次发布

- 收录四个独立技能：`law-text-ingest`、`comfyui-local-zimage`、`diagram-layout-discipline`、`chinese-report-voice`
- 每个技能目录自包含（`SKILL.md` + `scripts/` + `references/` / `examples/`），可单独拷出使用
- 新增 `docs/技能说明/`：四份面向使用者的说明，讲清适用场景、做法、边界与常见失败
- 新增 Pages 首页、Issue 表单、PR 模板、MIT 许可证
- **可移植性修复**：`diagram-layout-discipline` 的 `gen_all.py` / `gen_skeleton.py` 原先把 `sys.path` 写死成本机技能目录，换机器即 `ImportError`；改为用 `__file__` 定位同目录的 `measure_text.py`。修复后两脚本退出码均 0，断言全通过
- **脱敏**：`SKILL.md` 中的个人绝对路径改为占位符；`comfyui-local-zimage` 的「本机现状」章节改为「参考部署（作者机器，仅供对照）」，并注明换机器时每一项都要重写

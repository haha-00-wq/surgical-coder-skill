# Surgical Coder

`surgical-coder` 是一个给 Codex 使用的编码纪律 skill。它的目标是让代码修改更克制、更精准、更容易验证：少做假设，少做无关改动，避免过度设计，并用测试或明确检查证明结果。

## 它解决什么问题

- 需求有歧义时，先暴露假设或提问，而不是直接猜。
- 修 bug 或改功能时，只动和目标直接相关的代码。
- 避免为了“以后可能用得上”新增抽象、配置或复杂框架。
- 修改已有项目时保留现有风格，不顺手重构旁边代码。
- 完成后用测试、类型检查、lint、构建或手动场景验证结果。

## 适合什么时候用

- 写新功能
- 修 bug
- 重构
- code review
- 修改已有代码库
- 任务范围不清楚或存在多个实现路径

## 安装到 Codex

从仓库根目录运行：

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo haha-00-wq/surgical-coder-skill \
  --path skills/surgical-coder
```

也可以把 `skills/surgical-coder` 目录复制到：

```text
~/.codex/skills/surgical-coder
```

重启 Codex 后，新 skill 会被加载。

## 目录结构

```text
skills/
└── surgical-coder/
    ├── SKILL.md
    └── agents/
        └── openai.yaml
```

## 使用方式

Codex 在写代码、修 bug、重构、review 或处理有歧义的工程任务时，可以自动触发这个 skill。也可以显式要求：

```text
使用 $surgical-coder 来修这个 bug，尽量保持最小 diff，并验证结果。
```

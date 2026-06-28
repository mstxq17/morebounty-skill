# morebounty

中文 SRC 漏洞挖掘核心 skill。

## 目录

```text
skills/morebounty/
├── SKILL.md
├── manifest.json
├── agents/
│   └── openai.yaml
└── references/
    ├── dictionaries.md
    └── project-memory.md
```

## npx skills 安装

安装到当前项目的 Codex：

```bash
npx skills add https://github.com/mstxq17/morebounty-skill \
  --skill morebounty \
  --agent codex \
  --yes \
  --copy
```

安装位置：

```text
.agents/skills/morebounty
```

全局安装到 Codex：

```bash
npx skills add https://github.com/mstxq17/morebounty-skill \
  --skill morebounty \
  --agent codex \
  --global \
  --yes \
  --copy
```

重启 Codex 后使用：

```text
Use $morebounty 为这个SRC目标制定高效漏洞挖掘路径。
```

## 校验

```bash
npx skills add . --list
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py \
  skills/morebounty
```

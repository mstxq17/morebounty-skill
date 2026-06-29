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

全局安装：

```bash
npx skills add https://github.com/mstxq17/morebounty-skill \
  --skill morebounty \
  --global \
  --yes \
  --copy
```

安装到指定 agent（以 Codex 为例）：

```bash
npx skills add https://github.com/mstxq17/morebounty-skill \
  --skill morebounty \
  --agent codex \
  --yes \
  --copy
```

如需全局安装到指定 agent，可组合使用：

```bash
npx skills add https://github.com/mstxq17/morebounty-skill \
  --skill morebounty \
  --global \
  --agent codex \
  --yes \
  --copy
```

重启对应 agent 后使用：

```text
Use $morebounty 为这个SRC目标制定高效漏洞挖掘路径。
```

## 更新

全局：

```bash
npx skills update morebounty -g
```

当前项目（Codex）：

```bash
npx skills update morebounty -p
```

不指定范围时会交互选择：

```bash
npx skills update morebounty
```

重启 Codex 后生效。

## 校验

```bash
npx skills add . --list
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py \
  skills/morebounty
```

# morebounty

中文 SRC 漏洞挖掘核心 skill。

## 目录

```text
skills/morebounty/
├── SKILL.md
├── manifest.json
└── agents/
    └── openai.yaml
```

## npx skill 安装

```bash
SKILL_BASE_URL=https://github.com/mstxq17/morebounty-skill/tree/main \
  npx skill skills/morebounty
```

安装到当前项目：

```text
.codebuddy/skills/morebounty
```

## Codex 安装

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R skills/morebounty "${CODEX_HOME:-$HOME/.codex}/skills/"
```

重启 Codex 后使用：

```text
Use $morebounty 为这个SRC目标制定高效漏洞挖掘路径。
```

## 校验

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py \
  skills/morebounty
```

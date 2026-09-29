# C 盘清理工作流

> WorkBuddy Skill · 屋里涛说

只读扫描 → 分级清单 → 用户确认 → 精准删除 → 空间验证。

## 技能清单

| 技能 | 说明 |
|---|---|
| **c-drive-cleanup** · 磁盘清理 | 内置本机已知可清目标与风险分级，以及 PowerShell 删除被安全钩子拦截时的绕行方案。 |

## 工作流

```
只读扫描  →  分级清单  →  用户确认  →  精准删除  →  空间验证
（永不先删）  （带路径大小）  （明确授权）  （高风险区警告）  （确认释放）
```


## 安装

把 `skills/` 下的技能目录拷贝到 WorkBuddy 的技能目录：

```bash
cp -r skills/* ~/.workbuddy/skills/
```

Windows PowerShell：

```powershell
Copy-Item .\skills\* "$env:USERPROFILE\.workbuddy\skills\" -Recurse -Force
```

重启 WorkBuddy 后，技能列表即可看到。

## 使用要点

- **铁律**：先扫描、后删除。第一轮永远只读，出带路径和大小的清单，等明确确认后才动手。
- **高风险警告**：用户目录（Desktop / Downloads / Documents / Home）属高风险区，删除前必须警告 + 列全路径。绝不递归删除系统目录。
- 触发词：清理C盘、C盘满了、C盘爆了、磁盘空间不足、清一下缓存垃圾。

## 环境依赖

- PowerShell

## 目录规范

```
c-drive-cleanup/
└── skills/
    ├── c-drive-cleanup/
```

每个技能遵循统一结构：`SKILL.md`（必需，含 name/description frontmatter）+ `scripts/`（可选）+ `references/`（可选）。

---

## License

MIT — 随意取用、修改、二次分发。

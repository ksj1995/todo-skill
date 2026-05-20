# todo-skill

[English](#english) | [中文](#中文)

---

## English

Project TODO management plugin for Claude Code.

Scans TODO comments in code, syncs with `PROJECT_TODOS.md`, reminds you of unfinished items, and locates code positions.

### Features

- **Explicit triggers**: `/todo-skill`, `/todo`, "list todos", "what's left", "complete todos", "scan todos"
- **Implicit triggers**: Detects 35+ keywords during code editing (e.g., `TODO`, `FIXME`, `placeholder`, `temporary`, `waiting for api`, `mock`, `unfinished`, `reserved`, `pending`, `temp`, `hardcoded`, `dev-in-progress`, etc.) and proactively suggests adding markers
- **Bidirectional sync**: Compares code comments ↔ `PROJECT_TODOS.md`, finds orphan entries or unregistered items
- **Completion tracking**: Cleans up both code comments and `PROJECT_TODOS.md` when done

### Installation

**Via Claude Code Plugin Manager (Recommended)**

```
/plugin marketplace add ksj1995/todo-skill
/plugin install todo-skill@todo-skill
```

**Manual - Project Level (current project only)**

```bash
# Create directory in your project root
mkdir -p .claude/skills/todo-skill
cp skills/todo-skill/SKILL.md .claude/skills/todo-skill/SKILL.md
```

**Manual - Global (all projects)**

```bash
# macOS / Linux
mkdir -p ~/.claude/skills/todo-skill
cp skills/todo-skill/SKILL.md ~/.claude/skills/todo-skill/SKILL.md

# Windows
mkdir %USERPROFILE%\.claude\skills\todo-skill
copy skills\todo-skill\SKILL.md %USERPROFILE%\.claude\skills\todo-skill\SKILL.md
```

### Usage

After installation, in any Claude Code session:

```
/todo
```

Or natural language:

```
list todos
what's left
show pending items
complete todos
scan todos
```

### File Structure

```
.claude/skills/todo-skill/
└── SKILL.md          # Skill definition (required)
```

Project root should have:

```
PROJECT_TODOS.md      # Team TODO summary (auto-generated on first use)
```

### License

[MIT](LICENSE)

---

## 中文

Claude Code 项目待办管理插件。

扫描代码内 TODO 注释、同步 `PROJECT_TODOS.md`、提醒未完成项、定位代码位置。

### 功能

- **显式触发**：`/todo-skill`、`/todo`、`看看待办`、`列出 TODO`、`还有什么没做`、`补全 TODO`、`扫一下 TODO`
- **隐式触发**：编辑代码时检测到`预留`、`待定`、`mock`、`等接口`、`FIXME`、`先这样`、`等后端`、`等前端`、`等设计`、`占位`、`占坑`、`待完善`、`待优化`、`硬编码`、`临时方案`、`开发中`等 35+ 关键词，主动提议添加标记
- **双向同步**：代码注释 ↔ `PROJECT_TODOS.md` 对比，发现孤儿条目或未登记项
- **完成追踪**：实现后同步清理代码注释和 `PROJECT_TODOS.md`

### 安装

**通过 Claude Code 插件管理器（推荐）**

```
/plugin marketplace add ksj1995/todo-skill
/plugin install todo-skill@todo-skill
```

**手动安装 - 项目级（仅当前项目可用）**

```bash
# 在项目根目录执行
mkdir -p .claude/skills/todo-skill
cp skills/todo-skill/SKILL.md .claude/skills/todo-skill/SKILL.md
```

**手动安装 - 全局（所有项目可用）**

```bash
# macOS / Linux
mkdir -p ~/.claude/skills/todo-skill
cp skills/todo-skill/SKILL.md ~/.claude/skills/todo-skill/SKILL.md

# Windows
mkdir %USERPROFILE%\.claude\skills\todo-skill
copy skills\todo-skill\SKILL.md %USERPROFILE%\.claude\skills\todo-skill\SKILL.md
```

### 使用

安装后，在任意 Claude Code 会话中：

```
/todo
```

或自然语言：

```
看看待办
还有什么没做
列出 TODO
补全 TODO
扫一下 TODO
```

### 文件结构

```
.claude/skills/todo-skill/
└── SKILL.md          # Skill 定义（唯一必需文件）
```

项目根目录需配合创建：

```
PROJECT_TODOS.md      # 团队待办汇总表（首次使用时自动生成）
```

### 许可证

[MIT](LICENSE)

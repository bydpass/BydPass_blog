# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 仓库性质

这**不是一个代码仓库**，而是一个**纯 Markdown 个人知识库**，用于集中归档来自小红书、网页、视频等来源的收藏与种草信息。

没有 build、test、lint，没有 Node/Python/任何依赖管理器，没有 GitHub Actions。所有操作都是 `git add / commit / push` + 编辑 Markdown。

完整背景见 `README.md`（用户视角）和 `archive/v0.1-spec.md`（v0.1 设计文档，权威 spec）。

## 核心设计原则（spec §2，绝对不要违反）

1. **Inbox First** —— 新内容一律先进 `inbox/YYYY-MM.md`，不要强行分类
2. **Markdown First** —— 所有笔记是 `.md`，不要引入其他格式或工具
3. **Assets Separate** —— 图片/PDF/附件统一进 `assets/{images,files}/`，不混在 Markdown 目录里
4. **Manual Before Automation** —— v0.1 阶段**不要**写脚本、爬虫、Actions、bot
5. 极简优先，新手友好，中文说明

## 工作流（用户的日常动作）

```
新信息  →  inbox/YYYY-MM.md   （按 inbox 模板填写）
            ↓ 批量整理
notes/{products,tools,ideas,tutorials,references}/xxx.md   （按正式笔记模板重写）
            ↓ 过时
archive/   （归档，不删）
```

两套模板都已写在 `README.md` 里，**不要再单独建模板文件**。

## 目录约定

- 每个**空目录**用 `.gitkeep` 占位（git 不追踪空目录，但 GitHub 网页端需要能看到结构）
- 新月份 inbox 直接建 `inbox/2026-06.md` 之类的文件即可，不需要先建 `.gitkeep`
- `archive/v0.1-spec.md` 是 v0.1 spec 的归档版本，**不要修改**；如要演进到 v0.2，新建 `archive/v0.2-spec.md` 或 `SPEC.md`，再更新 README

## 标签

所有标签在 `tags.md` 中统一登记。新增标签前先检查那里是否已有合适的，遵循 `#组别/具体值` 的层级格式。当前四组：`source/`、`type/`、`status/`、`value/`。

## 文件命名

- inbox：`inbox/YYYY-MM.md`
- 素材：`YYYY-MM-DD-short-description.ext`，例 `2026-05-17-xhs-keyboard-layout.png`
- notes：自由命名，建议 kebab-case 英文或简短中文

## 修改时的边界

未经用户明确要求，**不要**做以下事情：

- 新增脚本、Makefile、`package.json`、`.editorconfig`、CI 配置
- 引入任何依赖管理器或框架
- 改动 spec 措辞（`archive/v0.1-spec.md` 已冻结）
- 在 `notes/*/` 子目录里预先放空模板文件
- 给目录加 `README.md` 说明（目录名已自解释）

允许的扩展：补充 README、增删标签、调整 inbox 月份文件、写新笔记、移动旧内容到 archive。

## Commit 风格

参照已有 commit（`Initial commit`、`Manual_Init_pour_cc`）保持简短。当前 repo 在 main 分支直接提交，无 PR 流程。

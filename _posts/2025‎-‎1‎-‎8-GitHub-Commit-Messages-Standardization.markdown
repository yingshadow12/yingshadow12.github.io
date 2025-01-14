---
layout:     post
title:      "GitHub提交信息（commit messages）的规范化"
date:       ‎2025‎-‎1‎-‎8‎ ‏‎9:47:06
author:     "yingshadow12"
header-style: text
catalog:    true
tags:
    - GitHub提交信息
    - GitHub Commit Messages
    - 教程
---
# GitHub提交信息（commit messages）的规范化
在 GitHub 或其他 Git 仓库中，提交信息（commit messages）的规范化是一个重要的最佳实践，有助于团队成员和未来的开发者理解提交的目的。常见的代码规范中，feat、chore、fix 等都是常见的提交类型。它们源自于 Conventional Commits 规范，旨在提高提交信息的可读性和自动化处理能力。

---

## 1. feat（Feature）
- 含义：表示新增一个功能或特性。
- 例子：`feat: add login functionality` 或 `feat: implement dark mode`.
- 解释：当你添加了新的功能或特性时，应该使用 `feat` 来标识。例如，添加一个新的 API 端点或一个新的 UI 组件。

## 2. fix
- 含义：表示修复了一个 bug 或错误。
- 例子：`fix: resolve bug with user authentication` 或 `fix: correct typo in the readme`.
- 解释：当提交的代码是为了修复某个错误或问题时，应使用 fix，它帮助识别哪些提交是解决已知问题的。

## 3. chore
- 含义：表示一些杂项工作，不涉及代码的功能或修复，通常是配置、脚本、工具等。
- 例子：`chore: update dependencies` 或 `chore: improve build scripts`.
- 解释：`chore` 用于标识那些非功能性和非修复性的改动，通常是一些维护性的任务，比如更新项目的依赖，或者改进开发工具和环境的配置。

## 4. docs
- 含义：表示仅修改文档。
例子：`docs: update README with new setup instructions`。
- 解释：当你的提交只涉及文档修改，比如更新 README、API 文档或注释时，使用 `docs`。

## 5. style
- 含义：表示代码格式的更改（不影响功能）。
- 例子：`style: format code according to ESLint rules` 或 `style: update indentation`.
- 解释：这类提交通常不涉及代码逻辑的更改，只是调整代码格式（例如修复缩进、空格、换行等），不会影响到程序的运行效果。

## 6. refactor
- 含义：表示代码重构，不改变功能，仅优化代码结构。
- 例子：`refactor: optimize authentication logic` 或 `refactor: simplify function`.
- 解释：`refactor` 用于标识那些不改变代码功能的改动，通常是为了改善代码的可读性、性能或可维护性。

## 7. perf（Performance）
- 含义：表示对性能的改进。
- 例子：`perf: optimize database queries` 或 `perf: improve image loading speed`.
- 解释：当你对代码进行优化以提升性能时，使用 `perf`。这类提交通常会涉及到性能瓶颈的解决。

## 8. test
- 含义：表示添加或修改测试。
- 例子：`test: add unit tests for authentication` 或 `test: update integration tests`.
- 解释：当提交的更改主要是与测试相关时，如添加、删除或修改测试代码时，使用 `test`。

## 9. build
- 含义：表示构建系统或外部依赖的更改。
- 例子：`build: update webpack config` 或 `build: add Docker support`.
- 解释：与项目构建相关的更改，比如更改构建工具配置、添加构建脚本等，通常使用 `build`。

## 10. ci（Continuous Integration）
- 含义：表示持续集成相关的更改。
- 例子：`ci: add GitHub Actions workflow` 或 `ci: fix Travis CI config`.
- 解释：涉及持续集成配置的更改，通常是在 CI 工具（如 GitHub Actions、Travis CI 等）相关的配置修改。

## 总结
这些关键词帮助区分不同类型的提交，通常在团队开发中会配合自动化工具（如 semantic-release）来生成版本号、生成 changelog 等。规范化的提交信息不仅能提高代码的可读性，还能让发布过程更加自动化，减少人为错误。

---

转载至[blog.darklotus.cn](https://blog.darklotus.cn/notes/githubcommitmessages.html)

# 快速操作：关联 Issue #13 和 PR #30

## 🎯 最简单的方法（推荐）

### 在 Issue #13 中评论

1. 打开：https://github.com/ErlichLiu/Proma/issues/13
2. 滚动到底部评论框
3. 输入并发送：

```markdown
我已经在 PR #30 中实现了这个功能，请审查！
```

**就这么简单！** ✅

---

## 🔄 如果希望 PR 合并时自动关闭 Issue

### 编辑 PR #30 描述

1. 打开：https://github.com/ErlichLiu/Proma/pull/30
2. 点击描述右上角的 "..." → "Edit"
3. 在描述开头添加：

```markdown
Closes #13
```

4. 点击 "Update comment"

**完成！** ✅

---

## 📖 详细教程

查看完整指南：[HOW_TO_LINK_ISSUE_PR.md](./HOW_TO_LINK_ISSUE_PR.md)

---

## 💡 提示

- 使用 `#30` 会自动创建到 PR #30 的链接
- 使用 `Closes #13` 会在 PR 合并时自动关闭 Issue
- 可以在评论、PR 描述、提交消息中使用这些引用

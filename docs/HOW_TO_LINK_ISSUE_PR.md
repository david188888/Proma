# 如何在 GitHub Issue 中关联 Pull Request

本指南教您如何在 GitHub Issue 中提及和关联您的 Pull Request。

## 场景说明

- **Issue #13**: [ErlichLiu/Proma#13](https://github.com/ErlichLiu/Proma/issues/13) - 功能请求：可视化统计
- **PR #30**: [ErlichLiu/Proma#30](https://github.com/ErlichLiu/Proma/pull/30) - 您的实现方案

## 方法一：在 Issue 中添加评论（推荐）

### 步骤：

1. **打开 Issue #13**
   - 访问：https://github.com/ErlichLiu/Proma/issues/13

2. **滚动到页面底部的评论框**

3. **输入以下评论**（选择其中一种）：

   **简单版本：**
   ```markdown
   I've created PR #30 to implement this feature.
   ```

   **详细版本：**
   ```markdown
   I've implemented this feature in PR #30. 
   
   The implementation includes:
   - Token usage tracking for all conversations
   - Cost estimation based on configurable pricing
   - Visualization dashboard with charts and statistics
   
   Please review and provide feedback. Thanks!
   ```

   **中文版本：**
   ```markdown
   我已经在 PR #30 中实现了这个功能。
   
   实现包括：
   - 所有对话的 Token 使用量追踪
   - 基于可配置定价的成本预估
   - 带图表和统计的可视化仪表板
   
   请审查并提供反馈，谢谢！
   ```

4. **点击 "Comment" 按钮**

### 效果：

- ✅ 在 Issue #13 下会显示您的评论
- ✅ GitHub 会自动将 `#30` 转换为 PR #30 的链接
- ✅ 在 PR #30 的页面会显示被 Issue #13 提及

---

## 方法二：在 PR 描述中关联 Issue（自动关闭）

如果您希望 **PR 合并时自动关闭 Issue**，需要在 PR #30 的描述中使用关键词。

### 步骤：

1. **打开 PR #30**
   - 访问：https://github.com/ErlichLiu/Proma/pull/30

2. **点击描述区域右上角的 "..." 按钮**

3. **选择 "Edit"**

4. **在描述开头或结尾添加以下任一行**：

   ```markdown
   Closes #13
   ```
   
   或者：
   ```markdown
   Fixes #13
   ```
   
   或者：
   ```markdown
   Resolves #13
   ```

5. **点击 "Update comment" 保存**

### 效果：

- ✅ PR #30 会自动关联到 Issue #13
- ✅ 当 PR #30 被合并时，Issue #13 会自动关闭
- ✅ 在 Issue #13 页面会显示被 PR #30 引用

---

## 方法三：同时使用两种方法（最佳实践）

**推荐做法：**

1. **在 PR #30 描述中**添加：
   ```markdown
   Closes #13
   ```

2. **在 Issue #13 中**添加评论：
   ```markdown
   I've implemented this in PR #30. Please review!
   ```

这样可以：
- ✅ 在 Issue 讨论区通知所有关注者
- ✅ 建立自动关闭关联
- ✅ 方便项目维护者追踪进度

---

## GitHub 关键词说明

GitHub 支持的自动关闭关键词（不区分大小写）：

| 关键词 | 说明 |
|--------|------|
| `close`, `closes`, `closed` | 关闭 Issue |
| `fix`, `fixes`, `fixed` | 修复 Issue |
| `resolve`, `resolves`, `resolved` | 解决 Issue |

**使用格式：**
- 同一仓库：`Closes #13`
- 跨仓库：`Closes ErlichLiu/Proma#13`

---

## 快速操作链接

- 📝 [在 Issue #13 添加评论](https://github.com/ErlichLiu/Proma/issues/13#new_comment_field)
- ✏️ [编辑 PR #30 描述](https://github.com/ErlichLiu/Proma/pull/30)
- 📚 [GitHub 官方文档：链接 PR 和 Issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue)

---

## 注意事项

⚠️ **重要提示：**

1. 确保您已登录 GitHub
2. 您需要有评论权限（通常任何人都可以评论公开仓库的 Issue）
3. 如果 Issue 或 PR 在私有仓库，您需要有访问权限
4. 使用 `#数字` 格式时，确保您在正确的仓库中操作

---

_本指南创建于 2026-02-18_

# 上游功能追踪：可视化统计

追踪上游仓库 [ErlichLiu/Proma](https://github.com/ErlichLiu/Proma) 中关于可视化统计功能的开发进展。

## Issue #13 → PR #30 关联

**功能请求**: [Issue #13 - Visualize usage statistics and recent conversation token consumption](https://github.com/ErlichLiu/Proma/issues/13)

**实现方案**: [PR #30 - feat: 添加 Token 使用量统计功能](https://github.com/ErlichLiu/Proma/pull/30)

## 功能范围

### 用户需求 (Issue #13)
- 总使用量统计（日/月维度）
- 近期对话的 Token 消耗明细
- 可视化图表展示，便于监控和优化

### 实现内容 (PR #30)

**数据层**
- `ChatMessage` 添加 `usage` 字段持久化
- Provider 适配器解析 SSE 流中的 usage 事件
- `usage-service` 提供统计聚合和成本预估

**界面层**
- UsageSettings 统计页面（科技蓝风格，支持暗/亮主题）
- 总览卡片：总 Token、对话数、预估成本
- 趋势图：7/30/90 天视图
- 饼图：模型使用量分布
- 最近对话列表及详情

**供应商支持**
- Anthropic、OpenAI、Google 等主流 Provider
- 可配置价格表用于成本预估

## 如何关联 Issue 和 PR

如果您想在 Issue #13 中提及 PR #30，请查看操作指南：
- 📖 [完整教程](./HOW_TO_LINK_ISSUE_PR.md)
- ⚡ [快速参考](./QUICK_REFERENCE.md)

## 同步计划

待上游 PR #30 合并后，评估同步到本仓库的可行性。

---

_追踪建立: 2026-02-18_

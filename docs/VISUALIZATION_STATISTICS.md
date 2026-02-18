# 可视化统计功能说明

## 概述

本文档说明了 Proma 项目中可视化统计功能的需求来源和实现方案。

## 相关 Issue 和 Pull Request

### 上游仓库 (ErlichLiu/Proma)

#### Issue #13: Feature request - 可视化使用统计
- **标题**: Feature request: Visualize usage statistics and recent conversation token consumption
- **链接**: https://github.com/ErlichLiu/Proma/issues/13
- **创建日期**: 2026-02-11
- **提出者**: @david188888

**功能需求**:
1. 提供一个汇总面板或可视化界面，用于追踪使用统计信息
2. 显示最近对话的 Token 消耗情况
3. 按时间维度（日/月）统计总使用量
4. 展示最近对话或会话的 Token 消耗明细
5. 提供可视化图表，便于解读和管理使用情况

#### PR #30: 实现 Token 使用量统计功能
- **标题**: feat: 添加 Token 使用量统计功能
- **链接**: https://github.com/ErlichLiu/Proma/pull/30
- **创建日期**: 2026-02-18
- **提交者**: @david188888
- **状态**: Open

**实现方案**:

##### 数据统计
- 收集每个对话的 Token 使用量（输入/输出）
- 支持 Anthropic、OpenAI、Google 等主流 Provider
- 按日、按模型维度的使用量聚合
- 基于可配置价格表的 API 成本预估

##### 可视化界面
- 全新的 UsageSettings 统计页面
- 采用科技蓝设计风格，支持深色/浅色主题
- 数据总览卡片（总 Token、对话数、预估成本）
- 趋势图表（7/30/90 天）
- 模型使用量分布饼图
- 最近对话列表及详情

##### 技术实现
- `ChatMessage` 新增 `usage` 字段持久化存储
- Provider 适配器解析 SSE 流中的 usage 事件
- `usage-service` 提供统计计算和数据聚合
- `usage-atoms` 管理统计状态

##### 修改的文件
- **新增**：
  - `usage-service.ts` - 统计服务
  - `usage-atoms.ts` - 状态管理
  - `UsageSettings.tsx` - 可视化界面组件
  - `usage.ts` - 类型定义
- **修改**：
  - `ipc.ts` - IPC 通道注册
  - `preload/index.ts` - API 桥接
  - 各 Provider 适配器 - usage 数据解析
  - `chat-service.ts` - 消息持久化

## 关联关系

PR #30 是对 Issue #13 功能需求的完整实现：

| 需求项 | 实现方案 |
|-------|---------|
| 追踪使用统计信息 | usage-service 收集和聚合统计数据 |
| Token 消耗情况 | ChatMessage 新增 usage 字段，持久化存储 |
| 时间维度统计 | 支持 7/30/90 天的趋势图表 |
| Token 消耗明细 | 最近对话列表展示详细的 usage 信息 |
| 可视化图表 | UsageSettings 页面提供多种图表展示 |
| 成本预估 | 基于可配置价格表计算预估成本 |

## 测试验证

- [ ] 测试各 Provider 的 usage 数据正确解析
- [ ] 测试统计页面数据显示正确
- [ ] 测试定价设置保存和生效
- [ ] 测试深色/浅色主题切换

## 后续计划

1. 等待上游仓库 PR #30 合并
2. 如果有改进建议，可以在 Issue #13 中继续讨论
3. 合并后在主分支中测试和验证功能

## 参考资源

- [上游仓库](https://github.com/ErlichLiu/Proma)
- [Issue #13](https://github.com/ErlichLiu/Proma/issues/13)
- [PR #30](https://github.com/ErlichLiu/Proma/pull/30)

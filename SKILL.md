---
name: daily-planner
description: Plan daily work schedules for Siemens Beijing employees based on fixed time blocks and task priorities. Use when the user asks to plan their day, schedule tasks, organize workload, or mentions daily planning, task arrangement, time management, or work schedule.
---

# Daily Planner

Plan each workday with scientific time blocking and priority-based task allocation for Siemens Beijing office.

## Fixed Schedule

```
08:45  Arrive at office
09:00-09:20  早会 (Morning standup)
09:30-11:30  深度工作时段 A (2 hours)
11:30-12:00  休息缓冲
12:00-13:00  午餐 (在公司用餐)
13:00-14:30  深度工作时段 B — 团队Silence Time (1.5 hours, 无会议)
14:30-15:00  邮件/消息集中处理窗口
15:00-17:30  深度工作时段 C (2.5 hours, 可安排会议/协作)
17:30-18:00  班会 (Evening standup)
18:00  下班
```

## Recurring Sprint & Monthly Meetings

Sprint周期 = 2周, 以下会议为固定不可移动:

| 会议 | 频率 | 时间 | 占用时段 | 备注 |
|------|------|------|----------|------|
| Sprint Plan | 隔周周一 | 15:00-16:00 (1h) | 时段C | 时段C剩余1.5h |
| Sprint Review+Retro | 隔周周四 | 15:00-16:30 (1.5h) | 时段C | 时段C剩余1h |
| 月度分享会 | 每月第四周周三 | 13:00-15:00 (2h) | ⚠️ 占Silence Time+邮件窗口 | Silence Time被覆盖 |

**Sprint节奏**: Plan在Week A周一, Review+Retro在Week B周四
**基准日期**: 最近一次Sprint Plan = 2026-06-08 (周一); 下次Sprint Review = 2026-06-18 (周四)

### Sprint日和月度分享日的可用时间变化

| 特殊日 | 时段A | 时段B | 邮件窗口 | 时段C | 专注时间 | 总可用 | 总变化 |
|--------|-------|-------|----------|-------|----------|--------|--------|
| Sprint Plan周一 | 2h | 1.5h | 0.5h | 1.5h | 5h | 5.5h | -1h |
| Sprint Review周四 | 2h | 1.5h | 0.5h | 1h | 4.5h | 5h | -1.5h |
| 月度分享周三 | 2h | ❌ | ❌ | 2.5h | 4.5h | 4.5h | -2h |
| 正常日 | 2h | 1.5h | 0.5h | 2.5h | 6h | 6.5h | 基准 |

专注时间 = A+B+C (排除邮件窗口)；总可用 = A+B+C+邮件窗口

## Available Work Time

### How 6.5h is calculated from 8h workday

```
9:00-18:00 = 9h (total at office)
- Lunch    = 1h
= 8h work time
- 早会      = 20min (fixed meeting)
- 早会后过渡 = 10min (9:20-9:30, switch to work mode)
- 休息缓冲  = 30min (11:30-12:00, wrap-up / rest)
- 班会      = 30min (fixed meeting)
= 6.5h total available
= 6h focus time + 0.5h email window
```

### Time blocks

| Block | Time | Duration | Character |
|-------|------|----------|-----------|
| A | 09:30-11:30 | 2h | 深度专注，大脑最清醒，适合高认知任务 |
| B | 13:00-14:30 | 1.5h | 团队Silence Time，无会议干扰，黄金深度时段 |
| C | 15:00-17:30 | 2.5h | 下午冲刺期，适合协作、会议、收尾任务 |

**Focus time (A+B+C): 6h/day** — 用于P0/P1深度工作和P2/P3任务
**Email window**: 14:30-15:00 (30min) — 集中处理邮件和消息，避免碎片化打断
**Total work time (Focus+Email): 6.5h/day**

## Sprint Task Tracking

Each Sprint (2 weeks) defines core tasks during Sprint Planning. These Sprint tasks are the **north star** for daily planning.

### Sprint Task File

Store Sprint tasks in `sprint-tasks.md` (same directory as this skill). Format:

```markdown
# Sprint [序号] — [起始日期] ~ [结束日期]

## 🎯 Sprint Goals
- [核心目标1]
- [核心目标2]

## 📋 Sprint Task List
| # | 任务 | 估时 | 已投入 | 状态 | 目标完成日 | 备注 |
|---|------|------|--------|------|------------|------|
| 1 | ...  | 4h   | 2h     | 🔄进行中 | 周三 | ... |
| 2 | ...  | 2h   | 0h     | ⬜未开始 | 周四 | ... |
| 3 | ...  | 1h   | 1h     | ✅完成  | —   | ... |

## ⏳ 未完成滚动任务 (from 上个Sprint)
| # | 任务 | 滚动天数 | 优先级调整 | 备注 |
|---|------|----------|------------|------|
```

Task status: ✅完成 | 🔄进行中 | ⬜未开始 | ⏳滚动 | ❌阻塞

### Sprint-Daily Integration Flow

When doing daily planning, ALWAYS follow this order:

1. **读取Sprint任务文件** — Check `sprint-tasks.md` for current Sprint status
2. **计算Sprint进度** — Show: 已完成/总任务, 已投入/总估时, 剩余工作日
3. **识别今日Sprint任务** — Which Sprint tasks should be worked on today?
4. **合并每日任务** — Sprint tasks + user's daily ad-hoc tasks → unified priority list
5. **标注来源** — In schedule output, tag each task: `[Sprint]` or `[Ad-hoc]`
6. **更新Sprint文件** — After daily review, update task status and hours in `sprint-tasks.md`

### Sprint Progress Bar

Include this in every daily plan output:

```
📊 Sprint进度: ████████░░░░ 60% (3/5 tasks) | 剩余6个工作日 | 已投入12h/估20h
⚠️ 风险: 任务4估时4h但仅剩1天深度时段, 建议今天优先推进
```

### Sprint Plan Day Protocol

On Sprint Plan Monday (隔周周一15:00-16:00), **proactively ask the user** for Sprint tasks:

**Step 1: 主动询问** — After detecting today is a Sprint Plan day, ask:
> "今天是Sprint Plan日！请告诉我这个Sprint的核心任务有哪些？包括：
> 1. 每个任务的名称和预估时长
> 2. 这个Sprint的主要目标
> 3. 上个Sprint有没有未完成需要滚动的任务？"

**Step 2: 记录到sprint-tasks.md** — Create/update the file with:
- Sprint Goals
- Sprint Task List (with estimates)
- Carry-over tasks from last Sprint

**Step 3: 任务拆分** — Help user decompose tasks >4h into 2h sub-tasks

**Step 4: 分布规划** — Distribute tasks across the 10 working days:
- Week A: 尽量前半周推进高难度Sprint任务
- Week B: 预留Review前2天做收尾和准备
- Sprint Review周四前必须完成所有Sprint P0任务
- Total Sprint task estimates should not exceed ~40h

**Step 5: 生成Sprint概览** — Output a Sprint-level summary:
```markdown
🎯 Sprint [X] 概览
📊 总估时: Xh / 可用容量: ~46h | 负荷: 正常/偏高/过载
📅 关键节点: [Review日期]
⚠️ 风险任务: [如有]
```

### Sprint Review Day Protocol

On Sprint Review Thursday (隔周周四15:00-16:30), before the meeting:
1. Summarize Sprint completion status from `sprint-tasks.md`
2. Flag any ❌阻塞 tasks with reasons
3. Identify ⏳滚动 tasks that need to carry over to next Sprint
4. Prepare 3 talking points for the Review: 亮点, 阻塞, 改进

## Planning Steps

1. **收集任务** — Ask the user to list today's tasks (or read from a task file)
2. **分类优先级** — Apply Eisenhower matrix:
   - 🔴 P0: 紧急且重要 → 必须今天完成
   - 🟡 P1: 重要不紧急 → 优先安排在深度时段A
   - 🔵 P2: 紧急不重要 → 安排在工作时段B/C快速处理
   - ⚪ P3: 不紧急不重要 → 如有时间再做，或推迟
3. **估算时间** — For each P0/P1 task, estimate duration (30min increments)
4. **分配时间块** — Fill time blocks following allocation rules below
5. **留出缓冲** — Reserve 15min buffer between tasks; keep 1 slot open for突发事项
6. **生成日程表** — Output the day's schedule in the format shown below

## Allocation Rules

- **时段A (09:30-11:30)**: P0 and P1 tasks only. Solo deep-work preferred (写方案、分析数据、写代码)
- **时段B (13:00-14:30)**: P0/P1 deep continuation. **This is Silence Time — never schedule meetings here** (except月度分享日, 见下方). This block equals时段A in focus quality
- **14:30-15:00**: Email/message batch processing. Quick P2 items can also be handled here
- **时段C (15:00-17:30)**: Meetings/collaboration + P2/P3 tasks + 收尾today's P0. **On Sprint Plan周一: only 16:00-17:30可用; On Sprint Review周四: only 16:30-17:30可用**
- **Rule**: Never schedule more than 90min of continuous deep work — insert 10-15min micro-breaks
- **Rule**: Always leave at least one 30min slot unfilled for unexpected tasks
- **Rule**: All meetings should be clustered in时段C unless user specifies otherwise

## Output Format

Generate the schedule as a clear table:

```markdown
# 📅 [日期] 工作日程

## 📊 Sprint进度
[进度条 + 统计]

## 任务清单 & 优先级
| # | 任务 | 来源 | 优先级 | 预估时长 | Sprint关联 | 备注 |
|---|------|------|--------|----------|------------|------|
| 1 | ...  | [Sprint] | P0   | 1h       | Sprint#1   | ...  |
| 2 | ...  | [Ad-hoc] | P1   | 2h       | —          | ...  |

## 时间块安排
| 时间 | 任务 | 优先级 | 来源 | 备注 |
|------|------|--------|------|------|
| 09:30-10:30 | 任务1 [Sprint] | P0 | Sprint | 深度专注 |
| 10:30-10:45 | 🧘 微休息 | — | — | 喝水、走动 |

## 今日重点
- 必须完成: [P0任务列表]
- 优先推进: [P1任务列表]
- 如有空余: [P2/P3任务列表]

## Sprint今日聚焦
- 今日Sprint任务: [哪些Sprint任务今天推进]
- Sprint风险提醒: [是否有延误风险]

## 复盘提醒
下班前花5min回顾: 完成了什么? 未完成的原因? 明天需调整什么?
```

## Smart Suggestions

When generating the schedule, also provide:
- **能量匹配**: 高认知任务 → 时段A或B (两个黄金深度时段); 日常事务 → 时段C
- **Silence Time利用**: 13:00-14:30是全天第二个无干扰窗口，优先安排需要连续思考的P0/P1
- **上下文切换成本**: 相似类型任务尽量连续安排，减少切换
- **截止日期提醒**: 标注本周内需交付的任务，优先排入近两天
- **会议冲突处理**: 如用户提到已有预定会议，将其标记为固定块，剩余时间再分配
- **邮件纪律**: 提醒用户在深度时段A/B关闭邮件通知，仅在14:30-15:00集中处理
- **Sprint日识别**: 规划前先确认当天是否为Sprint Plan周一 / Sprint Review周四 / 月度分享周三，并调整可用时间
- **月度分享日调整**: 周三有月度分享时(13:00-15:00)，Silence Time和邮件窗口被完全覆盖，P0/P1任务需全部压缩到时段A(2h)和时段C剩余(2.5h)
- **Sprint优先原则**: 当日任务排期时，Sprint任务优先于Ad-hoc任务安排在黄金深度时段(A/B)
- **Sprint进度预警**: 如果Sprint进度落后于时间消耗(如已过60%时间但只完成30%任务)，主动预警并建议调整
- **Sprint任务拆分**: 如果一个Sprint任务>4h，建议拆分为多个2h子任务分布在不同天

## Task Rolling

When tasks are not completed today:
1. Mark them with ⏳ in the schedule output
2. At the next day's planning, automatically carry over ⏳ tasks and re-prioritize
3. ⏳ tasks from yesterday get +1 urgency level (P1→P0, P2→P1)
4. If a task has been rolled 3+ days, flag it: "是否需要重新评估此任务的必要性？"
5. **Sprint任务滚动**: ⏳ Sprint任务在Sprint Review前必须完成或显式carry-over到下一个Sprint, 不可静默丢失

## Additional Resources

- For weekly planning strategy and task management methodology, see [reference.md](reference.md)
- For Sprint task file template, see the Sprint Task File section above

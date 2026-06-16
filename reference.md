# Daily Planner Reference

## Sprint Task Management

### Sprint Lifecycle

```
Sprint Plan (周一15:00)
    ↓
Week A (周一→周五): 推进高难度Sprint任务
    ↓
Week B (周一→周三): 收尾 + Review准备
    ↓
Sprint Review+Retro (周四15:00)
    ↓
下个Sprint Plan (下周一15:00)
```

### Sprint Task Decomposition

When Sprint Planning identifies a task >4h, decompose it:

| 原始任务 | 估时 | 拆分 |
|----------|------|------|
| 完成XX方案 | 6h | 1. 框架设计(2h) 2. 内容填充(2h) 3. 评审修改(2h) |
| 开发XX功能 | 8h | 1. 技术方案(2h) 2. 核心开发(4h) 3. 测试修复(2h) |

**Principle**: Each sub-task should be completable within a single deep work block (1-2h). This makes daily scheduling precise.

### Sprint Time Budget

A 2-week Sprint has ~60h total focus capacity (6h × 10 days). But effective Sprint work time is less:

| Item | Duration | Reason |
|------|----------|--------|
| 总容量 | 60h | 6h × 10天 |
| Sprint Plan会议 | -1h | Week A周一 |
| Sprint Review会议 | -1.5h | Week B周四 |
| 月度分享(可能) | -1.5h | 第四周周三 |
| 每日留白(buffer) | -5h | 0.5h × 10天 |
| 每日邮件窗口 | -5h | 0.5h × 10天 |
| **实际Sprint可用** | **~46h** | |

Planning rule: **Total Sprint task estimates should not exceed ~40h** (keep 6h buffer for ad-hoc tasks)

### Sprint Health Indicators

During daily planning, assess Sprint health:

| Indicator | Healthy | Warning | Critical |
|-----------|---------|---------|----------|
| 任务完成率 vs 时间消耗 | 完成≥时间% | 完成<时间% 10pp | 完成<时间% 20pp |
| 阻塞任务数 | 0 | 1 | ≥2 |
| 滚动任务数 | 0-1 | 2-3 | ≥4 |
| 剩余估时 vs 剩余天数 | 估时<剩余容量 | 估时≈剩余容量 | 估时>剩余容量 |

**When Critical**: Suggest user to
1. Drop P3 Sprint tasks
2. Negotiate P2 scope reduction
3. Request help for ❌阻塞 tasks
4. Carry over P1 to next Sprint with explicit agreement

### Sprint Review Preparation Checklist

Before Sprint Review (周四15:00), generate:

```markdown
## Sprint Review 准备

### ✅ 已完成
- [任务1] (Xh投入/Yh估时)
- [任务2] ...

### 🔄 进行中 (需carry-over)
- [任务3] 剩余Zh, 原因: ...

### ❌ 阻塞
- [任务4] 阻塞原因: ..., 需要谁协助: ...

### 💡 Retrospective要点
- 做得好的: ...
- 需改进的: ...
- 下个Sprint调整: ...
```

---

## Weekly Planning Strategy

### Monday Kickoff (每周一)

At the start of each week, help the user review:
1. **Sprint任务状态** — Read `sprint-tasks.md`, review current Sprint progress
2. **本周目标** — What are the key outcomes this week? (Align with Sprint tasks)
3. **截止日期清单** — List all deliverables with due dates
4. **会议预排** — Known meetings this week (fixed blocks)
5. **能量预算** — Estimate overall workload: light / normal / heavy

**If this Monday is a Sprint Plan Monday**: Skip regular kickoff, follow Sprint Plan Day Protocol instead

### Weekly Time Budget

With ~6h focus time × 5 days = **30h total weekly focus capacity**

- Heavy week (>24h planned): 每天必须留30min buffer, 拒绝新增任务
- Normal week (14-24h): 正常安排, 保持弹性
- Light week (<14h): 主动寻找P1任务推进, 不要浪费深度时段

---

## Task Prioritization Deep Guide

### Eisenhower Matrix Applied to Office Work

| | 紧急 | 不紧急 |
|---|---|---|
| **重要** | P0: 立即做 | P1: 计划做 |
| **不重要** | P2: 快速做/委托 | P3: 考虑删除 |

### Siemens Office Common Task Types

**P0 典型场景**:
- 今天必须交付的报告/方案
- 上级紧急交办的事项
- 系统故障/流程阻塞需要立即解决

**P1 典型场景**:
- 本周需推进的项目里程碑
- 需要深度思考的策略/分析工作
- 长期重要的技能学习/知识积累

**P2 典型场景**:
- 回复非紧急邮件/消息
- 日常流程性审批
- 可委托给同事的事项

**P3 典型场景**:
- 无明确产出的会议
- 可推迟的信息搜集
- 低优先级的流程优化想法

---

## Time Block Methodology

### Why 90-Minute Deep Work Limit?

Research shows cognitive performance drops significantly after 90 minutes of sustained focus. Enforcing micro-breaks (10-15min) maintains:
- Higher sustained quality of work
- Reduced error rate in the second half of the block
- Better transition between different task types

### Micro-Break Activities

Effective 10-15 minute breaks:
- 🧘 Physical: 站起来走动、伸展、去茶水间
- 👁️ Visual: 看窗外远处，放松眼部
- 🧠 Mental: 简单整理桌面/笔记，不涉及新问题思考
- ⚠️ Avoid: 刷手机/社交媒体 (会造成额外认知负荷)

### Context Switching Cost

Switching between different task types costs ~15-23min of mental reorientation. Strategies:
- **Batch similar tasks**: 把所有邮件处理放在一起, 所有数据分析放在一起
- **Same tool cluster**: 同一工具链的任务连续做 (e.g., 连续写几个PPT页面)
- **Energy descent**: 从高认知→低认知依次排列, 不要反复升降

---

## Meeting Handling Strategy

### Fixed Meeting Blocks

These are immovable and already occupy schedule:
- 09:00-09:20 早会 (每天)
- 17:30-18:00 班会 (每天)
- Sprint Plan: 隔周周一 15:00-16:00
- Sprint Review+Retro: 隔周周四 15:00-16:30
- 月度分享会: 每月第四周周三 13:00-15:00

### Sprint Cycle Details

**2-week Sprint cycle, alternating weeks:**

- **Week A (Sprint开始周)**: 周一有Sprint Plan (15:00-16:00)
- **Week B (Sprint结束周)**: 周四有Sprint Review+Retro (15:00-16:30)

**Date calculation from baseline:**
- Baseline Sprint Plan: 2026-06-08 (Mon)
- Sprint Plan dates: 2026-06-08, 2026-06-22, 2026-07-06, 2026-07-20, ... (every 2 weeks Monday)
- Sprint Review dates: 2026-06-18, 2026-07-02, 2026-07-16, 2026-07-30, ... (every 2 weeks Thursday, offset 10 days from Plan)

**How to determine which week type today is:**
1. Calculate days since last known Sprint Plan baseline (2026-06-08)
2. Divide by 14 to get the Sprint number
3. If remainder 0-6 → Week A; if remainder 7-13 → Week B
4. Week A Monday = Sprint Plan day; Week B Thursday = Sprint Review day

### Monthly Sharing Details

**月度分享会**: 每月第四周的周三, 13:00-15:00 (2h)

**Determine "第四周"**: Find the 4th Wednesday of the month.
- June 2026: 4th Wednesday = June 24 (13:00-15:00)
- July 2026: 4th Wednesday = July 22 (13:00-15:00)

**⚠️ Special impact**: Monthly sharing完全覆盖Silence Time (13:00-14:30) 和邮件窗口 (14:30-15:00):
- 时段B = ❌ 被月度分享覆盖
- 邮件窗口 = ❌ 被月度分享覆盖
- 有效可用时间 = 时段A (2h) + 时段C (2.5h) = **仅4.5h** (比正常日少1.5h)
- Planning advice: 月度分享日当天只安排1-2个P0任务, P1任务提前到前一天完成或推迟到后一天

### Silence Time (13:00-14:30)

This is a **team-wide commitment**: no meetings are scheduled during 13:00-14:30.

Implications for planning:
- This block has the same focus quality as时段A — treat it as equally valuable
- Never suggest scheduling any meeting here, even if the user mentions a time conflict
- Best use: continuation of deep P0/P1 work started in时段A, or standalone deep tasks
- If a meeting MUST happen at this time (客户/上级强制), flag it explicitly: "⚠️ 此会议侵占了Silence Time"
- **月度分享日例外**: 每月第四周周三的月度分享(13:00-15:00)是唯一合规的Silence Time覆盖, 不可拒绝

### Other Meetings

When the user mentions additional meetings:
1. Mark the meeting as a fixed block in the schedule
2. Assess: Is this meeting truly needed? (Suggest declining P3-level meetings)
3. For necessary meetings: Reserve 5min pre-meeting prep + 5min post-meeting notes
4. Try to cluster meetings in时段C (15:00-17:30) to preserve deep work time

### Meeting-Free Blocks

Encourage the user to protect时段A (09:30-11:30) and时段B (13:00-14:30) as **meeting-free zones**. These are the two most valuable focus blocks of the day, totaling 3.5h of uninterrupted deep work.

### Email/Message Window (14:30-15:00)

This 30min window sits between Silence Time and时段C:
- Purpose: Batch process all emails and messages accumulated during deep work blocks
- Rule: During时段A and时段B, email notifications should be muted/suppressed
- This window can also handle quick P2 items (审批、回复确认等) that take <10min each
- If no emails/messages to process, use this time as a transition buffer or early start for时段C tasks

---

## Daily Review Template

At the end of each day (before班会), prompt a 5-minute review:

```markdown
## 今日复盘
- ✅ 已完成: [列出完成的任务]
- ❌ 未完成: [列出未完成的任务及原因]
- 🔄 进行中: [列出持续推进的任务]
- 📝 明日调整: [基于今天的情况,明天需改变什么]
- 💡 今日洞察: [今天有什么发现/学习]
```

### Common Review Insights

- 如果P0经常未完成 → 可能P0定义过宽, 或时间估算不足
- 如果经常被突发事项打断 → buffer slot不够, 需要增加到1h
- 如果时段A效率低 → 检查是否有不当的会议入侵
- 如果整体任务太多 → 需要在周级别做减法, 与上级沟通优先级

---

## Handling Overload

When the user says "任务太多" or the planned tasks exceed available time:

### Step 1: Acknowledge
确认负荷情况, 不盲目塞更多任务

### Step 2: Triage
- 列出所有P0, 确认哪些真的必须今天完成
- 推迟到明天: 部分P1可以延后1天
- 委托: P2是否有同事可以帮忙?

### Step 3: Negotiate
- 如果P0数量 > 可用时间 → 建议与上级沟通优先级
- 提供"如果只能完成3件事,应该是哪3件?"的决策框架

### Step 4: Protect
- 即使超载, 仍然保留1个30min buffer slot
- 仍然保留微休息 (10min), 否则效率反而下降

---

## Task Rolling Mechanism

### Why Task Rolling?

In a busy office environment, not every task gets completed each day. Without a systematic rolling mechanism, unfinished tasks silently pile up and cause stress or get forgotten.

### Rolling Rules

| Situation | Action |
|-----------|--------|
| P0未完成 | ⏳标记, 优先级不变(P0仍为P0), 明天必须排入时段A或B |
| P1未完成 | ⏳标记, +1紧迫度(P1→P0), 明天优先安排 |
| P2未完成 | ⏳标记, +1紧迫度(P2→P1), 但仍可灵活安排 |
| P3未完成 | 不标记, 下次规划时重新评估是否仍需做 |

### Rolling Ceiling

- 同一个任务滚动超过 **3天**: Flag "是否需要重新评估此任务的必要性？"
- 可能的原因: 任务定义不清、实际不需做、需要拆分成更小任务、需要委托给他人

### Next-Day Planning Integration

When starting a new day's planning:
1. First list all ⏳ rolled tasks from yesterday
2. Re-prioritize them with +1 urgency applied
3. Then add any new tasks the user mentions
4. Generate the combined schedule
5. Remind the user: "今天有[X]项昨天的滚动任务, 已重新排入日程"

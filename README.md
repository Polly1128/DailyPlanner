# Daily Planner

A Qoder Agent Skill for scientific daily work planning with Sprint task tracking and time-blocking methodology. Designed for teams running 2-week Sprint cycles with dedicated focus time and recurring meeting patterns.

## Features

- **Time-Blocking Methodology** — Divides each workday into focused time blocks based on cognitive energy levels
- **Sprint-Daily Integration** — Connects 2-week Sprint goals with daily task execution, providing real-time progress tracking
- **Eisenhower Matrix** — Prioritizes tasks into P0-P3 levels for optimal allocation
- **Silence Time Protection** — Guards the team's 13:00-14:30 no-meeting window as a golden deep-work block
- **Task Rolling Mechanism** — Systematically carries over unfinished tasks with automatic urgency escalation
- **Sprint Health Monitoring** — Proactively alerts when Sprint progress falls behind time consumption
- **Special Day Handling** — Automatically adjusts available time for Sprint Plan/Review days and Monthly Sharing days

## Daily Schedule Template

```
08:45         Arrive at office
09:00-09:20   Morning Standup (早会)
09:30-11:30   Deep Work Block A (2h) — High cognitive tasks
11:30-12:00   Buffer / Break
12:00-13:00   Lunch
13:00-14:30   Deep Work Block B — Silence Time (1.5h) — No meetings
14:30-15:00   Email/Message Batch Processing
15:00-17:30   Work Block C (2.5h) — Meetings, collaboration, wrap-up
17:30-18:00   Evening Standup (班会)
18:00         End of day
```

## Available Time Calculation

```
9:00-18:00 = 9h (total at office)
- Lunch                    = 1h
= 8h work time
- Morning standup           = 20min (fixed meeting)
- Post-standup transition    = 10min (9:20-9:30, switch to work mode)
- Morning buffer             = 30min (11:30-12:00, wrap-up / rest)
- Evening standup            = 30min (fixed meeting)
= 6.5h total available = 6h focus time + 0.5h email window
```

| Day Type | Focus Time | Total Available | Change from Normal |
|----------|------------|-----------------|--------------------|
| Normal day | 6h | 6.5h | Baseline |
| Sprint Plan Monday | 5h | 5.5h | -1h focus |
| Sprint Review Thursday | 4.5h | 5h | -1.5h focus |
| Monthly Sharing Wednesday | 4.5h | 4.5h | -1.5h focus (Silence Time overridden) |

## Sprint Integration

### Sprint Plan Day (Every 2 Weeks Monday)

On Sprint Plan day, the agent proactively asks:
1. What are the core Sprint tasks and their time estimates?
2. What are the main Sprint goals?
3. Any unfinished tasks to carry over from last Sprint?

Then it:
- Records tasks in `sprint-tasks.md`
- Decomposes tasks >4h into 2h sub-tasks
- Distributes tasks across 10 working days
- Generates a Sprint overview with health assessment

### Sprint Review Day (Every 2 Weeks Thursday)

Before the Review meeting, the agent:
- Summarizes Sprint completion status
- Flags blocked tasks
- Identifies carry-over tasks
- Prepares 3 talking points: Highlights, Blockers, Improvements

### Sprint Health Indicators

| Indicator | Healthy | Warning | Critical |
|-----------|---------|---------|----------|
| Completion vs Time % | Done ≥ Time% | Behind 10pp | Behind 20pp |
| Blocked tasks | 0 | 1 | ≥2 |
| Rolling tasks | 0-1 | 2-3 | ≥4 |

## Task Prioritization (Eisenhower Matrix)

| | Urgent | Not Urgent |
|---|---|---|
| **Important** | 🔴 P0: Do today | 🟡 P1: Schedule in deep blocks |
| **Not Important** | 🔵 P2: Batch process | ⚪ P3: Consider dropping |

## File Structure

```
daily-planner/
├── SKILL.md           # Main skill instructions
├── reference.md       # Detailed methodology reference
├── sprint-tasks.md    # Current Sprint task tracking
└── README.md          # This file
```

## Recurring Meetings

| Meeting | Frequency | Time | Impact |
|---------|-----------|------|--------|
| Sprint Plan | Biweekly Monday | 15:00-16:00 | Block C -1h focus |
| Sprint Review+Retro | Biweekly Thursday | 15:00-16:30 | Block C -1.5h focus |
| Monthly Sharing | 4th week Wednesday | 13:00-15:00 | Silence Time + Email window overridden (-1.5h focus) |

## Installation

Copy this directory to your Qoder skills folder:

```
~/.qoder/skills/daily-planner/
```

## Usage

Once installed, simply tell the agent:

- "帮我规划今天的工作" (Plan my day)
- "今天任务太多了，帮我安排" (Too many tasks, help me schedule)
- "规划一下明天" (Plan tomorrow)

The agent will automatically:
1. Check the current Sprint status
2. Ask for today's tasks
3. Prioritize and allocate to time blocks
4. Generate a complete daily schedule with Sprint progress

## License

MIT

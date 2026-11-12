# FIFO-vs-RM-vs-EDF-Real-Time-Scheduling-Algorithms-Compared-in-Under-2-Minutes

A short, visual comparison of three classic real-time scheduling algorithms — **FIFO**, **Rate Monotonic (RM)**, and **Earliest Deadline First (EDF)** — on the same set of tasks.

**Duration:** ~2 minutes (12 clips, ~10 seconds each)
**Language:** English
**Background music:** Original 2-minute electronic track, made for this video

## What you'll learn

- How each algorithm decides which task runs first
- Why FIFO can miss deadlines, even though it is simple
- Why RM works well for periodic tasks
- Why EDF is optimal for meeting deadlines
- Which algorithm to choose for which kind of system

## The three algorithms

### 1. FIFO — First In, First Out

Tasks run in the order they arrive. The first task in the queue runs first, with no priority and no preemption.

- **Pros:** Very simple to implement and understand
- **Cons:** A long task can block an urgent task behind it. FIFO gives no deadline guarantee.

### 2. RM — Rate Monotonic

A fixed-priority algorithm for periodic tasks. The task with the shortest period gets the highest priority, and priorities never change at runtime.

- **Pros:** Simple, predictable, and well suited to periodic tasks
- **Cons:** Not always optimal. Some task sets that EDF can schedule, RM cannot.

### 3. EDF — Earliest Deadline First

A dynamic-priority algorithm. The task with the nearest deadline always runs first, and priorities change as deadlines approach.

- **Pros:** Optimal for meeting deadlines — if any algorithm can schedule the task set, EDF can
- **Cons:** More complex at runtime, and harder to predict under overload

## Worked example

The video uses the same three tasks, T1, T2, and T3, with different periods and deadlines, under all three algorithms:

- **Under FIFO:** Tasks run in arrival order. One task misses its deadline.
- **Under RM:** The shortest-period task runs first and preempts the others. Most deadlines are met.
- **Under EDF:** The task with the nearest deadline always runs first. All deadlines are met.

The side-by-side timelines make the difference visible: FIFO misses a deadline, RM does better, EDF meets them all.

## Comparison at a glance

| Algorithm | Priority | Preemptive | Deadline guarantee | Best for |
|---|---|---|---|---|
| FIFO | None — arrival order | No | No | Simple systems where order matters |
| RM | Fixed, by period | Yes | Only up to a utilisation bound | Periodic tasks with fixed priorities |
| EDF | Dynamic, by deadline | Yes | Yes, when a schedule exists | Systems where deadlines are critical |

## When to use which

- **Use FIFO** when the system is simple, tasks are similar, and strict deadlines are not critical.
- **Use RM** when tasks are periodic, priorities should stay fixed, and predictability matters.
- **Use EDF** when deadlines are critical and you need the best chance of meeting them all.

## Video structure

| Time | Clip | Topic |
|---|---|---|
| 0:00–0:10 | 1 | Introduction: FIFO, RM, and EDF |
| 0:10–0:20 | 2 | FIFO: first come, first served |
| 0:20–0:30 | 3 | The weakness of FIFO: a long task blocks an urgent one |
| 0:30–0:40 | 4 | RM: shorter period, higher priority |
| 0:40–0:50 | 5 | EDF: nearest deadline runs first |
| 0:50–1:00 | 6 | Summary table |
| 1:00–1:10 | 7 | Example setup: T1, T2, T3 |
| 1:10–1:20 | 8 | FIFO timeline: a deadline is missed |
| 1:20–1:30 | 9 | RM timeline: most deadlines are met |
| 1:30–1:40 | 10 | EDF timeline: all deadlines are met |
| 1:40–1:50 | 11 | Side-by-side results |
| 1:50–2:00 | 12 | Final recommendation |

## Key takeaway

FIFO is the simplest, RM is the most predictable for periodic work, and EDF is the most effective at meeting deadlines. The right choice depends on what your system must guarantee.

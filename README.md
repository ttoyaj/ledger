# The Ledger

> A single-file, offline-first task, habit, and productivity reporting app that runs entirely in your browser.

**No backend. No account. No installation required.**

Open `Ledger.html` and it works.

The Ledger is designed as a small **typewriter-on-paper ledger card** that can sit above your other browser tabs. Everything runs locally in the browser, with data stored in `localStorage`.

**Your data never leaves your machine unless you explicitly export it.**

---

## ✨ Features

| Area              | Highlights                                                                             |
| ----------------- | -------------------------------------------------------------------------------------- |
| **Tasks**         | Daily task board, categories, due dates, priorities, drag-and-drop, recurrence, URLs   |
| **Habits**        | Recurring habits, weekday schedules, flexible intervals, graded completion, streaks    |
| **Reports**       | Daily goals, productivity analytics, trends, streaks, correlations, historical reports |
| **Sync**          | JSON export/import with automatic schema migration                                     |
| **Floating Mode** | Document Picture-in-Picture floating window with minimize/restore                      |
| **Offline First** | No backend, no account, no network dependency                                          |
| **PWA**           | Installable from supported browsers                                                    |
| **Responsive**    | Works across different browser window sizes                                            |

---

# 1. Tasks

The main board is organized around your daily workload.

### Add Tasks

Use the **`+ add`** button to open a small modal where you can enter:

* Task text
* Optional due date
* Optional recurrence / habit configuration
* Work or Personal category

### Categories

Every task and habit belongs to one of two categories:

* **Work**
* **Personal**

Switch between them using the category toggle.

### Daily Board

Tasks are grouped by date:

1. **Today** always appears first
2. Upcoming dates follow, soonest first
3. Past dates appear last, most recent first
4. Only completed items linger in past dates

### Auto Carry-over

Any task left open at midnight is automatically carried forward to the next day's list.

A small badge indicates how long the task has been carried:

> `carried over 3d`

### Complete / Undo

Click the checkbox — or the task text — to mark a task as complete.

Click again to undo it.

### Inline Editing

Use the **✎ pencil icon** to edit task or habit text directly in place.

### Copy

Use the **📋 copy icon** to copy a task or habit's text to the clipboard.

### Auto-linked URLs

URLs entered into task text are automatically converted into clickable links.

For example:

```text
Review https://example.com before Friday
```

becomes a task containing a clickable URL.

### Due Dates

Tasks can optionally have a due date using the **⏰** icon.

The task displays:

* `due <date>` when upcoming
* `overdue <date>` when past due

Due dates are highlighted:

* **Orange** — due within 24 hours
* **Red** — overdue

### Due-date Reminders

When the app opens, a popup summarizes:

* Items due within 24 hours
* Overdue items

The reminder appears once per app opening and automatically re-checks if the day rolls over while the tab remains open.

### Manual Date Editor

Use the **📅** icon to manually change which day a task is filed under.

Moving a task this way also resets its carry-over counter.

### Move to Today

The **`↑ today`** shortcut moves any non-today item directly onto today's list.

### Drag and Drop

Tasks can be dragged:

* Onto another day to move them
* Onto another task to reorder them

When dropping onto a task, the drop position determines whether the task is placed **before or after** it.

### Delete with Undo

Deleting a task does not use a blocking confirmation dialog.

Instead, a temporary **Undo** toast appears so accidental deletions can be recovered immediately.

---

## Eisenhower Priority Matrix

Every task can be assigned to one of four priority quadrants using the **`+ priority`** chip.

The four quadrants are:

1. **Urgent / Important**
2. **Not Urgent / Important**
3. **Urgent / Not Important**
4. **Not Urgent / Not Important**

The priority chip cycles through the four options and uses different colors to distinguish them.

### Matrix View

A unified matrix view is available regardless of whether you're viewing Work or Personal tasks.

It contains:

* **Unsorted**
* **Urgent / Important**
* **Not Urgent / Important**
* **Urgent / Not Important**
* **Not Urgent / Not Important**

Tasks can be assigned to a quadrant directly from the matrix.

**Today's due habits** are automatically folded into the **Not Urgent / Important** quadrant.

---

# 2. Habits

Habits are recurring items created from the same `+ add` modal.

Enable:

> **🔁 habit**

to turn an item into a recurring habit.

## Recurrence Styles

### Specific Days

Select any combination of weekdays:

```text
Su  Mo  Tu  We  Th  Fr  Sa
```

For example:

```text
Monday + Wednesday + Friday
```

### Every N

Repeat the habit every N:

* Days
* Weeks
* Months

The interval is calculated from the habit's creation date.

Monthly recurrence automatically clamps to the last valid day for shorter months.

For example, a habit created on the 31st will use the last valid day in months that don't have 31 days.

---

## Habit Priority

Habits are automatically fixed at:

> **Important / Not Urgent**

They cannot be manually re-prioritized like normal tasks.

---

## Daily Check-off

A scheduled habit appears inline in the day list.

It can also be checked directly from the matrix view.

The habit only appears on days when it is scheduled.

---

## Habit Year Heatmap

Each habit has a GitHub-contributions-style calendar showing its activity throughout the year.

Each day's square can be clicked to cycle through **five intensity levels**:

```text
0 → blank
1 → light
2 → medium
3 → dark
4 → darkest
```

This allows you to record partial or graded completion instead of only binary done/not-done states.

The heatmap also displays:

> `X / Y days tracked this year`

where:

* `X` = completed days
* `Y` = scheduled days

### Missed Streak

A habit can display:

> `missed Nd`

This represents the current uninterrupted miss streak.

The calculation:

* Counts scheduled days that were not completed
* Works backward from today
* Goes back to the habit's creation date
* Does **not** artificially reset at month boundaries

---

# 3. Report

The **Report** tab provides analytics based on your task and habit history.

## Daily Goals

Set daily targets for:

* Number of tasks to close
* Percentage of habits to complete

The current day's progress is shown with a live progress bar.

---

## Today's Productivity Card

The live Today card includes:

* Tasks created today
* Tasks closed today
* Same-day task closes
* Oldest task closed
* Average age of tasks closed
* Median age of tasks closed
* Eisenhower quadrant breakdown
* Work / Personal breakdown

---

## Oldest Open Task

The report highlights your longest-running open task once it reaches **3+ days old**.

This acts as a gentle nudge toward tasks that may be getting forgotten.

---

## Weekly & Monthly Rollups

The report provides:

* This week
* This month
* Week-over-week comparison

The weekly comparison shows the percentage increase or decrease in tasks closed compared with the previous week.

---

## 14-Day Trend

A 14-day chart shows the number of tasks closed each day.

This makes it easy to see changes in productivity over time.

---

## Current Habit Streak

The report calculates the longest current unbroken run of days where **every scheduled habit was completed**.

---

## Habits ↔ Tasks Correlation

The report compares task productivity between:

* Days where all scheduled habits were completed
* Days where habits were only partially completed

This helps identify whether consistent habit completion correlates with higher task completion.

The correlation is shown only when enough sample data is available.

---

## Best Weekday

Based on up to **90 days of history**, the report identifies the weekday on which you tend to close the most tasks.

For example:

```text
Best weekday: Tuesday
```

---

## Past-Day History

Previous daily reports are stored as a scrollable history.

Reports are cached when a day is finalized, so historical results remain stable even if you continue modifying or adding tasks later.

---

## Copy Weekly Summary

Use the **📋 Copy weekly summary** button to copy a plain-text summary suitable for:

* Journaling
* Standup notes
* Weekly reviews
* Personal productivity tracking

Example:

```text
Tasks closed: 24
Habit completion: 87%
Current streak: 6 days
Best day: Tuesday
```

---

# 4. Sync — Export / Import

The **`⇅ SYNC Options`** menu provides data backup and migration.

## Export

**⬇ Export Tasks**

Downloads all application data as a timestamped `.json` backup file.

The export contains:

* Tasks
* Habits
* Daily reports
* Goals

## Import

**⬆ Import Tasks**

Restores data from a previously exported `.json` backup.

Import requires confirmation because it **fully replaces the current data**.

Older backup formats are automatically migrated to the current schema.

---

## Move Between Devices

Because the Ledger stores everything in browser `localStorage`, Export / Import is also the mechanism for moving your data between:

* Browsers
* Computers
* Devices

```text
Browser A
   │
   │ Export
   ▼
backup.json
   │
   │ Import
   ▼
Browser B
```

---

# 5. Floating / Picture-in-Picture Mode

The Ledger can be detached from the browser tab using the **Document Picture-in-Picture API**.

### ⧉ Pop Out

The **`⧉ pop out`** action undocks the application into a real floating window that can stay above your other browser tabs.

Supported on:

* Chrome desktop
* Edge desktop

Unsupported browsers display:

> `(needs Chrome/Edge)`

---

## Minimize

While popped out, the **`– minimize`** button reduces the Ledger to a small icon-sized badge showing the number of open tasks.

Click the badge to restore the full application.

The app remembers the last manually resized window dimensions.

---

## Pop Back In

Closing the floating window automatically reattaches the Ledger to its original browser tab.

---

# 6. General / Quality of Life

## Installable PWA

The Ledger includes:

* Web app manifest
* Apple/mobile meta tags

This allows it to be added to the home screen or installed like a native application on supported platforms.

---

## Responsive Layout

The ledger card scales with the browser window instead of being locked to a fixed narrow width.

---

## Midnight-Aware

The application automatically detects when the day changes, even if the browser tab has been left open and idle.

When midnight is detected, it:

1. Refreshes **Today**
2. Finalizes the previous day's report
3. Re-checks due-date reminders
4. Updates carry-over tasks
5. Refreshes habit scheduling

No manual page refresh is required.

---

# 🔒 Privacy & Storage

The Ledger is intentionally **local-first**.

```text
┌─────────────────────┐
│       Ledger        │
│                     │
│   Tasks             │
│   Habits            │
│   Reports           │
│   Goals             │
└──────────┬──────────┘
           │
           ▼
    Browser Storage
     localStorage
```

There is:

* ❌ No backend
* ❌ No database server
* ❌ No account
* ❌ No login
* ❌ No required network connection
* ❌ No automatic cloud sync

There is:

* ✅ Local browser storage
* ✅ Offline-first operation
* ✅ JSON export
* ✅ JSON import
* ✅ Full user control over backups

**Your data stays in your browser unless you explicitly export it.**

---

# 🚀 Getting Started

No build process is required.

Simply open:

```text
Ledger.html
```

in a supported browser.

That's it.

---

# 🧰 Technology

The Ledger is designed as a **single-file browser application**.

Core characteristics:

* Client-side only
* `localStorage` persistence
* Offline-first
* No backend
* No account system
* No installation step
* PWA-compatible
* Document Picture-in-Picture support where available

---

# 📁 Data & Backup

A typical workflow is:

```text
              ┌─────────────┐
              │   Ledger    │
              └──────┬──────┘
                     │
              localStorage
                     │
          ┌──────────┴──────────┐
          │                     │
       Browser              Export
          │                     │
          │                  .json
          │                     │
          └────── Import ───────┘
```

For important data, periodically export a backup JSON file.

---

# Browser Support

The core Ledger functionality works in modern browsers that support:

* JavaScript
* `localStorage`
* Clipboard APIs

The floating **Picture-in-Picture** mode specifically requires a browser supporting the **Document Picture-in-Picture API**, such as desktop Chrome or Edge.

---

# 📌 Design Philosophy

The Ledger is intentionally small and self-contained.

It aims to combine:

* **Task management**
* **Habit tracking**
* **Eisenhower prioritization**
* **Productivity analytics**
* **Daily reporting**
* **Offline storage**

without requiring:

* An account
* A server
* A subscription
* A complicated setup
* A cloud service

Just open the file and start using it.

---

## License

Add your preferred license here, for example:

```text
MIT License
```

if the project is intended to be released under MIT.

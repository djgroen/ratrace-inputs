# RatRace Input YAML Files Repository

This repository hosts input YAML files for the R2/RatRace simulation project available for use at [https://ratrace.streamlit.app/](https://ratrace.streamlit.app/), providing structured data for configuring simulation parameters. There are two YAML files per simulation for the `workweek` and `tasks`.

### Structure and Examples

#### Week Structure

The `effort_block` is an integral part of the `week` YAML file. It specifies the type of activity planned for each time block throughout the day. This allows for detailed planning and simulation of various activities, including work tasks, meetings, and breaks.

#### Key to `effort_block` Values:
- `2` indicates a high-focus time block, where intensive tasks are performed.
- `1` represents a low-focus time block, suitable for routine or less demanding tasks.
- `0` signifies a break, a period of no work activity.
- `-1` is used for meetings or lectures, times when participation in discussions or learning activities occurs.

**Example:**

```yaml
week:
  - day: "Monday"
    effort_blocks: [2, 1, 0, -1, 2, 1, 0, 1]
  - day: "Tuesday"
    effort_blocks: [-1, 2, 2, 0, 1, 1, 0]
```

#### Tasks Structure

Describes tasks for the workweek with attributes like name, duration, cost(cost of failure), priority, and potential complications.

**Example:**

```yaml
tasks:
  - name: "Quarterly Strategy Review"
    duration: 2
    priority: 4
    high_focus: true
    cost: 3
    deadline: 2
    complication_probability: 0.2
    complication:
      name: "Significant Changes Needed"
      duration: 2
      priority: 5
      high_focus: true
      cost: 3
      deadline: 2
```

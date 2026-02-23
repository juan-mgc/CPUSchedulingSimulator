# CPU Scheduling Simulator (SRTN + Round Robin)

**Live Demo (Recommended Use):**
https://juan-mgc.github.io/CPUSchedulingSimulator/schedulerProject.html

A lightweight, browser-based CPU scheduling simulator built using **vanilla HTML, CSS, and JavaScript**.

This tool allows users to create jobs with configurable arrival and burst times, select the number of CPUs, define a time quantum, and simulate modern scheduling behavior using:

- **SRTN (Shortest Remaining Time Next)**  
- **Round Robin (RR)**  

The interface dynamically computes job metrics and renders a detailed multi-CPU execution timeline.

---

## Overview

This simulator models preemptive CPU scheduling across multiple processors. It visually demonstrates how jobs are assigned, preempted, completed, and queued over time.

Each simulation computes and displays:

- Start Time
- End Time
- Turnaround Time
- Average Turnaround Time
- CPU utilization timeline
- Queue state snapshots at scheduling points

---

## Features

### Multi-CPU Support
- Simulate scheduling on **1 or more CPUs**
- Independent execution timelines per CPU

### Editable Job Table
- Add and remove jobs
- Edit **Arrival Time** and **Burst Time**
- Supports decimal values (e.g., `0.1`)
- Automatically updates:
  - Start Time
  - End Time
  - Turnaround Time (`endTime - arrivalTime`)

---

## Scheduling Algorithms

### SRTN (Shortest Remaining Time Next)
- Fully preemptive
- Multi-CPU aware
- Ready queue sorted by:
  1. Remaining time
  2. Arrival time (tie-breaker)
- Two operating modes:
  - **Immediately Continue Switch**
  - **Quantum Wait**

### Round Robin
- Multi-CPU implementation
- Configurable **time quantum**
- Fair queue-based rotation
- Uses fixed time precision of `0.1` units

---

## Visualization

The simulator renders a detailed execution timeline including:

- Color-coded job segments
- Idle CPU blocks
- Scheduling tick markers
- Hoverable queue state snapshots
- Arrival markers
- Dynamic scaling based on simulation length

Average turnaround time is displayed as:
(sum of turnaround times) / number of jobs

---

## How to Use

1. Select:
   - Number of CPUs
   - Time Quantum
2. Add jobs and configure:
   - Arrival Time
   - Burst Time
3. Click:
   - **Calculate SRTN**
   - **Calculate Round Robin**
4. Review:
   - Updated job metrics
   - Average turnaround time
   - Execution timeline
   - Queue state evolution

---

## Educational Purpose

This project is intended for:

- Operating Systems coursework
- Demonstrating preemptive scheduling behavior
- Comparing SRTN vs Round Robin
- Visualizing multi-CPU scheduling dynamics

It emphasizes clarity and visualization of scheduling behavior rather than low-level OS kernel implementation.

---

## Getting Started (Local Development)

Clone the repository:

```bash
git clone [https://github.com/juan-mgc/CPUSchedulingSimulator.git]
cd CPUSchedulingSimulator
```
Open:
```bash
schedulerProject.html
```
in your browser

---

## Technical Notes

- Simulation time advances in increments of 0.1 units
- No context-switch overhead is modeled
- Scheduling decisions occur at discrete simulation steps
- Timeline rendering automatically scales to screen width
- Entire project implemented without external libraries

---

## Future Improvements

- Add FCFS / Priority Scheduling
- Include Waiting Time and Response Time metrics
- Export timeline as PNG/SVG
- Import/Export job sets as JSON
- Model context-switch cost

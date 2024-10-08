# CPU-Scheduling-Algorithms
An implementation of various CPU scheduling algorithms in C++. The algorithms included are First Come First Serve (FCFS), Round Robin (RR), Shortest Process Next (SPN), Shortest Remaining Time (SRT) and Highest Response Ratio Next (HRRN).

## Table of Contents
- [CPU-Scheduling-Algorithms](#cpu-scheduling-algorithms)
  - [Algorithms](#algorithms)
    - [First Come First Serve (FCFS)](#first-come-first-serve-fcfs)
    - [Round Robin with varying time quantum (RR)](#round-robin-with-varying-time-quantum-rr)
    - [Shortest Process Next (SPN)](#shortest-process-next-spn)
    - [Shortest Remaining Time (SRT)](#shortest-remaining-time-srt)
    - [Highest Response Ratio Next (HRRN)](#highest-response-ratio-next-hrrn)
  - [Output Control](#output-control)
  - [Input Format](#input-format)

## Algorithms

### First Come First Serve (FCFS)
- First Come First Served (FCFS) is a scheduling algorithm in which the process that arrives first is executed first. It is a simple and easy-to-understand algorithm, but it can lead to poor performance if there are processes with long burst times. This algorithm does not have any mechanism for prioritizing processes, so it is considered a `non-preemptive` algorithm. In FCFS scheduling, the process that arrives first is executed first, regardless of its burst time or priority. This can lead to `poor performance`, as longer running processes will block shorter ones from being executed. It is commonly used in `batch systems` where the order of the processes is important.

### Round Robin with varying time quantum (RR)
- Round Robin (RR) with variable quantum is a scheduling algorithm that uses a `time-sharing` approach to divide CPU time among processes. In this version of RR, the quantum (time slice) is not fixed and can be adjusted depending on the requirements of the processes. The algorithm works by maintaining a queue of processes, where each process is given a quantum of time to execute on the CPU. When a process's quantum expires, it is moved to the back of the queue, and the next process in the queue is given a quantum of time to execute.

### Shortest Process Next (SPN)
- Shortest Process Next (SPN) is a scheduling algorithm that prioritizes the execution of processes based on their `burst time`, or the amount of time they need to complete their task. It is a `non-preemptive` algorithm which means that once a process starts executing, it runs until completion or until it enters a waiting state.

- This algorithm can be beneficial in situations where the objective is to `minimize the average waiting time` for processes, since shorter processes will be executed first, and thus will spend less time waiting in the queue. However, it can lead to longer running processes being blocked by shorter ones, which can negatively impact the overall performance of the system.

### Shortest Remaining Time (SRT)
- SRT is a scheduling algorithm that prioritizes the execution of processes based on their remaining time, it's a `preemptive algorithm`, which means that it can interrupt a process that's already executing if a new process with a shorter remaining time arrives and it's commonly used in situations where the objective is to minimize the average waiting time for processes and burst time is not known in advance.

### Highest Response Ratio Next (HRRN)

- Highest Response Ratio Next (HRRN) is a scheduling algorithm that prioritizes the execution of processes based on their response ratio, it's `non-preemptive` and it's commonly used in situations where the objective is to minimize the average waiting time for processes and burst time is not known in advance.

## Output Control
1- Install `mingw` and `make` then run `"mingw32-make target"` to create an executable named lab4

2- Redirect output to the output text file and read input from the given input file using the following command in powershell:
```bash
Get-Content testcases/sampleIP.txt | ./lab4 | Out-File testcases/sampleOP.txt
```

## Input Format
- Line 1: "trace" or "stats"
- Line 2: a comma-separated list telling which CPU scheduling policies to be analyzed/visualized along with
their parameters, if applicable. Each algorithm is represented by a number as listed in the
introduction section and as shown in the attached testcases.

 1. FCFS (First Come First Serve)
 2. RR (Round Robin)
 3. SPN (Shortest Process Next)
 4. SRT (Shortest Remaining Time)
 5. HRRN (Highest Response Ratio Next)

### Assumption:
  Processes are assumed to be sorted based on the arrival time. If two processes have the same arrival time, then the one with the lower priority is assumed to arrive first.

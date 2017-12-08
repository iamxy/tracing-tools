SystemTap Tools
===========================

## Installing

See [INSTALL.md](INSTALL.md) for installation steps on your platform.

## Tools

### Scheduler

- [cstop_pid.stp](cstop_pid.stp): Trace top 20 context switch pid. [Examples](cstop_pid_example.md)
- [cstop_tid.stp](cstop_tid.stp): Trace top 20 context switch tid. [Examples](cstop_tid_example.md)
- [sched_switch.stp](sched_switch.stp): Displays a list of processes which get switched in and out of the scheduler. [Examples](sched_switch_example.md)

### IO

- [iotrace.stp](iotrace.stp): Trace thread IO. [Examples](iotrace_example.md)
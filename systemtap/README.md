SystemTap Tools
===========================

## Installing

See [INSTALL.md](INSTALL.md) for installation steps on your platform.

## Tools

### Scheduler

- [cstop_pid.stp](cstop_pid.stp): Trace top 20 context switch pid. [Examples](cstop_pid_example.md)
- [cstop_tid.stp](cstop_tid.stp): Trace top 20 context switch tid. [Examples](cstop_tid_example.md)
- [sched_switch.stp](sched_switch.stp): Trace the scheduler switches happening with the process. [Examples](sched_switch_example.md)

### IO

- [iotrace.stp](iotrace.stp): Trace thread IO. [Examples](iotrace_example.md)

### Syscall

- [execsnoop-nd.stp](execsnoop-nd.stp): Trace process `exec()` with command line argument details. [Examples](execsnoop-nd_example.md)
- [killsnoop-nd.stp](killsnoop-nd.stp): Trace `kill()` signals showing process and signal details. [Examples](killsnoop-nd_example.md)

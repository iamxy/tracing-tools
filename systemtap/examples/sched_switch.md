### Usage
```
sudo stap sched_switch.stp pid <pid>
```

> This script works similar to ftrace's sched_switch. It displays a list of
processes which get switched in and out of the scheduler. The format of display
is PROCESS_NAME PROCESS_PID CPU TIMESTAMP PID: PRIORITY: PROCESS STATE ->/+
NEXT_PID : NEXT_PRIORITY: NEXT_STATE NEXT_PROCESS_NAME
-> indicates that prev process is scheduled out and the next process is
scheduled in.
\+ indicates that prev process has woken up the next process.

```
$ sudo stap sched_switch.stp pid 33709
PREV_PROCESS_NAME CPU           TIMESTAMP   PID: PRIO:S  NEXT_PID: PRIO:S NEXT_PROCESS_NAME
swapper/1           1 1512751047112866644     0:   20:R +   33709:   20:R prometheus
swapper/1           1 1512751047112882010     0:  120:R ==> 33709:  120:R prometheus
prometheus          3 1512751047112896327 33709:   20:R +   33709:   20:R prometheus
prometheus         17 1512751047112912190 33709:   20:R +   33709:   20:R prometheus
swapper/3           3 1512751047112912216     0:  120:R ==> 33709:  120:R prometheus
prometheus         15 1512751047112922767 33709:   20:R +   33709:   20:R prometheus
swapper/17         17 1512751047112926245     0:  120:R ==> 33709:  120:R prometheus
prometheus          3 1512751047112936353 33709:  120:S ==>     0:  120:R swapper/3
swapper/15         15 1512751047112938905     0:  120:R ==> 33709:  120:R prometheus
prometheus          1 1512751047112939770 33709:  120:S ==>     0:  120:R swapper/1
prometheus         17 1512751047112950155 33709:  120:S ==>     0:  120:R swapper/17
swapper/3           3 1512751047113000027     0:   20:R +   33709:   20:R prometheus
```

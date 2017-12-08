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
swapper/3           3 1512742700083270125     0:   20:R +   33709:   20:R prometheus
swapper/3           3 1512742700083289588     0:  120:R ==> 33709:  120:R prometheus
prometheus          5 1512742700083303071 33709:   20:R +   33709:   20:R prometheus
prometheus         11 1512742700083317268 33709:   20:R +   33709:   20:R prometheus
prometheus          7 1512742700083327218 33709:   20:R +   33709:   20:R prometheus
prometheus          3 1512742700083358164 33709:  120:S ==>     0:  120:R swapper/3
swapper/5           5 1512742700083361898     0:  120:R ==> 33709:  120:R prometheus
swapper/11         11 1512742700083368071     0:  120:R ==> 33709:  120:R prometheus
swapper/7           7 1512742700083376505     0:  120:R ==> 33709:  120:R prometheus
prometheus          5 1512742700083382945 33709:  120:S ==>     0:  120:R swapper/5
prometheus         11 1512742700083393288 33709:  120:S ==>     0:  120:R swapper/11
prometheus          7 1512742700083406075 33709:  120:S ==>     0:  120:R swapper/7
swapper/11         11 1512742700083443071     0:   20:R +   33709:   20:R prometheus
```

# xv6 OS Extensions

OSN Monsoon 2024 · IIIT Hyderabad

![C](https://img.shields.io/badge/C-00599C?style=flat&logo=c&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![RISC-V](https://img.shields.io/badge/RISC--V-283272?style=flat)

Extensions to the xv6 teaching OS (RISC-V) implementing custom scheduling policies and system calls.

## What I Built

### CPU Schedulers (`xv6/kernel/proc.c`)
Three scheduling algorithms implemented and switchable via Makefile flag:

| Scheduler | Description |
|---|---|
| **FCFS** | First Come First Serve — non-preemptive, ordered by creation time |
| **CFS** | Completely Fair Scheduler — vruntime-based preemptive scheduling |
| **MLFQ** | Multi-Level Feedback Queue — priority aging with starvation prevention |

### Custom System Call
Added a new system call with full kernel-to-user plumbing across `syscall.h`, `syscall.c`, `sysproc.c`, `usys.pl`, and `user.h`.

### Scheduler Test (`xv6/user/schedulertest.c`)
Userspace test program to benchmark and validate scheduler behavior.

## Build and Run

```bash
cd xv6

# Default scheduler
make qemu

# Choose scheduler
make qemu SCHEDULER=FCFS
make qemu SCHEDULER=CFS
make qemu SCHEDULER=MLFQ
```

## Stack
C · xv6 · RISC-V · POSIX · Makefile
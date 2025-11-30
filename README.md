# Linux Commands: top / ps / jobs / kill

## 1. top
실시간 프로세스 모니터링 명령어
CPU 이랑 RAM 사용량 확인 가능
## 사용 예시
top - 05:23:31 up 20 min,  0 users,  load average: 0.00, 0.00, 0.01
Tasks:   2 total,   1 running,   1 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.1 us,  0.1 sy,  0.0 ni, 99.7 id,  0.0 wa,  0.0 hi,  0.1 si,  0.0 st
MiB Mem :   7783.2 total,   6916.8 free,    496.4 used,    370.0 buff/cache
MiB Swap:   2048.0 total,   2048.0 free,      0.0 used.   7131.5 avail Mem

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
    1 root      20   0    4628   3584   3072 S   0.0   0.0   0:00.04 bash
   13 root      20   0    7316   3072   2560 R   0.0   0.0   0:00.01 top
### Dcocker 결과 설명
-    CPU 사용량과 램 사용량읇 보여줍니다.

## 2. ps
프로세스 목록 출력
root@501cfa442804:/# ps
  PID TTY          TIME CMD
    1 pts/0    00:00:00 bash
   14 pts/0    00:00:00 ps

   root@501cfa442804:/# ps aux
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.0  0.0   4628  3584 pts/0    Ss   05:06   0:00 /bin/bash
root        16  0.0  0.0   7064  2816 pts/0    R+   05:29   0:00 ps aux


---

## 3. jobs

root@501cfa442804:/# sleep 100 &
[1] 17
root@501cfa442804:/# jobs
[1]+  Running                 sleep 100 &
root@501cfa442804:/#


---

## 4. kill
root@501cfa442804:/# kill
kill: usage: kill [-s sigspec | -n signum | -sigspec] pid | jobspec ... or kill -l [sigspec]
[1]+  Done                    sleep 100
root@501cfa442804:/# kill 1234
bash: kill: (1234) - No such process

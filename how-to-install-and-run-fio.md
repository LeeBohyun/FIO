# How to Install and Run FIO Benchmark

1. Install FIO
```bash
$ sudo apt-get update && sudo apt-get upgrade
$ apt-get install fio
$ fio --version
```

2. Run FIO

```bash
[global]
ioengine=libaio
filename=/dev/nvme1n1
group_reporting=1
direct=1
verify=0
norandommap=1
size=100%
time_based=1
runtime=300s
ramp_time=10
randrepeat=0
refill_buffers
log_avg_msec=1000
log_max_value=1
unified_rw_reporting=1
percentile_list=50:99:99.9:99.99:99.999

[4k_randwrite_qd16_4w]
stonewall
bs=4k
rw=randwrite
iodepth=4
numjobs=4

[4k_randread_qd16_4w]
stonewall
bs=4k
rw=randread
iodepth=4
numjobs=4
```

# A Kernel Seedling

In this lab we create a /proc/count file that shows the current number of running processes running. We write a kernel module that runs in kernel mode to acces the process table that runs within kernel mode. The file proc_count.c consist of the kernel module.

In the module, we used for_each_process(p) to iterate through each process and increment our count by one. Then we used seq_printf to output our result.

## Building

Build your module with make command
insert module into the kernel

```shell
make
sudo insmod proc_count.ko
```

## Running

use command cat to run module

```shell
cat /proc/count
```

result: 157

## Cleaning Up

```shell
make clean

```

## Testing

```python
python -m unittest
```

result:
Ran 3 tests in 1.347s

OK

Report which kernel release version you tested your module on
(hint: use `uname`, check for options with `man uname`).
It should match release numbers as seen on https://www.kernel.org/.

uname - print system
-s (--kernel-name): print the kernel name
-r (--kernel-release): print the kernel release
-v (--kernel-version): print the kernel version

```shell
uname -r -s -v
```

Linux 5.14.8-arch1-1 #1 SMP PREEMPT Sun, 26 Sep 2021 19:36:15 +0000

kernel version:
#1 SMP PREEMPT Sun, 26 Sep 2021 19:36:15 +0000

# A Kernel Seedling

a kernel module that runs in kernel mode to acces the number of process running.

## Building

Build your module with make command
insert module into the kernel using sudo insmod

```shell
make
sudo insmod proc_count.ko
```

## Running

use command cat to run module
should expect an integer output representing the number of process running

```shell
cat /proc/count
```

result: 157

## Cleaning Up

remove module from kernel using sudo rmmod
clean up all binary files using make clean

```shell

sudo rmmod proc_count
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

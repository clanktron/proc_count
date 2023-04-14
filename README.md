## UID: 005412538

# A Kernel Seedling

An intro project for kernel development. This basic module outputs the number of active processes when invoked.

## Building

To build and load the kernel module run the following:
```bash
# compile the program
make
# load the module
sudo insmod proc_count.ko
```

## Running

To run the kernel module run the following:
```bash
cat /proc/count
```
This should output the number of processes on your system.

This number should be two less than the number output by the command `ps -e | wc -l` (one line is from the title of the output and the other is the ps process itself).

## Cleaning Up

To clean up the project run the following:
```bash
# remove module from kernel
sudo rmmod proc_count
# clean build directory
make clean
```

## Testing

To test the module run the python tests with:
```bash
python -m unittest
```

Builds have been tested on kernel versions 5.14.8 (class provided VM) and 6.2.10 (latest stable release).
To check your current kernel version run `uname -r`.

## Questions:

1. ```
Q: What is an ELF file?
A: Unix executable file format (Executable and Linkeable Format), common exec file for linux.
```

2. Q: How do you query the type of a cpu using cat?
A: cat /proc/cpuinfo

3: Q: What does the 'w' command output?
A: uptime and load average

4: Q: What does load average tell us:
A: measures the number of threads that are working and waiting to work (CPU, disk, uninterruptible locks). 

5: Q: How many hosts does a IP v4 class B network have?
A: 65534.

6: Q: What does NAT stand for and when is  it used?
A: Network Address Translation. A NAT Gateway is a host that bridges connectivity between a private network and the outside networks.

7: Q: How do you permenantly configure FD limits in linux
A: By Editing /etc/security/limits.conf and adding appropriate for 'nofiles' (hard and soft) entries.
NB: 'ulimit' is not the right answer, that only affects the current session.

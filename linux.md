# 리눅스 시스템 응용 설계
## Linux 소개
### Linux Kernel Main Job (4가지)
* Process management
* Momory/Storage management
* Device drivers
* System calls and security

### What does OS (4가지)
* Abstract
* Multiplex
* Isolation
* Share

## Linux commands and tools
```bash
cd
ls
mv
cp
sudo
pwd
mkdir 
touch
shutdown
reboot
passwd
ps (process status)
kill PID
apt
ssh
tar -cvzf (compressing)
tar -xvzf (extracting)
top
uname (a(everything), s(extracting), r(kernel release), v(kernel version))
history
less
man
ctags
cscope
tmux
```

## Linux kernel complile and system calls
### Monolithic Kernel (2가지)
* Monoritic kernel is and OS architecture where the entire operating system is working in kernel space
* Monoritic kernels are able to dynamically load executable modules at runtime
### Micro Kernel (2가지)
* It is the near-minimum amount of software that can provide the mechanisms needed to implement an operating system
* There mechanisms include address space management, thread management, and inter-process communications


![캡처](https://i.imgur.com/1MBG8Rd.png)

## System call
### popular system call
```c
open, read, write, close, wait, exec, fork, exit, kill
```

### System call major categories (6가지)
* **File management** (create, delete, open, close, read, write, repositioin, get/set file attributes)
* **Device management** (requests, release, read, write, reposition, get/set device attributes, logically attach or detach)
* **Information maintenance** (get/set time, date, systemdata, process, file, device attributes)
* **Communication** *(create/delete communication connection, send/receibce message, transfer status information, attach/detach remote devices)
* **protection** (get/set file permisions)

#### System call 예시
![캡처](https://i.imgur.com/KIsJW4n.png)


## Kernel data structure
### Red Block tree Properties (4가지)
* tpye of self-balancing binary search tree
* Nodes: red or black
* Leaves: black, no data
* The path from node to one of its leaves contains the same number of black nodes as the shortest path to any of its other leaves
* Fast search, insert delete operations O(logN)

### Hash table Properties (3가지)
* The size of bucket array chained hash table
* Each bucket has a singly linked list or doubly linked list to resolve hash collision
* Time complexity O(1)


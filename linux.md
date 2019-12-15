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
uname -(a(everything), s(extracting), r(kernel release), v(kernel version))
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


![캡처](https://i.imgur.com/XcaVUoA.png)
## System call
### popular system call
```c
open, read, write, close, wait, exec, fork, exit, kill
```

### System call major categories (6가지)
* **File management** (create, delete, open, close, read, write, repositioin, get/set file attributes)
* **Device management** (requests, release, read, write, reposition, get/set device attributes, logically attach or detach)
* **Information maintenance** (get/set time, date, systemdata, process, file, device attributes)
* **Communication** (create/delete communication connection, send/receibce message, transfer status information, attach/detach remote devices)
* **protection** (get/set file permisions)

#### System call 예시

![캡처](https://i.imgur.com/QaIvl9S.png)

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

## Process and Thread
### Process states (3가지)
* TASK_RUNNING
    (runqueue or waiting queue)
* TASK_INTERRUPTIBLE
* TASK_UNINTERRUPTIBLE
* TASK_STOPPED 
    task is not running nor waiting/ this occurs if the task receives some signal(e.g. SIGSTOP)


![캡처](https://i.imgur.com/nAKexyr.jpg)

### User Level Process and Thread
* Process
```c
    pid_t pid = fork()  // process create
                        // pid == -1 -> error
                        // pid == 0 -> child
                        // pid != 0 -> parent
```

* Thread
```c
 pthread_create(pthread_t *thread, const pthread_attr_t *attr, void *(*start_routine)(void*), void *arg)
 pthread_join(pthread_thread, void **retval)
```

### Kernel Level Process and Thread
 * Linux implements all threads as standard processes

#### Process example (Producer-Consumer)
![캡처](https://i.imgur.com/jSx2Dau.png)

#### Thread example
![캡처](https://i.imgur.com/rDbofgH.png)
![캡처](https://i.imgur.com/x5m7Rw9.png)

### Fork 과정
 1. fork()
 2. sys_fork()
 3. do_fork(clone_flags)
    1. Call copy_process()
        * Check flags (e.g. CLONE_VM, CLONE_FS)
        * Duplicate task_struct
        * check resource limits
        * Initialize task_struct
        * Call sched_fork() -> Scheduler-specific initialization
        * Copy/share process states
            * Call copy_files()
            * Call copy_signal()
            * Call copy_mm() -> **Copy-On-Write(COW)**
            * Call copy_namespace()
            * Call copy_thread()
    2. Allocate a new PID
    3. Call wake_up_new_task()


## Synchronization
### Synchronization 예시 (3가지)
* Fork and joins
* Producer-Consumer
* Exclusive use resources

### atomic operation 종류 와 설명 (3가지)
* Fetch-and-add(&x,a) : x에 a를 더함 그리고 기존 값 리턴
* Test-and-set
* Compare-and-swap

### linux에서 제공하는 lock
* spinlock (busy waiting)
* semaphore
* mutex (blocked)

```c
/* spin lock APIs */
spin_lock()             // acquires given lock
spin_lock_irq()         // Disables local interrupts and acquires given lock
spin_lock_irqsave()     // Saves current state of local interrupts, disables local interrupts, and acquires given lock
spin_unlock()           // Releases given lock
spin_unlock_irq()       // Releases given lock and enables local interrupts
spin_unlock_irqrestore()    // Releases given lock and restores local interrupts to given previous state
spin_lock_init()        // initializes given spinlock_t
spin_trylock()          // Tries to acquire given lock; if unavailable, returns nonzero
spin_is_locked()        // Returns nonzero if the given lock is currently acquired, otherwise it returns zero

/* rw_semaphore APIs */
down_read()     // Get a rw_semaphore for read (can block, if a writer is holding it)
down_write()    // Get a rw_semaphore for write (can block, if one or more readers are holding it)
up_read()       // Release a rw_semaphore held for read
up_write()      // Release a rw_semaphore held for write

/* Mutex APIs */
mutex_init(struct mutex *)      // Initialize the given mutex
mutex_lock(struct mutex *)      // Locks the given mutex; sleeps if the lock is unavailable
mutex_unlock(struct mutex *)    // Unlocks the given mutex
mutex_trylock(struct mutex *)   // Tries to acquirer the given mutex; returns one if successful and the lock is acquired and zero otherwise
mutex_is_locked(struct mutex *) // Returns one if the lock is locked and zero otherwise
```

## Scheduling
### Scheduling 의 목표 (4가지)
* Utilization : Keep the CPU busy with useful work as much as possible
* Throughput : Maximize the number of jobs processed per time unit
* Turnaround time : Minimize the time between submission of a task and its completion
* Fairness : Make sure each task gets a fair share of the CPU

### Scheduling의 발전 (4단계) 
1. Batch Processing OS : Improved Throuput
    * Priority-based scheduling and Round Robin Scheduling
2. Time Shared Interative OS : Balance between Interactivity and Throughput
    * O(N) Queue Scheduling
3. Real-Time OS : Bounded Scheduling Latency
    * O(1) Queue Scheduling, Preemptive Priority Scheduling
4. Multimedia Cloud Computing OS : Proportional Distribution of CPU Time
    * Fair Share Scheduling




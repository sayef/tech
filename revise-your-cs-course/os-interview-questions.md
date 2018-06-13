# Operating System        

**1. What is an operating system?**

An operating system is a program that acts as an intermediary between  the user and the computer hardware. The purpose of an OS is to provide a  convenient environment in which user can execute programs in a  convenient and efficient manner.

**2. What are the different operating systems?**

1.     Batched operating systems
 2.     Multi-programmed operating systems
 3.     Time sharing operating systems
 4.     Distributed operating systems
 5.     Real-time operating systems

**3. What are the basic functions of an operating system?**

Operating system controls and coordinates the use of the hardware  among the various applications programs for various uses. Operating  system acts as resource allocator and manager. Also operating system is  control program which controls the user programs to prevent errors and  improper use of the computer. It is especially concerned with the  operation and control of I/O devices.

**4. What is kernel?**

Kernel is the core and essential part of computer operating system that provides basic services for all parts of OS.

**5. What is difference between micro kernel and macro kernel?**

Micro kernel is a kernel which run services those are minimal for  operating system performance. In this kernel all other operations are  performed by processor.

Macro Kernel is a combination of micro and monolithic kernel. In  monolithic kernel all operating system code is in single executable  image.

**6. What is dead lock?**

Deadlock is a situation or condition where the two processes are  waiting for each other to complete so that they can start. This result  both the processes to hang.

**7. What is a process?**

A program in execution is called a process.

Processes are of two types:

\1. Operating system processes
 \2. User processes

**8. What are the states of a process?**

\1. New
 \2. Running
 \3. Waiting
 \4. Ready
 \5. Terminated

**9. What is starvation and aging?**

Starvation is Resource management problem where a process does not  get the resources it needs for a long time because the resources are  being allocated to other processes.

Aging is a technique to avoid starvation in a scheduling system.

**10. What is semaphore?**

Semaphore is a variable, whose status reports common resource,  Semaphore is of two types one is Binary semaphore and other is Counting  semaphore.

**11. What is context switching?**

Transferring the control from one process to other process requires  saving the state of the old process and loading the saved state for new  process. This task is known as context switching.

**12. What is a thread?**

A thread is a program line under execution. Thread sometimes called a  light-weight process, is a basic unit of CPU utilization; it comprises a  thread id, a program counter, a register set, and a stack

**13. What is process synchronization?**

A situation, where several processes access and manipulate the same  data concurrently and the outcome of the execution depends on the  particular order in which the access takes place, is called race  condition. To guard against the race condition we need to ensure that  only one process at a time can be manipulating the same data. The  technique we use for this is called process synchronization.

**14. What is virtual memory?**

Virtual memory is hardware technique where the system appears to have  more memory that it actually does. This is done by time-sharing, the  physical memory and storage parts of the memory one disk when they are  not actively being used.

**15. What is thrashing?**

It is a phenomenon in virtual memory schemes when the processor  spends most of its time swapping pages, rather than executing  instructions. This is due to an inordinate number of page faults.

**16. What is fragmentation? Tell about different types of fragmentation?**

When many of free blocks are too small to satisfy any request then  fragmentation occurs. External fragmentation and internal fragmentation  are two types of fragmentation. External Fragmentation happens when a  dynamic memory allocation algorithm allocates some memory and a small  piece is left over that cannot be effectively used.  Internal  fragmentation is the space wasted inside of allocated memory blocks  because of restriction on the allowed sizes of allocated blocks.

**17. What are necessary conditions for dead lock?**

\1. Mutual exclusion (where at least one resource is non-shareable)
 \2. Hold and wait (where a process holds one resource and waits for other resource)
 \3. No preemption (where the resources can’t be preempted)
 \4. Circular wait (where p[i] is waiting for p[j] to release a resource. )

**18. What is cache memory?**

Cache memory is random access memory (RAM) that a computer  microprocessor can access more quickly than it can access regular RAM.  As the microprocessor processes data, it looks first in the cache memory  and if it finds the data there (from a previous reading of data), it  does not have to do the more time-consuming reading of data from larger  memory.

**19. What is logical and physical addresses space?**

Logical address space is generated from CPU; it bound to a separate  physical address space is central to proper memory management. Physical  address space is seen by the memory unit. Logical address space is  virtual address space. Both these address space will be same at compile  time but differ at execution time.

**20. Differentiate between Compiler and Interpreter?**

An interpreter reads one instruction at a time and carries out the  actions implied by that instruction. It does not perform any  translation. But a compiler translates the entire instructions

**21. What is Throughput, Turnaround time, waiting time and Response time?**

Throughput – number of processes that complete their execution per time unit

Turnaround time – amount of time to execute a particular process

Waiting time – amount of time a process has been waiting in the ready queue

Response time – amount of time it takes from when a request was  submitted until the first response is produced, not output (for  time-sharing environment)

**22. What is Memory-Management Unit (MMU)?**

Hardware device that maps virtual to physical address. In MMU scheme,  the value in the relocation register is added to every address  generated by a user process at the time it is sent to memory.

The user program deals with logical addresses; it never sees the real physical addresses

**23. What is a Real-Time System?**

A real time process is a process that must respond to the events  within a certain time period. A real time operating system is an  operating system that can run real time processes successfully

**24. What is a trap and trapdoor?**

Trapdoor is a secret undocumented entry point into a program used to  grant access without normal methods of access authentication. A trap is a  software interrupt, usually the result of an error condition.

**25. When is a system in safe state?**

The set of dispatchable processes is in a safe state if there exists  at least one temporal order in which all processes can be run to  completion without resulting in a deadlock.

**26. Explain the concept of the Distributed systems?**

Distributed systems work in a network. They can share the network resources, communicate with each other.

**27. What is cache-coherency?**

In a multiprocessor system there exist several caches each may  containing a copy of same variable A. Then a change in one cache should  immediately be reflected in all other caches this process of maintaining  the same value of a data in all the caches s called cache-coherency.

**28. What is a long term scheduler and short term schedulers?**

Long term schedulers are the job schedulers that select processes  from the job queue and load them into memory for execution. The short  term schedulers are the CPU schedulers that select a process from the  ready queue and allocate the CPU to one of them.

**29. Explain the meaning of mutex.**

Mutex is the short form for ‘Mutual Exclusion object’. A mutex allows  multiple threads for sharing the same resource. The resource can be  file. A mutex with a unique name is created at the time of starting a  program. A mutex must be locked from other threads, when any thread that  needs the resource. When the data is no longer used / needed, the mutex  is set to unlock.

**30. What is cycle stealing?**

We encounter cycle stealing in the context of Direct Memory Access  (DMA). Either the DMA controller can use the data bus when the CPU does  not need it, or it may force the CPU to temporarily suspend operation.  The latter technique is called cycle stealing. Note that cycle stealing  can be done only at specific break points in an instruction cycle.

**31. What is Marshalling?**

The process of packaging and sending interface method parameters across thread or process boundaries.

**32. What is a daemon?**

Daemon is a program that runs in the background without user’s  interaction. A daemon runs in a multitasking operating system like UNIX.  A daemon is initiated and controlled by special programs known as  ‘processes’.

**33. What is pre-emptive and non-preemptive scheduling?**

Preemptive scheduling: The preemptive scheduling is prioritized. The  highest priority process should always be the process that is currently  utilized.

Non-Preemptive scheduling: When a process enters the state of  running, the state of that process is not deleted from the scheduler  until it finishes its service time.

**34. What is busy waiting?**

The repeated execution of a loop of code while waiting for an event  to occur is called busy-waiting. The CPU is not engaged in any real  productive activity during this period, and the process does not  progress toward completion.

**35. What is page cannibalizing?**

Page swapping or page replacements are called page cannibalizing.

**36. What is SMP?**

To achieve maximum efficiency and reliability a mode of operation  known as symmetric multiprocessing is used. In essence, with SMP any  process or threads can be assigned to any processor.

**37. What is process migration?**

It is the transfer of sufficient amount of the state of process from one machine to the target machine.

**38. Difference between Primary storage and secondary storage?**

Primary memory is the main memory (Hard disk, RAM) where the operating system resides.

Secondary memory can be external devices like CD, floppy magnetic  discs etc. secondary storage cannot be directly accessed by the CPU and  is also external memory storage.

**39. Define compactions.**

Compaction is a process in which the free space is collected in a large memory chunk to make some space available for processes.

**40. What are residence monitors?**

Early operating systems were called residence monitors.

**41. What is dual-mode operation?**

In order to protect the operating systems and the system programs  from the malfunctioning programs the two mode operations were evolved
 System mode
 User mode.

**42. What is a device queue?**

A list of processes waiting for a particular I/O device is called device queue.

**43. What are the different types of Real-Time Scheduling?**

Hard real-time systems required to complete a critical task within a guaranteed amount of time.
 Soft real-time computing requires that critical processes receive priority over less fortunate ones.

**44. What is relative path and absolute path?**

Absolute path– Exact path from root directory.
 Relative path– Relative to the current path.

**45. What are the disadvantages of context switching?**

Time taken for switching from one process to other is pure over head.  Because the system does no useful work while switching. So one of the  solutions is to go for threading when ever possible.

**46. What is a data register and address register?**

Data registers – can be assigned to a variety of functions by the  programmer. They can be used with any machine instruction that performs  operations on data.
 Address registers – contain main memory addresses of data and  instructions or they contain a portion of the address that is used in  the calculation of the complete addresses.

**47. What is DRAM?**

Dynamic Ram stores the data in the form of Capacitance, and Static RAM stores the data in Voltages.

**48. What are local and global page replacements?**

Local replacement means that an incoming page is brought in only to  the relevant process’ address space. Global replacement policy allows  any page frame from any process to be replaced. The latter is applicable  to variable partitions model only.

**49. Explain the concept of the batched operating systems?**

In batched operating system the users gives their jobs to the  operator who sorts the programs according to their requirements and  executes them. This is time consuming but makes the CPU busy all the  time.

**50. What is SCSI?**

SCSI – Small computer systems interface is a type of interface used  for computer components such as hard drives, optical drives, scanners  and tape drives. It is a competing technology to standard IDE  (Integrated Drive Electronics).

**51.When is a system in safe state?**

The set of dispatchable processes is in a safe state if there exists  at least one temporal order in which all processes can be run to  completion without resulting in a deadlock.

**52. What is cycle stealing?**

We encounter cycle stealing in the context of Direct Memory Access  (DMA). Either the DMA controller can use the data bus when the CPU does  not need it, or it may force the CPU to temporarily suspend operation.  The latter technique is called cycle stealing. Note that cycle stealing  can be done only at specific break points in an instruction cycle.

**53. What is an idle thread?**

The special thread a dispatcher will execute when no ready thread is found.

**54. What is FtDisk?**

It is a fault tolerance disk driver for Windows NT.

**55.What is  Dispatcher?**

Dispatcher module gives control of the CPU to the process selected by  the short-term scheduler; this involves: Switching context, Switching  to user mode, Jumping to the proper location in the user program to  restart that program, dispatch latency – time it takes for the  dispatcher to stop one process and start another running.

**56. When does the condition ‘rendezvous’ arise?**

In message passing, it is the condition in which, both, the sender and receiver are blocked until the message is delivered.

**57. What is process spawning?**

When the OS at the explicit request of another process creates a process, this action is called process spawning

**58. What are the reasons for process suspension?**

1) swapping
 2) interactive user request
 3) timing
 4) parent process request

**59. What are the sub-components of I/O manager in Windows NT?**

1) Network redirector/ Server
 2) Cache manager.
 3) File systems
 4) Network driver
 5) Device driver

**60. What is a drawback of MVT?**

1) ability to support multiple processors
 2) virtual storage
 3) source level debugging

**61. What is the Translation Lookaside Buffer (TLB)?**

In a cached system, the base addresses of the last few referenced  pages is maintained in registers called the TLB that aids in faster  lookup. TLB contains those page-table entries that have been most  recently used. Normally, each virtual memory reference causes 2 physical  memory accesses- one to fetch appropriate page-table entry, and one to  fetch the desired data. Using TLB in-between, this is reduced to just  one physical memory access in cases of TLB-hit.
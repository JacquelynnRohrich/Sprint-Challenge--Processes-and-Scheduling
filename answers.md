# Multiple Choice and Short Answer Questions

### List all of the main states a process may be in at any point in time on a standard Unix system. Briefly explain what each of these states mean.

* Created - is when a process is first created, it occupies the "created" or "new" state.
* Ready - a ready or waiting process has been loaded into main memory and is awaiting execution on a CPU.
* Running - a process moves into the running state when it is chosen for execution. 
* Blocked - a process transitions to a blocked state when it cannot carry on without an external change in state or even occurring. 
* Terminated - a process may be terminated, either from the "running" state by completing its execution or by explicitly being killed. In either of these cases, the process moves to the "Terminated" state. 


### What is a Zombie Process? How does it get created? How does it get destroyed?

* S Zombie Process is a process that has completed execution (via the EXIT system call) but still has an entry in the process table: it is a process in the "Terminated state". 

* A Zombie Process is created by child processes where the entry is still needed to allow the parent process to read its child's exit status:

* You can destroy a Zombie Process by once the exit status is read via the WAIT system call, the zombie's entry is removed from the process table and it is said to be "reaped". Child process always becomes a zombie before being removed from the resource table.

* The term zombie process derives from the common definition of zombie — an undead person. In the term's metaphor, the child process has "died" but has not yet been "reaped". Also, unlike normal processes, the kill command has no effect on a zombie process.

* Zombie processes should not be confused with orphan processes: an orphan process is a process that is still executing, but whose parent has died. These do not remain as zombie processes; instead, (like all orphaned processes) they are adopted by init (process ID 1), which waits on its children. The result is that a process that is both a zombie and an orphan will be reaped automatically.

### Describe the job of the Scheduler in the OS in general.
* A scheduler is what carries out the scheduling activity. Schedulers are often implemented so they keep all computer resources busy (as in load balancing), allow multiple users to share system resources effectively, or to achieve a target quality of service. The concept of scheduling makes it possible to have computer multitasking with a single central processing unit (CPU).

### Describe the benefits of the MLFQ over a plain Round-Robin scheduler.
* Benefits of MLFQ - They are good for seperating processes into categories based on their need for a CPU. They favor I/O bound processes by letting them run often. Versions of this scheduling policy that increase the quantum at lower priority levels also favor CPU bound processes by giving them a bigger chunk of CPU time when they are allowed to run.

* Benefits of Round Robin Scheduling -  Round robin scheduling is fair in that every process gets an equal share of the CPU. It is easy to implement and, if we know the number of processes on the run queue, we can know the worst-case response time for a process. Cons -  Giving every process an equal share of the CPU is not always a good idea. For instance, highly interactive processes will get scheduled no more frequently than CPU-bound processes.



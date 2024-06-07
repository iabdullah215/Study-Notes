# Operating System Notes

* A program that acts as an intermediary between a user of a computer and the computer hardware.
* Computer System can be divided into four components.
	1. Hardware ***CPU, Memory, I/O Devices***
	2. Operating System ***Intermediate b/w hardware and software***
	3. Application program ***Software used to perform a specific task***
	4. User ***consumer***
- OS is a **resource allocator**
- OS is a **control program**. Controls execution of programs to prevent errors and improper use of the computer.
- “The one program running at all times on the computer” is the ***kernel.***
- ***Bootstrap program*** is also known as the **firmware**
- Each I/O device controller is in charge of a particular device type and its local buffer.
- Device controller informs CPU that it has finished its operation by causing an ***interrupt***.
- A ***trap*** is a software-generated interrupt caused either by an error or a user request.
- An operating system is ***interrupt driven***
- To determine which type of interrupt has been generated we use two methods.
	1. ***Polling***: Polling involves the processor continuously checking each device to see if it has generated an interrupt. In polling, the processor typically loops through each device and checks a specific flag to determine if the device requires attention.
	2. ***Vector***: Vectored interrupt handling uses a table, often called the *interrupt vector table*, which contains addresses of **interrupt service routines** **(ISRs)** corresponding to different interrupt sources.
- Faster storage **(cache)** checked first to determine if information is there If it is, information used directly from the cache **(fast)**. If not, data copied to cache and used there.
- ***System call*** is the request to the operating system to allow user to wait for ***I/O completion.***
- There are two type of Multiprocessing:
	1. **Asymmetric Multiprocessing:** Each processor is assigned a specific task.
	2. **Symmetric Multiprocessing:** All the tasks are divided over all the processors.
- Clustered system are like multiprocessor systems, but multiple systems working together.
	1. **Asymmetric Clustering**: Asymmetric clustering designates specific nodes for specific tasks.
	2. **Symmetric Clustering**: Symmetric clustering involves each node performing the same tasks
- Multiprogramming organizes jobs **(code and data)** so CPU always has one to execute. One job selected and run via ***job scheduling***
- Multitasking involves the simultaneous execution of multiple programs on a single computer, maximizing resource utilization.
- A process is a program in execution. Program is a ***passive entity***, process is an ***active entity.***
- Multi-threaded process has one program counter per thread.

---
#### MIGRATION OF INTEGER A FROM DISK TO REGISTER

**Magnetic Disk --> Main Memory --> Cache --> Hardware Register**

---

- **Protection** – Any mechanism for controlling access of processes or users to resources defined by the OS.
- **Security** – defense of the system against ***internal*** and ***external*** attacks
- Operating systems made available in ***source-code*** format rather than just binary ***closed-source***.
- Operating system provides.
	1. User Interface for **interaction**
	2. Program execution 
	3. I/O Operations
	4. File-System Manipulation
	5. Communication ***(process to process or between networks)***
	6. Error Detection ***(Debugging)***
	7. Resource Allocation 
	8. Accounting ***(To keep track of which users use how much and what kinds of computer resources)***
	9. Protection and Security
* The system call provides an interface through which the programs running on the ***user level*** can demand services from the ***kernel***. System calls operate at a low level of abstraction, directly interacting with the operating system kernel.
* ***APIs (Application Programming Interfaces)*** are define how different software components interact with each other, allowing developers to access functionality and data provided by these components. APIs operate at a higher level of abstraction, providing a more user-friendly interface for developers to interact with software components
* Parameter passing in system calls
	1. Pass the parameters in *registers*
	2. Parameters pushed, onto the *stack* by the program and *popped* off the stack by the operating system.
- ***System programs***, also known as ***system utilities***, provide a convenient environment for program development and execution.
- Constantly running system-program processes are known as ***services***, ***subsystems***, or ***daemons***.
- **Communications** - Provide the mechanism for creating virtual connections among processes, users, and computer systems.
- *User goals* and *System goals*
	1. **User Goals** - operating system should be convenient to use, easy to learn, reliable, safe, and fast.
	2. **System goals** – operating system should be easy to design, implement, and maintain, as well as flexible, reliable, error-free, and efficient.
- Policy -> *what will be done?*
- Mechanism -> *How to do it?*
- Mechanisms determine **how to do something**, policies decide **what will be done**
- **MS-DOS** was written to provide the most functionality in the least space, so it was not carefully divided into modules.
- Such freedom leaves MS-DOS vulnerable to *malicious programs*, causing entire system crashes when user programs fail.
- **UNIX** initially was limited by hardware functionality.
- It consists of two separable parts: *the kernel* and the *system programs*.
- The operating system is divided into a number of **layers (levels)**, each built on top of lower layers. The bottom layer **(layer 0)**, is the *hardware*; the highest **(layer N)** is the *user interface*.
- **Modulization** of *kernel* is call *microkernel*.
- More reliable **(less code is running in kernel mode)**
- A virtual machine takes the **layered approach** to its logical conclusion. It treats **hardware** and the **operating system kernel** as though they were all *hardware*.
- The ***operating system host*** creates the illusion that a process has its own processor and virtual memory.
- **Paravirtualization** is a method of running virtual machines where the guest operating system knows it's running in a virtual environment and works closely with the virtualization software to improve *performance* and *efficiency*. It's like the guest OS and virtualization software speaking the same language to work together more *effectively*.
- OS generate *log files* containing error information.
- *Failure of an application* can generate **core dump** file capturing *memory of the process*.
- *Operating system failure* can generate **crash dump** file containing *kernel memory*.
- **Booting** – starting a computer by loading the kernel.
- **Bootstrap program** – code stored in ROM that is able to locate the kernel, load it into memory, and start its execution.
- Small piece of code – **bootstrap loader**, locates the *kernel*, loads it into *memory*, and starts it.
- Sometimes *two-step* process where **boot block** at fixed location loads *bootstrap* loader.
- Program becomes process when executable file loaded into memory
- One *program* can be several *processes*.
- Process State
	1. New *The process is being created*
	2. Running *Instructions are being executed*
	3. Waiting *The process is waiting for some event to occur*
	4. Ready *The process is waiting to be assigned to a processor*
	5. Terminated *The process has finished execution*
- Program has multiple parts
	1. Text section *code*
	2. Current activity *program counter*
	3. Temporary data *stack*
	4. Global variables *data section*
	5. Dynamically allocated memory *heap*
- Each process is represented in the operating system by a **process control block (PCB)** — also called a **task control block**.
	1. Process state – *running, waiting, etc*
	2. Program counter – *location of instruction to next execute*
	3. CPU registers – *contents of all process-centric registers*
	4. CPU scheduling information - *priorities, scheduling queue pointers*
	5. Memory-management information – *memory allocated to the process*
	6. Accounting information – *CPU used, clock time elapsed since start, time limits*
	7. I/O status information – *I/O devices allocated to process, list of open files*
- The objective of multiprogramming is to have some process running at all times, to maximize CPU utilization.
- As processes enter the system, they are put into a **job queue**, which consists of all processes in the system.
- The processes that are residing in main memory and are ready and waiting to execute are kept on a list called the **ready queue**.
- The list of processes waiting for a particular I/O device is called a **device queue**. *Each device has its own device queue*.
- **Long-term scheduler (or job scheduler)** – selects which processes should be brought into the ready queue. Invoked infrequently *(seconds, minutes)*. It controls the level of *multiprogramming.*
- **Short-term scheduler (or CPU scheduler)** – selects which process should be executed next and allocates CPU. Invoked very frequently *(milliseconds)*
- **Medium-term scheduler** can be added if degree of multiple programming needs to decrease. What is does is that It takes out a process in order to decrease the level of multiprogramming and then reintroduces it and starts working on it from where it was left.
- Processes can be described as either:
	1. **I/O-bound process** – spends more time doing I/O than computations, *many short CPU bursts.*
	2. **CPU-bound process** – spends more time doing computations; *few very long CPU bursts.*
- **Context-switch** time is *overhead*; the system does no useful work while switching.
- Process identified and managed via a **Process Identifier (PID)**.
- ***All children terminated - cascading termination***
- ***Cooperating process*** can affect or be affected by other processes, including sharing data.
- Cooperating processes need **inter-process communication (IPC)**.
- *Producer* *process* produces information that is consumed by a *consumer process*.
- **Unbounded-buffer** places no practical limit on the size of the buffer. The *consumer* may have to wait for new items, but the *producer* can always produce new items.
- **Bounded-buffer** assumes that there is a fixed buffer size. The *consumer* must wait if the buffer is *empty*, and the *producer* must wait if the buffer is *full*.
- **Directed Communication** -- Processes must name each other explicitly. 
- **Undirected Communication** -- Messages are directed and received from mailboxes (also referred to as ports).
- Message passing can either be **blocking** or **non-blocking**.
	1. *Blocking Send* -- The sending process id blocked until the message is being received by another process or a mailbox.
	2. *Blocking receive* -- The receiving processes is blocked until a message isn't available.
	3. *Non-blocking send* -- In the non-blocking send the sending process sends a message then continues wit its process.
	4. *Non-blocking receive* -- In the non-blocking receive the receiving end either receives a message or a *null* message.
- Buffering is of three types.
	1. *Zero Capacity* -- In this case no message can stay in the link. The sender should be blocked after it has sent a message. It is also known as the zero message.
	2. *Bounded Capacity* -- finite length of `n` messages. ; thus, at most `n` messages can reside in it. Sender must wait if link full.
	3. *Unbounded Capacity* -- infinite length. Sender never waits.
- In Mach OS while communication there are two mailboxes formed i.e. *kernel and notify mailbox*. The kernel uses the *Kernel mailbox* to communicate with the task and sends notification of events to *Notify mailbox*.
- Three system call are used
	1. `msg_send()` *send message*
	2. `msg_receive()` *receive message*
	3. `msg_rpc()` *remote procedure call*
- A socket is defined as an *endpoint for communication*.
- A pair of processes communicating over a network employs a pair of sockets — one for each process.
- The socket `161.25.19.8:1625` refers to port `1625` on host `161.25.19.8`
- Ordinary Pipes allow communication in standard producer-consumer style. Producer writes to one end *(the write-end of the pipe)* and consumer reads from the other end *(the read-end of the pipe)*. Requires parent-child relationship between communicating processes.
- Named Pipes are more powerful than ordinary pipes. Communication is bidirectional. No parent-child relationship is necessary between the communicating processes.
- ***RMI -- Remote Method Invocation*** allows a java program on one machine to invoke a method from a remote object.

---

## After Mid Term:

* A thread is a basic unit of CPU utilization; it comprises a **thread ID**, a **program counter**, a **register set**, and a **stack**.
* An application typically is implemented as a separate process with several threads of control.
* A web browser might have one thread display images or text while another thread retrieves data from the network.
* A word processor may have **a thread for displaying graphics**, **another thread for responding to keystrokes from the user**, and **a third thread for performing spelling and grammar checking in the background**.
* In certain situations, a single application may be required to perform several similar tasks. For example, a web server accepts client requests for web pages, images, sound, and so forth.
* When a server receives a message, it services the message using a separate thread. This allows the server to service several concurrent requests.
* Several threads operate in the kernel, and each thread performs a specific task, such as managing devices, managing memory, or interrupt handling.
* Threads share resources of process, easier than **shared memory** or **message passing**.
* Threads share the resources of the process to which they belong. In general it is significantly more time consuming to create and manage processes than threads.
* The benefits of multithreading can be even greater in a multiprocessor architecture, where threads may be running in parallel on different processing cores.
* Processing core is capable of executing only one thread at a time.
* However, concurrency means that the threads can run in parallel, because the system can assign a separate thread to each core.
* The data accessed by the tasks must be examined for dependencies between two or more tasks.
* ***Data parallelism*** focuses on distributing subsets of the same data across multiple computing cores and performing the same operation on each core.
* ***Task parallelism*** involves distributing not data but tasks (threads) across multiple computing cores.
* **User threads** are supported above the *kernel* and are managed without *kernel support*, whereas **kernel** **threads** are supported and managed directly by the *operating system*.
* **Many-to-One Model**
	* Many user-level threads mapped to single kernel thread
	* However, the entire process will block if a thread makes a blocking system call.
	* Also, because only one thread can access the kernel at a time, multiple threads are unable to run in parallel on multicore systems.
* **One-to-One**
	* The one-to-one model maps each user thread to a kernel thread.
	* Allows other thread to run when a thread makes a blocking system call.
	* It also allows multiple threads to run in parallel on multiprocessors.
	* The only drawback to this model is that creating a user thread requires creating the corresponding kernel thread.
* **Many-to-Many Mode**
	* Allows many user level threads to be mapped to many kernel threads.
	* The number of kernel threads may be specific to either a particular application or a particular machine (an application may be allocated more kernel threads on a multiprocessor than on a single processor).
	* Windows with the ***Thread Fiber*** package
	* Developers can create as many user threads as necessary, and the corresponding kernel threads can run in parallel on a multiprocessor.
	* When a thread performs a blocking system call, the kernel can schedule another thread for execution.
*  Thread library provides programmer with API for creating and managing threads.
* ***Pthreads*** refers to the ***POSIX*** standard (IEEE 1003.1c) defining an API for thread creation and synchronization.
* May be provided either as *user-level* or *kernel-level*.
* The `pthread attr t attr` declaration represents the attributes for the thread.
* A separate thread is created with the `pthread create()` function call.
* Threads are created in the Windows API using the `CreateThread()` function.
* Threads are the fundamental model of program execution in a Java program.
* Java threads may be created by:

```java
public interface Runnable 
{ 
	public abstract void run(); 
}
```

* When a class implements Runnable, it must define a `run()` method. The code implementing the `run()` method is what runs as a separate thread.
* Creating a `Thread` object does not specifically create the new thread; rather, the `start()` method creates the new thread.
* The general idea behind a thread pool is to create a number of threads at process startup and place them into a pool, where they sit and wait for work.
* Some UNIX systems have chosen to have two versions of `fork()`, one that duplicates all threads and another that duplicates only the thread that invoked the `fork()` system call.
* `exec()` usually works as normal – replace the running process including all threads.
* A **signal** is used in UNIX systems to notify a process that a particular event has occurred.
* Thread to be canceled is **target thread**.
* **Asynchronous cancellation** terminates the target thread immediately.
* **Deferred cancellation** allows the target thread to periodically check if it should be cancelled.
* If thread has cancellation disabled, cancellation remains pending until thread enables it.
* Default type is **deferred**.
* Cancellation only occurs when thread reaches **cancellation point**. `pthread_testcancel()`
* Thread-local storage (TLS) allows each thread to have its own copy of data.
* Similar to `static` data.
* **TLS is unique to each thread.**
* The **register set**, **stacks**, and **private storage** area are known as the ***context*** of the thread.
* Linux refers to them as ***tasks*** rather than ***threads***.
* Thread creation is done through `clone()` system call.
* `clone()` allows a child task to share the address space of the parent task (process).

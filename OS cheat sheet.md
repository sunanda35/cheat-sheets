# **Operating System**
# CPU Scheduling:
## What is CPU scheduling? 
The basis of multiprogrammed operating systems 
## What is the basic concept of CPU scheduling? 
To be able to have a process running at all time to maximize CPU utilization. The operating system takes the CPU away from a process that is in wait, and gives the CPU to another process. 

## What is a CPU-I/O Burst Cycle? 
The process execution cycle where the process alternates between CPU execution and I/O wait. Begins with CPU burst, then I/O burst, and then CPU burst, and so on. The CPU burst eventually ends with a system request to terminate execution.

## What is a CPU Scheduler? (Also called short-term scheduler) 
Carries out a selection process that picks a process in the ready que to be executed if the CPU becomes idle. It then allocates the CPU to that process. 
## When might a CPU scheduling decision happen? 
### CPU Scheduling (cont) 
1) Switches from running to waiting state 
2) Switches from running to ready state 
3) Switches from waiting to ready state 
4) Process terminates 
The scheduling under 1 and 4 is nonpreemptive (or cooperative), otherwise it is preemptive. Preemptive: Priority to high priority processes, Nonpreemeptive: Running task is executed till completion and can not be interrupted. 
## Potential issues with preemptive scheduling? 
1) Processes that share data: While one is in a state of updating its data, another process is given priority to run but can not read the data from the first process. 
2) Operating system kernal: Another process might be given priority while the kernal is being utilized by another process. The kernal might be going through important data changes, leaving it in a vulnerable state. A possible solution is waiting for the kernal to return to a consistent state before starting another process. 
## What is the dispatcher? 
It is a module that gives control of the CPU to the process selected by the CPU scheduler. This involves (01})a) switching context b) switching to user mode c) jumping to the proper location in the user program to restart that program. 
It is involked in every process switch; the time the dispatcher takes to stop one process and start another is the dispatch latency. 
## CPU Scheduling (cont) 
### Describe the Scheduling Criteria 
Various criterias used when comparing various CPU- scheduling algorithms. -  CPU utilization: Keep the CPU as busy as possible. Ranges from 0 to 10%, usually ranges from 40% (lightly loaded system) to 90% (heavily loaded system). 
-  Throughput: Measures the number of processes that are completed per time unit. 
-  Turnaround time: Amount of time to execute a a particular process. It is the sum of time spent waiting to get into memory, waiting in the ready queue, executing on the CPU, and doing I/O. 
-  Waiting time: The time spent waiting in the ready queue. 
- Response time: The amount of time it takes to produce a response after a submission of a request. Generally limited by the speed of the output device. 
Best to maximize CPU utilization and throughput, and minimize turnaround time, waiting time, and response time, but can still vary depending on the task. 
## Describe the First-Come, First-Served scheduling algorithm 
The process that requests the CPU first is allocated the CPU first. The Gantt chart illustrates a schedule of start and finish times of each process. The average waiting time is heavily dependent on the order of arrival of the processes. If a processes with longer burst time arrive first, the entire process order will now have a longer average wait time. This effect is called the convoy effect 

----Needed to be made, working on it..


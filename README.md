# operating-System
Basic notes on operating system
Memory -- > Ram , Harddisk , Registers , Cache 
CPU will pull the program line by line from the memory and will execute it .
any program which CPU want to run should be in ram . Apart from program , there will be data inside ram which the cpu will use .
The data will copied  from harddisk to RAM and then CPU will access it because the access time of ram is kinda million times that of harddisk .

Need of Operating System:
Long term scheduler is a program in operating system which will decide which programs needs to kept inside ram .
Operating system is called as resource manager (any device we use can be called as a resource s ram is a resource and os is allocating programs to ram )
If there are two process in ram and they are competing to access RAM , In that case function in os will decide whcih process will access first . This functionality of OS is called as short term Scheduler.

Whenever we switch on computer the os program will be copied to RAM . the space where the os code is placed as called as OS code space .othe space is called user place where we keep prorgrams .

Input/Output Device : every IO device has a memory buffer where the binary data will go and fro there it will be transferred to RAM and from there it will move to CPU registers and there the operation will be performed (eg calculation will be done in this way usig ALU) the result will be overridden in any of the register and from there it wil move to CPU and cpu will move it to Ouput Register (eg monitor )


PROGRAM will be either executed by CPU or it is performing some IO event or it is waiting for both the operation to happen .

Turn around time : waiting time(it just waited inside cpu) + burst time(execution time) + I/o time (i/o time)
(time taken by program to stay in CPU)


Program Vs Process
in HDD we have googlechrome.exe it is called as program .the running instance of googlecrome is called as process.
States of program:
New state -> Ready State(waiting for CPU or I/o Operation) -> Running state ( being executing by CPU)->I/O state (if performing I/O event, its also called blocked state)-> Terminated state(after execution , removed from ram ) ->Suspend ready state-> Suspend wait state .

Degree of Multiprogramming (maximum number of programs that can be stayed inside ram )

Types of Operating system : 

Degree of multiprogramming is always 1 . Both I/O and CPU will not be working simultaneously for a single process . they can work at the same time for different process . so if one process is runnig we are wasting the resources .So the efficiency is low .

CPU Efficiencey =userful time of CPU /total time of CPU .
out of total time for how much time cpu is getting consumed .

Multiprogramming operating system : more than one program in the ram .it improve efficiency .(if one of the process is undergoing I/O , i can use the other process to consume CPU .It is called concurrent processing .

MultiProcessing OS : we can have more than one CPU .It will improve the efficiency . It is called parallel processing .
we have multiprocessing computers these days .


Passive Entity: A program creating the processes is called passive entity .
Active Entity : the process which is which being used actually is called active entity 

Process Control block :Apart from the program , process  has stack ( in case the program function call each other ) , It has heap(dynamic memory allocation, allocating memory at runtime ) and also memory for global or static variables (in case the program has static and global variables ).

Properties/Attributes of process :
Process ID:Process ID(unique number of every process) ,
program counter(p1,p2,p3 are three processes in ram,os code will decide which one wil be picked by cpu to execute . that os code is called scheduler . there are multiple algorithms to do that . One is first come first serve  like p1 come to ram first than p2 so it will be executed first . there is another one which is called shortest job for scheduling algorithms (one will shortest execution time will be executed first )if we terminated the process in between , to execute some higher priority . progam counter is the line of the program where we terminated . so that again moving to the program which got terminated , from that line we need this .we store the progra counter inside a registers .
General purpose register : every process will . have register values which need to be remembered (incase we reschedule some terminated process ) so it will be kept in gerneral purpose registers.
Priority 
list of open files : list of open files should be remembered . the reading of the left out files after rescheduling should be done 
list of open devices 
protection : os makes sure that one process should not access space area of another process . that is called protection 

Context of process :
pcb and attributes of a process is called context of process .

Types of scheduler :
Long term scheduler : the part of os code which decides which process from harddisk should be moved to ram .
Short term scheduler : once the prgrams are inside the ram , which process need to execute first is decided by shortterm sch
Medium term scheduler : it decides which process need to be swapped in and swapped out on the basis of priority (in case there is a process inside harddisk having higher priority then it need to put inside ram but ram is full . hence we will do a swap where one process will move from ram to harddisk (swapped out ) and one process will move from hdd to ram (swapped in ).

we save the context of a process in case we halt some process in between . and we start soem other high priority process. it is called context swiching .

VARIOUS TIMES OF PROCESS:
point in time : a particular time 
duration in time : difference between two point in time.
Arrival time : point in time when a program arrives in the ram 
Burst time : Execution time(duration in time for which the process is executed ( it doesn't include waiting time))
Completion time : point in time 
turn around time : Completion time-arrival time (duration of time for which the process is inside the ram )= burst+I/O+waiting time
Waiting time :duration in time for which the process waited while other process were running 
Response time :
I/O time:duration in time spent in I/O 

Scheduling Algorithms :
Preemtive scheduling algorithms and non preemtive scheduling algorithms 

Non-preemptive algorithms (even the process with more priority comes inside RAM , the process in execution will not go into wait state where in preemtive algorithms , the process in execution with less priority will go into wait state .

OS will only consider those process which are in ready state and the process which are in I/O state won't be considered by scheduling algorithms and that's why the process in I/O state is considered as Blocked state .

SJF Algorithms (Shortest Job FIrst Algorithm ): the process with the shortest burst time will be given priority and its non preemptive algorithm.

Schedule length = Completion time of last process-arrival time of first process 

Throughput = no of process/schedule length 

SRTF( shortest remaining time first Algorithm ): it is same as sjf its just that it is preemptive algorithms . it means a process is executing and a new process come in which has burst time less than the remaining time of the running algorithm then that process will get priority .
After all the process are arrived to ram , it will behave as SJF .

Response Time :
Waiting time of the process until it gets the CPU for the first time .

In Any non preemptive algorithm ,Response time= waiting time 
For non-preemtive algorithm , it is not true


FIFO scheduling algorithms : the process which has least arrival time will be scheduled first .



### COSC514BowieState
**The repo contains C++ code that I wrote for a graduate level project in the "Operating Systems" course (COSC 514) at Bowie State University**

In this project, the goal is to simulate several processes going through various queues in a simplified simulated queueing system. 

Ten processes are started and placed in a Ready Queue; one process from the Ready Queue is assigned to a CPU when one becomes available (the assumption is only one CPU is available). A process stays in the CPU for a period that is decided dynamically by random numbers (ranging from 1 to 5) generated before the process is placed in the CPU stage. 

Next, the process is assigned to the Wait Queue where it waits until a Disk becomes available (the assumption is one Disk only is available). In the Disk, an operation of reading in a set of data to fill a memory page is performed (the assumption is a page consists of 8 lines) before the process is moved to the Ready Queue out of the Disk Queue. Each process reads in a specific file corresponding to the process number; each file holds 100 lines with 10 characters per line. The processes traverse the pipeline until all of them read in all 100 lines in their respective files. 

Each process is represented as a Process Control Block (PCB) node; memory information is represented as a memory node. The states in the pipeline are represented as   the following lists consisting of PCB nodes: 
- Ready Queue (N-node list)
- CPU Queue (1-node list)
- Wait Queue (N-node list) 
- Disk Queue (1-node list) 
- Done Queue (N-node list) 

As the processes move through the pipeline, the processes are removed and added to the proper queues. Once all ten processes are done reading in their files, they transition to the Done queue, which completes the execution of the pipeline. The contents of the read-in data are stored in the memory nodes and are organized in a hash table. The hash function is the process number minus 1; each cell in the table holds a pointer to the head pointer of a linked list holding memory nodes for the process. 

The program does not require user input to run. Once it finishes, it will output two pieces of information: 1) a table showing a progression of the processes as they move in the pipeline; 2) the contents of memory nodes showing the read-in data for each of the processes.

![COSC514GITHUB 001](https://user-images.githubusercontent.com/20401990/116634295-a2804280-a929-11eb-96e2-ff07a0adba22.jpeg)

![COSC514GITHUB 002](https://user-images.githubusercontent.com/20401990/116634353-c9d70f80-a929-11eb-88d0-c4a1b689b7d9.jpeg)

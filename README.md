# Modified xv6 OS #

Type 'make qemu' to boot xv6 operating system.

### Modification 1: myapp1 ###
To print out user input to console

### Modification 2: myapp2 ###
To copy contents of one file to another

### Modification 3: Adding a system call ###
Adding the cps() or the current process state system call

### Modification 4: Creating a file ###
This file creates processes that consume CPU time

*	the function takes in two arguments, the number of children to be created and the increment value( default is 1)
*	fork is used to create children. The parent will wait for the child to finish before it goes back to the loop and the child will print out the process id and do some computation. This will consume some computing time so the status of the processes can be seen.
*	later the parent will go back and create another child; the child does not create any other children.

### Modification 5: Adding a priority attribute ###
The processes are assigned with a priority value between 0 and 20, the smaller the value, the higher the priority. 

*	Added priority to a struct proc in proc.h. This data structure is the PCB that consists of all the information about a process.
*	Modified proc.c.Modified cps() so that it prints out the priority of the process also.
*	Modified allocproc,which is a system call, a function that allocates resources to a new process by scanning through the process table

### Modification 6: Changing the priority attribute ###
*	Created a system call chpr(int,int) which takes in two arguments – the process id and it’s new priority.
*	It scans through the process table and changes the priority of that process.

### Modification 7: Implementing Priority Scheduling ###
Modified the schedular in proc.c

# Modified xv6 OS #

To run the program:

Type 'make' to compile the codes.

Type 'make qemu' to boot xv6 operating system.

### Modification 1: Creating myapp1 ###
It echos out whatever we write back on the command line.

DESCRIPTION OF CODE (myapp1.c):

o	the main funtion takes as input the string required to be printed back
o	variable i traverses through the string and prints in on the command line


### Modification 2: Creating myapp2 ###
The copy feature takes in two files, say file1 and file2 and copy the contents of file1 to file2.

DESCRIPTION OF CODE:

o	Fd0 and fd1 are two file descriptors for the two files
o	therefore we need two arguments, If the number of arguments is less than 2, we print out error message to standard output and exit.
o	file1 is opened is opened in read only mode
o	file2 can be created if it does not already exist
o	the while loop simply copies content from file1 to file2


### Modification 3: Adding a system call ###
Adding the cps() or the current process state system call
DESCRIPTION OF CODE:
o	the function does not take any argument. It simply loops through the process table to show the current  process state of the given process

### Modification 4: Creating dummy file ###
This file will create child processes which which would waste CPU time by doing useless computation

DESCRIPTION OF CODE:

o	the function takes in two arguments, the first argument is the number of children to be created and the second argument is the increment value in our for loop; the default is 1
o	we have used fork to create children. The parent will wait for the child to finish before it goes back to the loop and the child will print out the process id and do some computation. In this way they will consume some computing time and we can see the status of these processes
o	later it just breaks and exits so the child does not create any other children but the parent will go back and create another child
o	when k is smaller than n it will create the children one by one


### Modification 5: Adding priority attribute ###
We will assign the process with a priority value between 0 and 20, the smaller the value, the higher the priority. 

o	Added priority to a struct proc in proc.h. This data structure is the PCB that consists of all the information about a process. We add the priority attribute to it.
o	Modified proc.c.Modified cps() so that it prints out the priority of the process also.
o	Modified allocproc,which is a system call, a function that allocates resources to a  new process by scanning through the process table the ptable

### Modification 6: Changing priority attribute ###
o	Created a system call chpr(int,int) which takes in two arguments – the process id and it’s new priority.
o	It scans through the process table and changes the priority of that process.

### Modification 7: Implementing Simple Priority Scheduling ###
Modified the schedular in proc.c


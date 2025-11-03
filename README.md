# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec()

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:

## C Program to create new process using Linux API system calls fork() and getpid() , getppid() and to print process ID and parent Process ID using Linux API system calls


#include <stdio.h>

#include <sys/types.h>

#include <unistd.h>

int main(void)

{ //variable to store calling function's process id

pid_t process_id;

//variable to store parent function's process id

pid_t p_process_id;

//getpid() - will return process id of calling function

process_id = getpid();

//getppid() - will return process id of parent function

p_process_id = getppid();

//printing the process ids//printing the process ids

printf("The process id: %d\n",process_id);

printf("The process id of parent function: %d\n",p_process_id);

return 0; }













##OUTPUT

<img width="836" height="80" alt="image" src="https://github.com/user-attachments/assets/385e80f9-34d2-4034-9d57-5ee1b77ff7d4" />









## C Program to execute Linux system commands using Linux API system calls exec() , exit() , wait() family


#include <unistd.h>

#include <stdio.h>

#include <stdlib.h>

#include <sys/wait.h>

#include <sys/types.h>

int main()

{ int status;

    printf("Running ps with execlp\n");
    
    execl("ps", "ps", "ax", NULL);
    
    wait(&status);
    
    if (WIFEXITED(status))
    
            printf("child exited with status of %d\n", WEXITSTATUS(status));
            
    else
    
            puts("child did not exit successfully\n");
            
    printf("Done.\n");

    printf("Running ps with execlp. Now with path specified\n");
    
    execl("/bin/ps", "ps", "ax", NULL);
    
    wait(&status);
    
    if (WIFEXITED(status))
    
            printf("child exited with status of %d\n", WEXITSTATUS(status));
            
    else
    
            puts("child did not exit successfully\n");
            
    printf("Done.\n");
    
    exit(0);}





























##OUTPUT

<img width="793" height="71" alt="image" src="https://github.com/user-attachments/assets/591e0ee4-64fe-4c01-beef-964633bf4275" />



















# RESULT:
The programs are executed successfully.

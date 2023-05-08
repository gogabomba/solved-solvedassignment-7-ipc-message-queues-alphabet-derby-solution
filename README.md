Download Link: https://assignmentchef.com/product/solved-solvedassignment-7-ipc-message-queues-alphabet-derby-solution
<br>
Assignment DescriptionTo emphasize the IPC an additional channel called message queues is exercised in this assignment.

The assignment is called AlphaDerby, and in the “demo” folder several different versions are to be copied and run by yourself.

The parent process creates 26 child processes among which each moves an alphabet letter ‘A’ to ‘Z’ on a separate row across the screen. Each move is coupled with a random delay (0.05, 0.1, 0.15, or 0.2 second). So, which letter wins is random. The results will be printed out by the parent process once all children have reached the end goal position.

Your turn-in code should be able to compile and run with the matching result of what AlphaDerby does in the minimum version.

The extra-credit version earns 2 more points. You need to write keypoll.c to compile into executabl keypoll as a child process of parent.c. It will first run and let the user pick an alphabet to see if it will win. The picked alphabet is then returned to the parent process via an exit number. The parent process then shows “GOOD LUCK” at that character row, and subsequently shows if the player wins.

The top 5 winning alphabets will also be marked on the screen by the parent process on the rightmost column at the end (see how the demo runs).

Remember to delete your old semaphores and message queues in the system: ipcs; ls -l /dev/shm to show them. Issue ipcrm and rm /dev/shm/* to remove those that belong to you. There is a Perl script cleanup.pl that automatically clean them. You can copy it over and run it.

Program ExamplesLook into the MsgExample1/2/3 folders for example programs on how to request for a message queue and use it among processes. See the code-skeleton folder for the code structure of the assignment.

The parent is the process that prepares a semaphore for the video access sharing, and a message queue for message passing among all processes. The access of the message queue requires a process to know the message queue number (ID) first, and each message sent will need a designated recipient number in it (we can use the unique PID for this purpose). Other data items in the message is to be freely defined as a data structure as needed.

We will also learn how to combine multiple source-code files in compilation via a Makefile and the shell command make will read this file and link all parts into compilation of executables specified by the rules scripted in the Makefile. This is the beginning of a project builder (later called IDE with GUI representation).

The common.h has commonly-used includes, constants, types, and prototypes. The common.c has commonly-used functions (prototyped in common.h) by both parent.c and child.c (and keypoll.c if used).

Main Syscallsmsgget() to request for a message queuemsgsnd() to send a message to the queuemsgrcv() to receive a message from the queuemsgctl() to remove a message queuesem_open() to request for a semaphore (process)sem_wait() to wait on a semaphore (process)sem_post() to post to a semaphore (process)sem_unlink() to remove a semaphore (process)Other Sys/Lib CallsOthers used ones are: wait(), write(), execl(), printf(), sprintf(), perror(), exit(), srand(), rand(), getpid(), getppid(), some more used in the “keypoll.c” that you need to code from examples given in the KeyPoll folder as part of what is required for extra-credit points.Assignment Turn-inSubmit your source-code files the same way as required before. No E-mail will be accepted, and no late turn-ins.

Clean up your code with a clean format, preamble header, and comments where suited (and can help the grader to understand your code). Do not mess with your code since it may cause point deduction. You’re forewarned.

==========================
Process Identification
==========================

The `pid_t` data type represents process IDs. You can get the process ID of a process by calling `getpid`.

The function `getppid` returns the process ID of the parent of the current process (this is also known as the **parent process ID**). Your program should include the header files `unistd.h` and `sys/types.h` to use these functions.

Data Type: **pid_t**

    The `pid_t` data type is a signed integer type which is capable of representing a process ID. In the GNU C Library, this is an `int`. 

Function: **pid_t getpid (void)**

    Preliminary: | MT-Safe | AS-Safe | AC-Safe | See `POSIX Safety Concepts <PSC>`_.

    The `getpid` function returns the process ID of the current process. 

Function: **pid_t getppid (void)**

    Preliminary: | MT-Safe | AS-Safe | AC-Safe | See `POSIX Safety Concepts <PSC>`_.

    The `getppid` function returns the process ID of the parent of the current process. 



==========================
BSD Process Wait Functions
==========================

The GNU C Library also provides these related facilities for compatibility with BSD Unix. BSD uses the `union wait` data type to represent status values rather than an `int`.

The two representations are actually interchangeable; they describe the same bit patterns. The GNU C Library defines macros such as `WEXITSTATUS` so that they will work on either kind of object, and the `wait` function is defined to accept either type of pointer as its **status-ptr** argument.

These functions are declared in `sys/wait.h`.

Data Type: **union wait**

    This data type represents program termination status values. It has the following members:

    `int w_termsig`

        The value of this member is the same as that of the `WTERMSIG` macro.
        
    `int w_coredump`

        The value of this member is the same as that of the `WCOREDUMP` macro.
        
    `int w_retcode`

        The value of this member is the same as that of the `WEXITSTATUS` macro.
        
    `int w_stopsig`

        The value of this member is the same as that of the `WSTOPSIG` macro. 

    Instead of accessing these members directly, you should use the equivalent macros. 

The `wait3` function is the predecessor to `wait4`, which is more flexible. `wait3` is now obsolete.

Function: **pid_t wait3 (union wait *status-ptr, int options, struct rusage *usage)**

    Preliminary: | MT-Safe | AS-Safe | AC-Safe | See `POSIX Safety Concepts <PSC>`_.

    If **usage** is a null pointer, `wait3` is equivalent to `waitpid (-1, status-ptr, options)`.

    If **usage** is not null, `wait3` stores usage figures for the child process in `*rusage` (but only if the child has terminated, not if it has stopped). See `Resource Usage <RU>`_.


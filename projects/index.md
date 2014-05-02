---
layout: default
title: Projects
---


## Projects

There are many interesting improvements that can be done to S2E. We list
some of ideas below. Feel free to propose your own on the developer's
mailing list or volunteer to contribute to an existing project! You will
gain a lot of experience with low-level programming, advanced
virtualization technologies, and will also help the community.

-   **Symbolic execution support for standalone programs.**
    S2E is a VM-based platform, i.e, it requires setting up a VM with an
    entire software stack to test programs. While useful for testing
    applications directly in their native environment, it comes at a
    non-negligible cost, which could be avoided when testing programs in
    isolation. Besides running entire VMs, QEMU can also emulate
    isolated user-mode applications. For example, it is possible to take
    a Linux binary compiled for, say, the ARM architecture and run it on
    an x86 Linux host environment. Behind the scene, QEMU automatically
    translates ARM to x86 and forwards all syscalls performed by the ARM
    binary to the x86 Linux host. The goal of this project is to add
    symbolic execution support to user-mode emulation, to enable
    symbolic execution of unmodified binaries without the overhead of
    the entire software stack. The main challenge of this project is how
    to invoke the system calls in a consistent manner without clobbering
    all execution states. Recall that in the VM-based symbolic
    execution, one can fork the entire system state, which automatically
    guarantees that changes done to one state do not affect the others.
    Since the host environment is outside the control of user-mode S2E,
    forking is not an option.

-   **Graphical User Interface for S2E.** S2E is currently configured
    prior to execution and has little interaction with its users during
    execution. S2E users have a hard time monitoring and controlling the
    evolution of their tests. The purpose of this project is to
    integrate S2E with existing development platforms, such as gdb and
    Eclipse. This project will bring an entirely new dimension to
    software debugging in Eclipse. Imagine performing queries on the
    debugged program, such as: “find all test scenarios for my program
    such that x < 15”, or “insert a breakpoint at each possible
    segmentation fault in my program”.

-   **Linux Instrumentation Toolkit for S2E.** The S2E platform was
    successfully applied by multiple research groups for a variety of
    tasks ranging from automatic device driver reverse engineering
    (RevEng) and testing (DDT), to multi-path performance profiling.
    These tools work by looking at the guest OS’s kernel and driver
    state in order to analyze their behavior, detect bugs, etc.
    Unfortunately, using S2E to perform any analysis that requires deep
    introspection or modification of system state is hard as the
    introspection API provided by S2E is very basic and low-level. The
    aim of this project is to provide a high-level introspection API for
    Linux targets in S2E (potentially based on the
    [insight-vmi](http://code.google.com/p/insight-vmi/) tool). Such API
    would significantly simplify the use of S2E for Linux software
    analysis and enable new applications, such as testing of
    multi-threaded software, performing security analysis, etc.

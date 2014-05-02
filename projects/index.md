---
layout: default
title: Projects
---

## Projects

### S²E Showcase

S2E is currently being used for several scientific projects across the
world. Among them:

-   **Corruption Impact Analysis** at University of Wisconsin
    ([Subramanian
    Sriram](http://pages.cs.wisc.edu/~srirams/new_hp_2011/homepage.html),
    [Sundararaman Swaminathan](http://pages.cs.wisc.edu/~swami/),
    [Andrea C. Arpaci-Dusseau](http://pages.cs.wisc.edu/~dusseau/),
    [Remzi Arpaci-Dusseau](http://pages.cs.wisc.edu/~remzi/)).
    Corruption Impact Analysis is a novel technique to understand the
    impact of memory corruptions in file systems. We employ selective
    symbolic execution to exhaustively explore the impact of memory
    corruptions on other in-memory data structures, disk and the user.
    Our technique emphasizes the importance of the location of
    corruption in addition to the corrupted data structure. We present a
    detailed case study of applying our technique to Ext2. We identify
    the data structures and code regions most sensitive to corruption
    and present corruption spectrums for each scenario. Thus, our
    technique offers developers the opportunity to improve file system
    reliability without sacrificing performance.

-   **[KleeNet
    project](http://www.comsys.rwth-aachen.de/research/projects/kleenet/)**
    at Chair of Communication and Distributed Systems (ComSys), RWTH
    Aachen University ([Raimondas
    Sasnauskas](http://ds.informatik.rwth-aachen.de/members/sasnauskas),
    [Klaus Wehrle](http://www.comsys.rwth-aachen.de/team/klaus/)).
    Within KleeNet project, we are symbolically executing unmodified
    sensornet applications to generate distributed execution paths at
    high-coverage. However, the symbolic execution of Internet
    communication protocols is difficult since the software is not
    self-contained and hence heavily interacts with its surrounding
    environment (OS, libraries). Using S2E, we are able to switch
    between symbolic and native execution in a flexible way with low
    manual effort. Therefore, it allows us to drive the analysis towards
    interesting software parts.

-   **[Improving Automation in Developer Testing: Cooperative Developer
    Testing](http://people.engr.ncsu.edu/txie/)** at North Carolina
    State University ([Xie Tao](http://people.engr.ncsu.edu/txie/)).
    Developer testing, a common step in software development, involves
    generating sufficient test inputs and checking the behavior of the
    program under test during the execution of the test inputs. This
    project develops novel techniques and tools for improving automation
    in developer testing focusing on improving automation in test
    generation and test oracles. This project also investigates the
    methodology of cooperative developer testing: developers and tools
    cooperate in effectively accomplishing challenging tasks in software
    testing.

-   **File Systems Equivalence Checking** at Max Planck Institute for
    Software Systems ([Carreira
    João](http://www.mpi-sws.org/index_noflash.php?n=people/Joao_Carreira),
    [Rodrigo Rodrigues](http://www.mpi-sws.org/~rodrigo/), [Rupak
    Majumdar](http://www.cs.ucla.edu/~rupak/)). The goal of this project
    is to find functional bugs in systems code by checking the
    equivalence of multiple implementations that obey the same
    specification. Checking the equivalence of the different systems is
    performed by comparing the outputs and the logical state of
    different systems after executing the operations in their
    specification. Symbolic execution will allows us to reason about all
    possible executions and results of these operations. We specifically
    intend to apply this approach to find functional bugs in file
    systems.

-   **Exploiting Parallelism for Effective Low-Level Software Analysis**
    at Institute of Software Chinese Academy of Sciences ([Jian
    Liu](http://124.16.139.203/self_pages/liujian/index.htm), Bin Li,
    Sunlv Wang). In this project, one goal is to analyze typical
    application software and system code such as embedded OS or
    hypervisor. For example, we use S2E to analyze hypercalls in the Xen
    hypervisor. This project also plans to improve performance of S2E.
    We introduce concurrency algorithms and build a framework of
    scheduling rules to maximize the multi-path processing efficiently
    using multi-threading and multi-core processors. We are also
    devising heuristics to reduce the search time and to enhance
    efficiency.

-   **[Testing Linux Device
    Drivers](http://research.cs.wisc.edu/sonar/projects/symdrive/)** at
    University of Wisconsin-Madison (Matthew J. Renzelmann, Asim Kadav,
    and Michael M. Swift). SymDrive is a system for testing Linux and
    FreeBSD drivers without their devices. The system uses symbolic
    execution to remove the need for hardware, and provides three new
    features beyond prior symbolic-testing tools. First, SymDrive
    greatly reduces the effort of testing a new driver with a
    static-analysis and source-to-source transformation tool. Second,
    SymDrive allows checkers to be written as ordinary C and execute in
    the kernel, where they have full access to kernel and driver state.
    Finally, SymDrive provides an execution-tracing tool to identify how
    a patch changes I/O to the device and to compare device driver
    implementations. In applying SymDrive to 21 Linux drivers and 5
    FreeBSD drivers, we found 39 bugs.

### Project Ideas

There are many interesting improvements that can be done to S2E. We list
some of ideas below. Feel free to propose your own on the developer's
mailing list or volunteer to contribute to an existing project! You will
gain a lot of experience with low-level programming, advanced
virtualization technologies, and will also help the community.

-   **Symbolic execution support for standalone programs.** \
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

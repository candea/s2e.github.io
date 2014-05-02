---
layout: default
title: Showcase
---


## Showcase

S²E is currently being used for several scientific projects across the
world. Among them:

-   **<a href="http://research.cs.wisc.edu/sonar/projects/symdrive/" target="_blank">Testing Linux Device
    Drivers</a>** at
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

-   **File Systems Equivalence Checking** at Max Planck Institute for
    Software Systems (<a href="http://www.mpi-sws.org/index_noflash.php?n=people/Joao_Carreira" target="_blank">Carreira
    João</a>,
    <a href="http://www.mpi-sws.org/~rodrigo/" target="_blank">Rodrigo Rodrigues</a>, <a href="http://www.cs.ucla.edu/~rupak/" target="_blank">Rupak
    Majumdar</a>). The goal of this project
    is to find functional bugs in systems code by checking the
    equivalence of multiple implementations that obey the same
    specification. Checking the equivalence of the different systems is
    performed by comparing the outputs and the logical state of
    different systems after executing the operations in their
    specification. Symbolic execution will allows us to reason about all
    possible executions and results of these operations. We specifically
    intend to apply this approach to find functional bugs in file
    systems.


-   **Corruption Impact Analysis** at University of Wisconsin
    (<a href="http://pages.cs.wisc.edu/~srirams/new_hp_2011/homepage.html" target="_blank">Subramanian
    Sriram</a>,
    <a href="http://pages.cs.wisc.edu/~swami/" target="_blank">Sundararaman Swaminathan</a>,
    <a href="http://pages.cs.wisc.edu/~dusseau/" target="_blank">Andrea C. Arpaci-Dusseau</a>,
    <a href="http://pages.cs.wisc.edu/~remzi/" target="_blank">Remzi Arpaci-Dusseau</a>).
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

-   **<a href="http://www.comsys.rwth-aachen.de/research/projects/kleenet/" target="_blank">KleeNet
    project</a>**
    at Chair of Communication and Distributed Systems (ComSys), RWTH
    Aachen University (<a href="http://ds.informatik.rwth-aachen.de/members/sasnauskas" target="_blank">Raimondas
    Sasnauskas</a>,
    <a href="http://www.comsys.rwth-aachen.de/team/klaus/" target="_blank">Klaus Wehrle</a>).
    Within KleeNet project, we are symbolically executing unmodified
    sensornet applications to generate distributed execution paths at
    high-coverage. However, the symbolic execution of Internet
    communication protocols is difficult since the software is not
    self-contained and hence heavily interacts with its surrounding
    environment (OS, libraries). Using S2E, we are able to switch
    between symbolic and native execution in a flexible way with low
    manual effort. Therefore, it allows us to drive the analysis towards
    interesting software parts.

-   **<a href="http://people.engr.ncsu.edu/txie/" target="_blank">Improving Automation in Developer Testing: Cooperative Developer
    Testing</a>** at North Carolina
    State University (<a href="http://people.engr.ncsu.edu/txie/" target="_blank">Xie Tao</a>).
    Developer testing, a common step in software development, involves
    generating sufficient test inputs and checking the behavior of the
    program under test during the execution of the test inputs. This
    project develops novel techniques and tools for improving automation
    in developer testing focusing on improving automation in test
    generation and test oracles. This project also investigates the
    methodology of cooperative developer testing: developers and tools
    cooperate in effectively accomplishing challenging tasks in software
    testing.

-   **Exploiting Parallelism for Effective Low-Level Software Analysis**
    at Institute of Software Chinese Academy of Sciences (<a href="http://124.16.139.203/self_pages/liujian/index.htm" target="_blank">Jian
    Liu</a>, Bin Li,
    Sunlv Wang). In this project, one goal is to analyze typical
    application software and system code such as embedded OS or
    hypervisor. For example, we use S2E to analyze hypercalls in the Xen
    hypervisor. This project also plans to improve performance of S2E.
    We introduce concurrency algorithms and build a framework of
    scheduling rules to maximize the multi-path processing efficiently
    using multi-threading and multi-core processors. We are also
    devising heuristics to reduce the search time and to enhance
    efficiency.

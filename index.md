---
layout: default
title: Overview
---



S2E is a platform for writing tools that analyze the properties and
behavior of software systems. S2E is a virtual machine augmented
with symbolic execution and modular path analyzers. S2E runs
unmodified x86, x86-64, or ARM software stacks, including programs,
libraries, the kernel, and drivers. Symbolic execution then
automatically explores hundreds of thousands of paths through the
system, while analyzers check that the desired properties hold on
these paths and selectors focus path exploration on components of interest.

We have used S2E to develop a
comprehensive performance profiler, a reverse engineering tool for
proprietary software, and a bug finding tool for both kernel-mode
and user-mode binaries. Others have used S2E to build scalable
file system checkers, symbolic execution engines for interpreted languages,
tools for finding trojan messages in distributed systems, verifying
software routers, testing embedded systems, and more.

<table>
<tr>
<td><img src="/images/s2e-vm.png" height="300px"/></td>
<td><img src="/images/s2e-sel.png" height="300px"/></td>
</tr>
</table>




<hr/>


<table style="border-collapse:separate; border-spacing: 0.7em 0.7em;border:0px;;">

    <tr>
      <td rowspan="2"><img src="/images/vm.png" height="64"/></td>
      <td width="50%">
        <span style="font-size:large;font-weight:bold;">
          <a href="https://s3.amazonaws.com/s2e-demo-vm/s2e-demo-vmware.tar.bz2" class="external">
          S2E in a Box
          </a>
        </span>
      </td>
      <td rowspan="2"><img src="/images/dl.png" height="64"/></td>
      <td width="50%">
        <span style="font-size:large;font-weight:bold;">
          <a href="https://github.com/dslab-epfl/s2e/archive/stable-1.3.zip" class="external">
            Source Code
          </a>
        </span>
      </td>
      <!--
      <td rowspan="2"><img src="/images/ddt.png" height="64"/></td>
      <td width="30%">
        <span style="font-size:large;font-weight:bold;">
          <a href="http://codetickler.org" class="external" target="_blank">
            S2E in the Cloud
          </a>
        </span>
      </td>
      -->
    </tr>

    <tr>
      <td style="vertical-align: top;">
        Hands-on experience of multi-path software analysis in a preconfigured environment.<br />
        <span style="font-size:x-small;">
          Requires <a href="http://www.vmware.com/products/player/" class="external">VMware Player</a>
        </span>
      </td>
      <td style="vertical-align: top;">
        Including build instructions, documentation, tutorials, and more.
      </td>
      <!--
      <td style="vertical-align: top;">
        Test Windows device drivers with CodeTickler.
      </td>
      -->
    </tr>
</table>


<hr/>

S2E’s novelty consists of its ability to scale to large real
systems, such as a full Windows stack. S2E is based on two new ideas:

  *  Selective symbolic execution, a way to automatically minimize the amount of code that has to be executed symbolically given a target analysis; and
  *  Relaxed execution consistency models, a way to make principled performance/accuracy trade-offs in complex analyses.

These techniques give S2E three key abilities:

  *  to simultaneously analyze entire families of execution paths, instead of just one execution at a time;
  *  to perform the analyses in-vivo within a real software stack—user programs, libraries, kernel, drivers, etc.—instead of using abstract models of these layers; and
  *  to operate directly on binaries, thus being able to analyze even proprietary software.


Conceptually, S2E is an automated path explorer with modular path
analyzers: the explorer drives the target system down all execution
paths of interest, while analyzers check properties of each such
path (e.g., to look for bugs) or simply collect information (e.g.,
count page faults). Desired paths can be specified in multiple ways,
and S2E users can either combine existing analyzers to build a
custom analysis tool, or write new analyzers using the S2E API.

S2E helps make analyses based on symbolic execution practical for
large software that runs in real environments, without requiring
explicit modeling of these environments.

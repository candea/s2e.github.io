---
layout: default
title: Overview
---

S2E is a platform for writing tools that analyze the properties and
behavior of software systems. So far, we have used S2E to develop a
comprehensive performance profiler, a reverse engineering tool for
proprietary software, and a bug finding tool for both kernel-mode
and user-mode binaries. Building these tools on top of S2E took less
than 770 LOC and 40 person-hours each.

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

<table style="border-collapse:separate; border-spacing: 0.7em 0.7em;border:0px;;">
    <tr>
      <td style="border:0px;;"><img src="/images/dl.png" style="height:48px;" alt="" /> </td>
      <td style="border:0px;">
        <span style="font-size:large;font-weight:bold;">
          <a href="https://s2e.epfl.ch/attachments/download/63/s2e-demo-vmware.tar.bz2" class="external">
          S2E in a Box
          </a>
        </span><br />
        Hands-on experience of multi-path software analysis in a preconfigured environment.<br />
        <span style="font-size:x-small;">
          Requires <a href="http://www.vmware.com/products/player/" class="external">VMware Player</a>
        </span>
      </td>
    </tr>
    <tr>
      <td style="vertical-align:middle;border:0px;padding-bottom: 1em;;">
        <img src="/images/vm.png" style="height:48px;" alt="" />
      </td>
      <td style="border:0px;;">
        <span style="font-size:large;font-weight:bold;">
          <a href="https://github.com/dslab-epfl/s2e/archive/stable-1.3.zip" class="external">
            Source Code
          </a>
        </span><br />
        Including build instructions, documentation, tutorials, and more.
      </td>
    </tr>
</table>

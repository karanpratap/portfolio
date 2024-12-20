---
layout: ../../layouts/post.astro
title: "My Projects"
pubDate: 2024-08-20
description: "My Projects"
author: "karanprs"
excerpt: Projects I have undertaken during my time as a CMU graduate student. Some of these, especially the first few, are incredibly involved.
image:
  src:
  alt:
tags: ["projects"]
---

### > x86 multi-threaded paravirtualized hypervisor kernel
__Language(s)__: C, x86 assembly

A multi-threaded uniprocessor kernel written from scratch for x86 architecture. The implementation includes drivers for timer, keyboard and CRTC console. Also includes synchronization primitives like mutexes, conditional variables and semaphores. Supports 25 system calls including the core - fork, thread_fork, exec, wait and vanish. The virtual memory implementation supports zero-fill-on-demand (ZFOD) for performance. Extended to support hosting guest kernels using paravirtualization. Tested and debugged using Intel Simics simulator.

- Implemented a loader utilized for loading kernel code, as well as new programs using exec().
- Implemented virtual memory using recursive directories, for easy access to page tables' entries. Virtual memory uses zero-fill-on-demand (ZFOD) approach for quick allocation of frames and population of page table entries. Page tables are dynamically allocated/freed, as and when pages get mapped/freed in an address space, using physical memory judiciously. Kernel memory is limited and direct-mapped, much like linux, therefore all page tables are offloaded from the kernel memory to be able to support more simultaneous processes. Kernel memory houses kernel stacks for threads, PCBs and TCBs, as well as page directories.
- Implemented various system calls including the core - fork, thread_fork, exec, wait and vanish. Implementation also has support for per-thread software exception handlers defined by the user and run in user-space in the event of a subset of exceptions, supporting dynamic registration/de-registration of these handlers.
- Implemented preemptible handlers for page faults/general exceptions.
- Extended the implemention to support simultaneous multi-threaded guest kernels alongside user programs using paravirtualization, supporting time-slicing between guests; using hypercalls for privileged instructions, and modeling virtual interrupts with support for queueing multiple virtual interrupts.

### > C0 Compiler with compiler optimizations
__Language(s)__: Rust

A compiler for C0, an unambiguous and memory-safe subset of the C language designed at Carnegie Mellon University. The implementation involves lexing, parsing and elaboration, type and scope checking, intermediate representations, instruction selection and conversion to x86 assembly and LLVM IR, with various compiler optimizations. Used Rust to architect and implement the entire project.

- Implemented memory-safety as part of memory operations - array accesses, struct field access and pointer dereferences, including NULL checks and length checks, along with other safety checks like shift quantity checks and division by zero; and strong type information across intermediate representation transformations.
- Compiler optimizations implemented as part of the project involve edge-split Static Single Assignment (SSA) form implementation with SSA-based optimizations - Simple and conditional constant/copy propagation with constant folding and constant conditionals, dead code elimination, common subexpression elimination, redundant instruction removal and reachability analysis for unreachable block removal.
- Other optimizations include Register allocation using Maximal cardinality search (MCS) based Greedy graph coloring, register coalescing, function inlining and tail call elimination, and gained parity with 
- Balanced compilation and execution times using weighted heuristics to determine use/disuse of analysis/transformation passes.
- Supported LLVM IR as a target to leverage LLVM-based transformations and analyses for further optimized binaries.

### > Real-time embedded kernel and file system
__Language(s)__: C, ARMv7 assembly

A full-fledged kernel on Cortex M4 microprocessor using ARMv7 assembly and C, capable of multi-threading and context-switching, task scheduling and synchronization using Original Priority Ceiling Protocol ([O]PCP). 

More details on implemented components:
- Drivers for modules like Successive approximation analog-to-digital-converter (SAADC), I2C compatible two-wire interface (TWI), general purpose input output (GPIO), and Pulse-width modulation (PWM).
- Handled peripheral data and timers utilizing events and interrupts; built a system call interface with newlib
- Implemented users and a full-fledged file-system on top of the Operating System for the microprocessor, along with a shell to interact with the filesystem, supporting owner-based permissions.

### > WASM interpreter and JIT compiler
__Language(s)__: C++, WebAssembly (WASM), x86 assembly

A virtual machine runtime for WebAssembly, supporting interpretation of a subset of WASM opcodes. Devised a custom ABI for Just-in-time (JIT) compilation of WASM bytecode and native x86-64 assembly execution. Also supported dynamic profiling for the runtime using probes (cache, memory and instruction profiling).

### > TCP Reno congestion control Protocol
__Language(s)__: C

Implemented TCP Reno congestion control algorithm with fast-recovery and out-of-order packet handling.

### > Multi-threaded Caching Web Proxy
__Language(s)__: C

Implemented Multi-Threaded web proxy server that handles concurrent clients and services HTTP/1.0 requests for static web pages. Added LRU caching to handle repeated requests to web objects faster.

### > Dynamic memory allocator
__Language(s)__: C

Implemented a likeness of C's dynamic memory allocator (malloc), managing free blocks using segregated lists and supporting coalescing, block splitting and encoded mini blocks for efficient memory utilization, and greater throughput.

### > Tiny Shell
__Language(s)__: C

Implemented a shell capable of foreground and background job handling using Signal handlers and process system calls (fork(), execve() etc.).\
_Signals: SIGCHLD, SIGINT, SIGSTP_

### > HTTP 1.1
__Language__: C

Implemented HTTP 1.1 text-based protocol with pipe-lining and persistent connections.

### > Mixnet
__Language__: C

Implemented packet mixer with Spanning tree protocol (STP) and link state algorithm using Dijkstra's shortest path algorithm, supporting route randomization.
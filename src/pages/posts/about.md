---
layout: ../../layouts/post.astro
title: "About Me"
pubDate: 2024-08-20
description: "About Me"
author: "karanprs"
excerpt: Additional details about my academic and professional background. This post mainly covers information about my schooling, college, projects and interests, and can be considered as a personal statement.
image:
  src:
  alt:
tags: ["about"]
---

My hometown is Jammu, Jammu and Kashmir (J&K), India. I can be referred to as _Karan_, _Karan Pratap_, _Pratap_ and _Karan Pratap Singh_, but never _Karan Singh_.

## Mindset and Academic Background
Computer Science was the natural choice as a major in my undergraduate education. In my junior and sophomore years, I once attempted to build a desktop computer from scratch and witnessed it coming to life. My peers regarded me as the first stop for fixing their code or faults with their OS installations. These instances were reminiscent of my excitement and gratification on designing my first webpage as a kid, and incited feelings that have stuck with me throughout the years - the satisfaction of seeing my creation in action, of understanding and dissecting seemingly complex stuff. Coding and mathematics are a respite for me; something absolute and logical, in a world where our every attempt to subdue, categorize and comprehend natural phenomena is ridden with exceptions and unreliabilities. I am attracted to the beauty of these subjects, which lies in how absolute they are, devoid of biases, and thus the only means capable of driving real change. I have come to view software as the intangible manifestation of logical thought, capable of producing very tangible effects, and solving real-world problems, whose existence we may not even realize. 

I obtained my undergraduate degree in Computer Science and Engineering from [Visvesvaraya Technological University, Belagavi](https://vtu.ac.in/en/) in 2020 and am currently pursuing my master's degree in Systems and Networking (MSIN) from [Carnegie Mellon University](https://www.cmu.edu). My main interests lie in systems software design and implementation. I have undertaken some of the most rigorous project-based systems courses at CMU, including [Compiler Design](https://www.cs.cmu.edu/~janh/courses/411/24/index.html), and [Operating Systems Design and Implementation](https://www.cs.cmu.edu/~410/), which I have in my fall 2024 schedule. Other project-heavy systems courses I have taken include [15-213/513: Introduction to Computer Systems](https://www.cs.cmu.edu/~213), [15-441/641: Networking and the Internet](www.myheartisinthenetwork.com) and [14-642: Introduction to Embedded Systems](https://mews.sv.cmu.edu/teaching/14642/).

## Interests and Professional Background
I worked as a Software engineer at [Cisco](www.cisco.com), Bangalore, India for a little over 2 years as a Software Engineer in the SDN domain before deciding to go beyond the abstractions that were proving quite frustrating. I developed an interest in low-level programming and computer systems and started pursuing my master's degree in Fall 2023 from CMU, concentrating on [Networks and Systems](https://www.cmu.edu/ini/academics/msin/). I fell deeply in love with CMU systems after taking [15-213/513: Introduction to Computer Systems](https://www.cs.cmu.edu/~213) during the summer of 2023, following which I have mainly concentrated on systems courses. 

During the summer of 2024, I worked as an Embedded Software Engineer Intern at [SIL4 Systems Inc.](https://sil4systems.com/), a Pittsburgh-based innovative supplier of affordable safety and control system products and services for rail transit, railroad and industrial markets worldwide. I worked with a custom development board, researching and testing peripherals, including SPI, EMAC, UART etc., reading and writing driver level code and dealing with assembly on a regular basis whilst debugging. Alongside this internship, I also worked as a teaching assistant for _15-213/513: Introduction to computer systems_ with the department of Computer Science (SCS) at CMU.

## Projects
### > C0 Compiler with compiler optimizations
__Language(s)__: Rust\

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
### > TCP Reno congestion control Protocol
__Language(s)__: C

Implemented TCP Reno congestion control algorithm with fast-recovery and out-of-order packet handling.
### > Multi-threaded Caching Web Proxy
__Language(s)__: C

Implemented Multi-Threaded web proxy server that handles concurrent clients and services HTTP/1.0 requests for static web pages. Added LRU caching to handle repeated requests to web objects faster.
### > Dynamic memory allocator
__Language(s)__: C

Implemented a likeness of C's dynamic memory allocator (malloc), managing free blocks using segregated lists and supporting coalescing, block splitting and mini blocks for efficient memory utilization, and greater throughput.
### > Tiny Shell
__Language(s)__: C

Implemented a shell capable of foreground and background job handling using Signal handlers and process system calls (fork(), execve() etc.).\
_Signals: SIGCHLD, SIGINT, SIGSTP_
### > HTTP 1.1
__Language__: C

HTTP 1.1 text-based protocol with pipe-lining and persistent connections.

### > Mixnet
__Language__: C

Implemented packet mixer with Spanning tree protocol (STP) and link state algorithm using Dijkstra's shortest path algorithm, supporting route randomization.
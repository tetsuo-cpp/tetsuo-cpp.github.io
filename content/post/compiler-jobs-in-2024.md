+++
date = 2024-02-04
title = "What does a compiler job look like in the year 2024?"
authors = ["Alex Cameron"]
[taxonomies]
tags = ["compiler"]
+++

When people think of a job working on compilers, they usually imagine a job working on a general purpose compiler/runtime that they use in their day-to-day work such as: Clang, V8, MSVC, Roslyn, etc.
While those jobs do exist, they make up just one slice of the pie that is the compiler job market.

While there are resources out there listing companies that do compiler work (namely the invaluable [CompilerJobs](https://mgaudet.github.io/CompilerJobs/) page), I thought it'd be useful to write up a post talking about what **types** of roles are out there.
Every company and job is unique but there are some broad categories of compiler jobs that fit under the same umbrella.
I figured it'd be useful to enumerate those categories and hopefully give a sense of the variety of roles available.

Compiler jobs can be quite diverse so I think it's useful to identify exactly what interests you about the field.
For example, if you love programming language design and type systems, it wouldn't make sense for you to work at an AI hardware accelerator startup.
Similarly, if you're interested in compiler optimisation, working on a static analysis tool probably wouldn't scratch your particular itch.

# General purpose programming languages

These are the technologies that everyone thinks about when we talk about compilers and runtimes.
Think C++, Java, JavaScript, Python, etc.

General purpose programming languages are, generally speaking, not monetisable.
This means that this type of development is part of a broader company strategy and is usually the domain of larger companies that have the resources to fund this R&D and have a heavy investment in a particular language/stack and want to guide its direction to ensure that their interests are represented in the open-source community.

# Embedded

There are a number of companies developing specialised compiler toolchains for embedded applications.
For the most part, these are C compilers although Pascal and Ada do exist.

Interestingly, this is one niche where the practice of selling compiler licenses still thrives.
Usually, these compilers have support for unusual architectures or have some other features such as a focus on code size optimisation or being formally certified in some way that justify their pricetag over open-source alternatives like GCC.

Some players in this area are:
* ARM
* SEGGER
* Green Hills Software

# GPU

# Domain specific hardware accelerators

With the end of Moore's law, there's incentive to develop specialised hardware that is designed to tackle specific applications more efficiently.
There's a great talk from Chris Lattner about this.

The most common application is machine learning.
The development of new hardware and ISAs necessitates new compilers to target them.
These compilers are untypical in that they often don't have a source language in the conventional sense as they're trying to lower ML models (Tensorflow, PyTorch, ONXX, etc) to the hardware.

Some players in this area are:
* FAANG (Google TPU, Amazon Inferentia, etc)
* Groq
* Tenstorrent
* d-Matrix

# Crypto

# Static analysis

There are a number of companies with a <abbr title="Software as a Service">SaaS</abbr> offering for statically analysing code.
Most of these are part of a larger suite of security-focused tools.

Some players in this area are:
* Synopsys (Coverity)
* Perforce (Klocwork)
* Snyk
* Praetorian

# Security research

[DARPA](https://www.darpa.mil/) funds a lot of security research that involves compiler-adjacent problems such as: program analysis, decompilation, binary patching, etc.

You can think of these jobs as a blend of academia and industry as they deal with cutting edge ideas and the result of this research is usually a proof-of-concept to pave the way for further research.

Some players in this area are:
* Trail of Bits
* Galois
* GrammaTech

# Domain specific languages

There's a certain school of thought that believes that the most efficient way to solve a problem is to write a specialised language for a given domain.
The most widespread example of that is SQL!
This category is a bit of a catch-all as a lot of these use-cases don't have much in common but the point is that small specialised languages exist **everywhere**.

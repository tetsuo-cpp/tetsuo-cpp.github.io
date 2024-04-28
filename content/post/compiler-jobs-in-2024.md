+++
date = 2024-04-27
title = "What does a compiler job look like in the year 2024?"
authors = ["Alex Cameron"]
[taxonomies]
tags = ["compiler", "industry"]
+++

When people think about compiler development, they usually imagine a job working on a general purpose compiler/runtime that they use in their day-to-day work such as Clang or V8.
While those jobs do exist, they make up just one slice of the pie that is the compiler job market.

There are resources out there listing companies that do compiler work (namely the invaluable [Compiler Jobs](https://mgaudet.github.io/CompilerJobs/) page), however I thought it'd be useful to write up a post talking about what **types** of roles are out there.

In this post, I'm necessarily talking about parts of the industry that are outside of my own personal experience.
If you feel that I've omitted or mischaracterised something, shoot me an email and I'll fix it.

# General purpose programming languages

These are the technologies that we mentioned earlier.
Think compilers and runtimes for C++, Java, JavaScript, Python, etc.
I'd put compiler infrastructure such as [LLVM](https://llvm.org/), [Cranelift](https://cranelift.dev/) and [GraalVM Truffle](https://www.graalvm.org/latest/graalvm-as-a-platform/language-implementation-framework/) under this category too.

Toolchains for general purpose programming languages are, generally speaking, not directly monetisable.
This means that this type of development is usually part of a broader company strategy and, with a few exceptions, tends to be the domain of larger companies that have a heavy investment in a particular language/stack and want to represent their interests in the open-source community.

One way to get an idea of what companies hire contributors is to clone one of these projects and see what corporate emails turn up in `git log`.

Examples:
* Google, Apple, Microsoft, et al
* [Red Hat](https://www.redhat.com/)
* [Mozilla](https://www.mozilla.org/)
* [Igalia](https://www.igalia.com/technology/compilers)

# Embedded

There are a number of companies developing specialised compiler toolchains for embedded applications.
For the most part, these are C/C++ compilers although Pascal and Ada do exist.

These compilers are often from the hardware vendors themselves and come with an IDE, build system, etc.
There are also third-party toolchains that have a focus on code size optimisation or are formally certified in some way to justify their pricetag over the hardware vendor's toolchain or open-source alternatives like GCC.
Interestingly, this is one niche where the practice of selling compiler licenses still thrives.

Examples:
* [ARM](https://www.arm.com/)
* [Qualcomm](https://www.qualcomm.com/)
* [Green Hills Software](https://www.ghs.com/)
* [AdaCore](https://www.adacore.com/)
* [SEGGER](https://www.segger.com/)

# Hardware accelerators

With improvements in processor performance diminishing in recent years, there's an incentive to develop *domain specific hardware* that is designed to tackle certain applications more efficiently.
Chris Lattner did a great talk on this topic [here](https://www.youtube.com/watch?v=4HgShra-KnY).
The development of new hardware and <abbr title="Instruction Set Architecture">ISA</abbr>s necessitates new compilers to target them.

The most common application is machine learning.
These compilers are unusual in that they often don't have a source language in the conventional sense as they're trying to lower ML models (Tensorflow, PyTorch, ONNX, etc) to hardware.

I'll go ahead and throw GPU compiler stacks such as NVIDIA's [CUDA](https://developer.nvidia.com/cuda-toolkit) and AMD's [ROCm](https://www.amd.com/en/products/software/rocm.html) under this category too as they share some similarities.

Examples:
* [Google TPU](https://cloud.google.com/tpu)
* [Amazon Inferentia](https://aws.amazon.com/machine-learning/inferentia/)
* [Groq](https://groq.com/)
* [Tenstorrent](https://tenstorrent.com/)
* [Fabric Cryptography](https://www.fabriccryptography.com/)

# Web3

There are a number of companies in the Web3 space that are developing programming languages for writing smart contracts and <abbr title="Decentralised Applications">dApps</abbr>.
The most widespread of these is [Solidity](https://soliditylang.org/), a language designed to target the Ethereum network's <abbr title="Ethereum Virtual Machine">EVM</abbr>.

Since the introduction of the EVM, there have been a growing number of networks with their own virtual machines, smart contract languages, toolchains, etc.

Examples:
* [Solana](https://solana.com/)
* [DFINITY](https://dfinity.org/)
* [Aleo](https://aleo.org/)

# Static analysis

There are a number of companies with a <abbr title="Software as a Service">SaaS</abbr> offering for statically analysing code.
These often come as part of a larger suite of security-focused tools.

Unlike the basic static analysis implemented in most compilers, these dedicated tools usually have cross-language support and provide more in-depth analysis such as: detecting security vulnerabilities (e.g. SQL injection), checking code quality or adherence to style guides, and analysis that would be too intensive to run as part of a developer's edit-compile-run workflow.

Most of these tools are heavily customisable and in the case of CodeQL, can be extended with a query language.

Examples:
* [Synopsys Coverity](https://scan.coverity.com/)
* [Perforce Klocwork](https://www.perforce.com/products/klocwork)
* [Snyk](https://snyk.io/)
* [GitHub CodeQL](https://codeql.github.com/)
* [Praetorian](https://www.praetorian.com/)

# Security research

[DARPA](https://www.darpa.mil/) funds a lot of security research that involves compiler-adjacent problems such as: program analysis, decompilation, binary patching, etc.

These projects are a blend of academia and industry as they are often about validating novel ideas and producing proof-of-concepts to pave the way for further research rather than building industry-grade implementations.

Examples:
* [Trail of Bits](https://www.trailofbits.com/)
* [Galois](https://galois.com/)
* [GrammaTech](https://www.grammatech.com/)

# Domain specific languages

There's a certain school of thought that believes that the most efficient way to solve a problem is to write a specialised language for a given domain.
The most widespread example of that is SQL!
These small languages or *DSLs* are used for everything from querying databases to scripting game engines.

Database query languages are a particularly interesting example as, internally, most database systems contain a query compiler that performs optimisations to the query and outputs a *query plan* that outlines how to access and transform data in an efficient way.
If you squint a bit, this looks a lot like traditional compiler optimisation.

This category is a bit of a catch-all as a lot of these use-cases don't have much in common but the point is that these small specialised languages exist **everywhere**.
I've expanded on the examples below to give you a sense of just how diverse this category is.

Examples:
* [Roblox](https://www.roblox.com/): Building a Lua variant called [Luau](https://luau-lang.org/) for scripting the Roblox game engine.
* [Snowflake](https://www.snowflake.com/en/): Building a query compiler for the Snowflake SQL Engine.
* [Lokad](https://www.lokad.com/): Building a DSL for representing supply chain optimisation problems.
* [Workday](https://www.workday.com/): Building in-house proprietary programming languages for development of the Workday platform.

# 05. Programming & Software

!!! info
    - Week: 7
    - Rahida Asadli, Ismayil Shahaliyev
    - Created: Nov 9 2025
    - Updated: Dec 20 2025

# Programming

_Programming_ is the process of taking an algorithm and writing it in a language that a computer can understand and execute. This language is called a [programming language](https://en.wikipedia.org/wiki/Programming_language).

A computer does not understand programming languages directly. It only understands [machine code](https://en.wikipedia.org/wiki/Machine_code): very low-level instructions represented in binary (0s and 1s) that tell the CPU exactly what to do. A programming language is therefore a human-readable [abstraction](https://en.wikipedia.org/wiki/Abstraction_%28computer_science%29) that must be translated into machine code before execution.

Every programming language has rules about how things must be written. These rules are called **syntax**. If syntax rules are violated, the program will not run. Even with correct syntax, a program may still behave incorrectly. This is a matter of **semantics**, which concerns meaning.

!!! note
    **Example.**  
    `x = 5 + ;` is a syntax error.  
    `x = "Hello" - 3` is syntactically valid but semantically meaningless.

## Compiler vs Interpreter

A **compiler** translates the entire source code into machine code or an intermediate representation _before_ execution. The result is usually an executable file or [bytecode](https://en.wikipedia.org/wiki/Bytecode). Compilation detects many errors early and produces fast-running programs, but requires recompilation after changes and often targets a specific platform.

An **interpreter** translates and executes code instruction by instruction during execution. It produces no separate executable. Interpreted programs are easier to test and modify but usually run more slowly and depend on the interpreter at runtime.

Compiled languages are typically used where predictable performance is critical, such as mobile apps and games. Interpreted languages are common in scripting, automation, and rapid prototyping.

**Important.** Many modern interpreted languages use [just-in-time compilation](https://en.wikipedia.org/wiki/Just-in-time_compilation), blurring the traditional distinction. The key difference today is when and how translation occurs.

!!! note
    **Example (Oversimplified).**

    Program:
    ```text
    print("Hello")
    print(10 + 5)
    ```

    Interpreter example:
    ```text
    print("Hello")
    print(10 + 5)
    print(10 / 0)
    print("This will not run")
    ```

    The interpreter executes line by line and stops at the error.

## Evolution of Programming Languages

Programming languages have evolved to make interaction between humans and computers more natural and productive. Each generation increases the level of abstraction, moving further away from hardware details and closer to human concepts.

**First generation (Machine language).**  
Programs consist entirely of binary instructions (0s and 1s). These instructions are executed directly by the CPU. While extremely fast, they are almost impossible for humans to read, write, or debug.

```text
10110000 00000101
10110001 00000110
00000001

**Second generation  (Assembly language).**
Assembly replaces raw binary with symbolic instructions that correspond closely to machine operations. Programs are still hardware-specific and must be translated by an assembler.

```text
MOV AX, 5
MOV BX, 6
ADD AX, BX

**Third generation (High-level languages).**  
High-level languages use English-like words, familiar mathematical notation, and structured control flow. They are designed to be readable, portable, and independent of specific hardware. Programs written in these languages are translated using compilers or interpreters, allowing the same source code to run on different machines with little or no modification.

```text
a = 5
b = 6
sum = a + b
print(sum)

**Fourth generation (Very high-level languages).**
Very high-level languages aim to minimize the amount of code a programmer must write. Instead of specifying detailed procedures, the programmer describes what result is desired. These languages are often domain-specific and commonly used in databases, reporting, and data analysis.

```text
SELECT * FROM users WHERE name = 'Codd'

**Fifth generation (Logic-based languages).**
Logic-based languages are founded on formal logic rather than step-by-step instructions. The programmer defines facts and rules, and the language engine derives conclusions automatically through inference. Control flow is implicit rather than explicitly programmed.

```text 
parent(alice, bob).
parent(bob, carol).

ancestor(X, Y) :- parent(X, Y).
ancestor(X, Y) :- parent(X, Z), ancestor(Z, Y).


Example queries:
```text
?- parent(alice, bob).
?- ancestor(alice, carol).
?- ancestor(X, carol).

**Post-fifth generation (Generative AI systems).**
In modern computing, many systems are no longer programmed with explicit rules or logical facts. Instead, they are trained on large datasets using machine learning techniques. These systems learn statistical patterns that allow them to generate text, code, images, or actions in response to user prompts. They do not guarantee logical correctness, but they are effective at handling ambiguity, incomplete information, and complex real-world inputs. This shift represents a new interaction paradigm rather than a traditional new generation of programming languages.

# Software

[Software](https://en.wikipedia.org/wiki/Software) consists of computer programs and related documentation that instruct a computer on how to perform tasks. Software translates human intentions into machine-level operations and enables computers to carry out activities ranging from simple calculations to complex simulations and system control.

[System software](https://en.wikipedia.org/wiki/System_software) is responsible for managing and operating computer hardware. It provides the foundational environment in which other programs can run and ensures that resources such as memory, processing time, and input/output devices are used efficiently.

| Type | Purpose | Examples |
| --- | --- | --- |
| Operating systems | Manage hardware and system resources | Windows, macOS, Linux |
| Device drivers | Enable communication with hardware devices | Printer driver, GPU driver |
| Utility programs | Perform maintenance and optimization tasks | File manager, disk cleanup, antivirus |

!!! note
    When a computer is powered on, the operating system loads first. It initializes hardware components, loads necessary drivers, and prepares the system so that application programs can be executed.

[Application software](https://en.wikipedia.org/wiki/Application_software) consists of programs designed for end users to perform specific tasks. These include productivity tools, creative software, communication applications, and educational programs.

!!! note
    A user may write documents in LibreOffice or Microsoft Word (application software) running on Ubuntu or Windows (system software), while device drivers handle communication with hardware such as the graphics card and printer.

In addition to their functional role, software systems can be categorized by how they are licensed and distributed. **Proprietary software** is owned and controlled by a company and typically requires a paid license, offering professional support and regular updates. **Open-source software** makes its source code publicly available, allowing users to inspect, modify, and redistribute it. Organizations choose between these models based on cost, security requirements, support needs, and technical expertise.

!!! note
    **Exercise.** Compare the advantages and disadvantages of proprietary and open-source software.

## Operating Systems

An [operating system](https://en.wikipedia.org/wiki/Operating_system) (OS) is the core software that manages a computer’s hardware and software resources. It acts as an intermediary between users, applications, and the underlying hardware, translating high-level requests into low-level operations and coordinating all system activity.

!!! note
    **Example.** A user edits a document, listens to music, and downloads a file at the same time. The operating system schedules CPU time, allocates memory, and manages input/output so all tasks proceed smoothly without interfering with one another.

The [kernel](https://en.wikipedia.org/wiki/Kernel_%28operating_system%29) is the central component of an operating system. It directly controls the CPU, memory, storage, and devices. Users do not interact with the kernel directly; instead, applications make requests that the kernel validates and executes safely.

!!! note
    **Example.** When an application saves a file, it sends a request to the operating system. The kernel checks permissions, allocates disk space, and communicates with the storage device through drivers, ensuring system stability and data integrity.

The kernel is also responsible for [multitasking](https://en.wikipedia.org/wiki/Computer_multitasking). When multiple programs run simultaneously, the kernel rapidly switches the CPU between them, giving each program a small time slice. This creates the illusion that all programs are running at the same time.

An operating system includes more than just the kernel. It also contains system libraries, background services, device drivers, and user interfaces. Different operating systems can be built around the same kernel. For example, Ubuntu and Android both use the Linux kernel but provide very different environments and user experiences.

# Additional Material

- https://www.youtube.com/embed/l26oaHV7D40
- https://www.youtube.com/embed/_C5AHaS1mOA
- https://www.youtube.com/embed/CFRhGnuXG-4
- https://www.youtube.com/watch?v=26QPDBe-NB8
- https://www.youtube.com/watch?v=H2tuKiiznsY
- https://www.youtube.com/watch?v=PK_yguLapgA
- https://www.youtube.com/watch?v=niWpfRyvs2U


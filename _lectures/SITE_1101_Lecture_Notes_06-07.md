---
layout: page
title: Week 06-07 — Algorithms, Programming & Programming Languages
order: 4
---
{% include lecture-styles.html %}

**Authors:** Rahida Asadli, Nilufar Ismayilova, Rahman Karimov, Ismayil Shahaliyev

**Created / Updated:** Nov 9 2025 **/** Nov 9 2025

{% include reading-time.html %}
<button id="toc-toggle">☰ Sections</button>

<div id="toc-panel">
  <h4>On this page</h4>
  <ul>
    <li><a href="#algorithm">Algorithm</a></li>
    <li><a href="#programming-and-programming-languages">Programming & Languages</a></li>
    <li><a href="#evolution-of-programming-languages">Evolution of Languages</a></li>
    <li><a href="#additional-material">Additional Material</a></li>
  </ul>
</div>

# Algorithm

An [**algorithm**](https://en.wikipedia.org/wiki/Algorithm) is a step-by-step procedure or set of rules to solve a specific problem or perform a task. It is like a recipe in cooking: you follow a clear sequence of actions to achieve a specific result. In computer science, algorithms receive some input, process it in a logical way, and produce an output. What makes a good algorithm is that it has a clear starting point, a clear ending point, and every step is unambiguous, meaning that there is no confusion about how it should be executed.
<div class="frame" markdown="1">

**_Example._** Imagine you want to find the largest of three numbers: A, B, and C. A simple algorithm would say: first compare A and B. If A is greater than or equal to B, then compare A with C. If A is still the greatest, then A is the largest number. Otherwise, C is the largest. But if in the very first comparison B was already greater than A, then compare B with C, and whichever is larger is the answer. This exact set of steps can be written in code or performed by a person.
</div>

### Programming and Programming Languages

Programming is the process of taking an algorithm and writing it in a language that a computer can understand and execute. This language is called a [programming language](https://en.wikipedia.org/wiki/Programming_language). Every programming language has rules about how things must be written. These rules are called **_syntax_**. If you break the syntax rules, the computer will show an error and will not run the program.

However, even if your syntax is correct, your program may still not work the way you expect. That is where **_semantics_** comes in. Semantics refers to the meaning behind each statement.
<div class="frame" markdown="1">

**_Example._** The instruction x = 5 + ; is a syntax error because the grammar is wrong. But the instruction x = "Hello" - 3 is syntactically correct but semantically meaningless, because subtracting a number from a word makes no logical sense.
</div>
A **compiler** is a program that translates the entire source code of a program (written in a high-level language like C, C++, Java) into machine code _before_ the program runs. The output of this translation is usually an executable file (.exe, .out) or bytecode. Think of a compiler like a translator who reads a whole book, understands it fully, and then produces a translated version. After that, you can read the translated book without the translator.

An **interpreter** reads the source code line by line (or instruction by instruction), translating and executing on the spot. It does not create a separate executable file. Think of an interpreter like a live translator who translates every sentence as the speaker is talking. If you want to hear the speech again, you need the interpreter present.

| **Feature** | **Compiler** | **Interpreter** |
| --- | --- | --- |
| Translation | Whole program at once | Translates line by line |
| --- | --- | --- |
| Execution speed | Faster | Slower |
| --- | --- | --- |
| Error Detection | All errors shown after compilation | Stops at first error |
| --- | --- | --- |
| Output | Executable file | No executable |
| --- | --- | --- |
| Good for | Large, performance-heavy apps | Scripting, teaching, quick testing |
| --- | --- | --- |

<div class="frame" markdown="1">

**_Example._** A compiler is used when you are building a program that needs to run extremely fast and operate efficiently on a specific device. For example, imagine you are developing an iOS mobile app, such as a fitness tracker or a game. These kinds of applications need smooth performance, fast loading times, and good battery efficiency. In this situation, the entire program is compiled beforehand into machine code that the phone's processor understands directly. Once the app is compiled, users can download and run it without needing any additional tools. This makes compiled languages like Swift and C++ ideal for performance-critical, professional software that will be distributed to many users.

An interpreter is used in a very different scenario. Imagine you are at work and need to quickly automate a small task, such as renaming dozens of files, scraping some data from a website, or processing a spreadsheet. You don't want to wait for a full compile step and you want to be able to test each part of the script immediately. In this case, using an interpreted language like Python makes sense because you can write a line of code and run it right away. The interpreter reads and executes the code line by line, making debugging much easier and faster. Engineers, researchers, and students often use interpreters for small tools, experiments, and data analysis because the focus is on flexibility and quick testing rather than performance.

**_Example (Workflow)._** Imagine you wrote a short program:
{% highlight c %}

print("Hello")

print(10 + 5)
{% endhighlight %}

**How a Compiler Works (Example: C, C++):**

A compiler reads the _entire program_ first, checks for errors, and then translates the whole code into machine language **before** running it. It is like translating an entire book from English to Azerbaijani, checking everything, and then giving the translated book to the reader.

**In C language:**

1) You write the code in a file called hello.c.

2) You run the compiler: gcc hello.c

3) If no errors, it creates an executable file like a.exe.

4) Only then the program runs and prints the output.

If there is even one error in any line, the program will not run at all.

**How an Interpreter Works (Example: Python, JavaScript):**

An interpreter translates and runs the program line-by-line, one instruction at a time.

It is like a translator standing next to you, you speak one sentence in English, and the translator immediately says it in Azerbaijani.

**Example (Python):**  
If the program is:
{% highlight c %}

print("Hello")

print(10 + 5)

print(10 / 0) # error happens here

print("This will not run")
{% endhighlight %}


**Python** will do the following:

1) It runs the first line → prints **Hello**

2) It runs the second line → prints **15**

3) It runs the third line → finds an error (division by zero) and stops

4) The last line will not run, but the first two lines still worked
</div>

### Evolution of Programming Languages

_Programming languages_ have evolved over time to make communication between humans and computers easier. Early computers could only understand sequences of 0s and 1s, but modern languages allow us to write instructions in a way that is closer to human thinking. This development is divided into generations, where each generation makes programming more abstract, simpler, and more powerful than the previous one.

| **Generation of Language** | **Description** | **Example** |
| --- | --- | --- |
| First-generation language (Machine Language) | Consists only of binary digits 0s and 1s. Directly understood by the computer but extremely difficult for humans to write or debug. | 10110010 |
| --- | --- | --- |
| Second-generation language (Assembly Language) | Uses symbolic codes or abbreviations instead of binary. Easier than machine language, but still closely tied to hardware. Needs an assembler to convert to machine code. | MOV AX, 5 |
| --- | --- | --- |
| Third-generation language (High-Level Language) | Uses English-like words and mathematical symbols. Easier to read, write, and understand. Portable across different machines. | Python, C++, Java |
| --- | --- | --- |
| Fourth-generation language (Very High-Level Language) | Designed to reduce programming effort. Focuses more on what needs to be done rather than how. Often used in databases and report generation. | SQL: SELECT \* FROM users; |
| --- | --- | --- |
| Fifth-generation language (Artificial Intelligence and Logic-Based Language) | Focuses on solving problems using logic and constraints instead of step-by-step instructions. Used in AI, expert systems, and machine learning. | Prolog, AI-based tools |
| --- | --- | --- |

**_Example._** **First-generation language (Machine Language - binary):**
{% highlight c %}

10110000 00000101 ; load 5 into register

10110001 00000110 ; load 6 into register

00000001 ; add
{% endhighlight %}

This is extremely hard to write and understand because it uses only 0s and 1s.

**Second-generation language (Assembly Language):**
{% highlight c %}

MOV AX, 5 ; move 5 into register AX

MOV BX, 6 ; move 6 into register BX

ADD AX, BX ; add BX to AX
{% endhighlight %}

Still hardware-specific but more readable than pure binary.

**Third-generation language (High-Level Language - Python example):**
{% highlight c %}

a = 5

b = 6

sum = a + b

print(sum)
{% endhighlight %}

This looks more like natural language and is easy to understand.

# Additional Material

- [Explain different **types of algorithmic actions** i.e. repetition, modularization, recursion](https://adauniversity-my.sharepoint.com/:v:/g/personal/ayusubov_ada_edu_az/EaKZQecLElVOhojdc9bAng0BIppEl64AdPowJ3S11mRHIA)
- [Explain evolution of **programming language generations** and basic **paradigms**](https://adauniversity-my.sharepoint.com/:v:/g/personal/ayusubov_ada_edu_az/ERc4eyVOErpMsxLiLQVhNvIBABVK45kkgdwsaDUKIr05jg)
- [Differentiate between **compiler** and **interpreter**](https://adauniversity-my.sharepoint.com/:v:/g/personal/ayusubov_ada_edu_az/EX6r5GCMnr1Eh8O0Uk3ag2cBeYOmYykpNcKMn42Odr7l4w)
- [**Programming Basics: Statements & Functions: Crash Course Computer Science #12**](https://www.youtube.com/embed/l26oaHV7D40)
- [**Interpreters and Compilers (Bits and Bytes, Episode 6)**](https://www.youtube.com/embed/_C5AHaS1mOA)
- [**How do Graphics Cards Work? Exploring GPU Architecture**](https://www.youtube.com/embed/h9Z4oGN89MU)
- [**What on Earth is Recursion? - Computerphile**](https://www.youtube.com/embed/Mv9NEXX1VHc)
- [**Binary, Hanoi and Sierpinski, part 1**](https://www.youtube.com/embed/2SUvWfNJSsM)
- [**Why You Shouldn't Nest Your Code**](https://www.youtube.com/embed/CFRhGnuXG-4)

{% include lecture-footer.html %}

---
layout: page
title: Week 03 — Von Neumann Architecture, Binary Representation, Arithmetic & Logic Operations
order: 1
---

{% include lecture-styles.html %}

**Week 03**

**Authors:** Rahida Asadli, Nilufar Ismayilova, Rahman Karimov, Ismayil Shahaliyev

**Created / Updated:** Oct 23 2025 **/** Oct 23 2025

{% include reading-time.html %}


<button id="toc-toggle">☰ Sections</button>

<div id="toc-panel">
  <h4>On this page</h4>
  <ul>
    <li><a href="#von-neumann-architecture">Von Neumann Architecture</a></li>
    <li><a href="#continuous-vs-discrete-analog-vs-digital">Continuous vs Discrete | Analog vs Digital</a></li>
    <li><a href="#bit-byte-data-units">Bit, Byte, Data Units</a></li>
    <li><a href="#number-systems">Number Systems</a></li>
    <li><a href="#binary-arithmetic-and-twos-complement">Binary Arithmetic and Two's Complement</a></li>
    <li><a href="#transistors-and-moores-law">Transistors and Moore's Law</a></li>
    <li><a href="#boolean-logic">Boolean Logic</a></li>
    <li><a href="#additional-material">Additional Material</a></li>
  </ul>
</div>

# Von Neumann Architecture

The [_von Neumann architecture_](https://en.wikipedia.org/wiki/Von_Neumann_architecture) (1945) describes how most computers are structured. It consists of five key components:

| **Component** | **Function** |
| --- | --- |
| Input Unit | Takes data and instructions from external devices (keyboard, sensors, etc.) |
| --- | --- |
| Memory Unit | Stores data and instructions temporarily or permanently |
| --- | --- |
| Arithmetic Logic Unit (ALU) | Performs arithmetic (addition, subtraction) and logic (AND, OR) operations |
| --- | --- |
| Control Unit (CU) | Directs and coordinates all system operations |
| --- | --- |
| Output Unit | Displays or transmits processed information (monitor, printer, etc.) |
| --- | --- |

<p align="center">
  <img src="{{ '/assets/images/lecture02/1.png' | relative_url }}" alt="">
</p>

_Figure 1. Diagram of the von Neumann architecture. Adapted from Von Neumann Architecture, Wikipedia, Wikimedia Commons,_ [_https://en.wikipedia.org/wiki/Von_Neumann_architecture_](https://en.wikipedia.org/wiki/Von_Neumann_architecture)_. Licensed under CC BY-SA 4.0._

Both **data** and **instructions** are stored together in the same memory. This is called the _stored-program concept_. It was an important idea because it allowed computers to keep programs in memory along with the data they use. This made it possible to change or run different programs just by loading new instructions into memory, instead of manually changing the computer's hardware connections. It simplified computer design, enabled automation of complex tasks, and made programming far more flexible.

It is common sense to us now, but only because it became the foundation of all modern computing. Before the stored-program concept, computers like [ENIAC](https://en.wikipedia.org/wiki/ENIAC) had to be rewired by hand for every new task. There was no "program" to load - the hardware was the program. [John von Neumann](https://en.wikipedia.org/wiki/John_von_Neumann)'s idea was radical because it separated hardware (the machine) from software (the instructions it runs) and treated code as just another form of data. That single shift is what made general-purpose computers possible.

In von Neumann architecture, both program instructions and data are stored in _Random Access Memory (RAM)_. _Central Processing Unit (CPU_) sequentially fetches each instruction, executes it, and stores the result. This sequence of _fetch-decode-execute_ cycles forms the basis of computer operation. We will discuss in detail RAM and CPU in the next week.

<div class="frame" markdown="1">

**_Example._** When you use a calculator app to add two numbers, both the program's instructions (e.g. load first number, add, display result) and the numbers you enter are stored in the same memory. The CPU retrieves and executes these instructions one by one, reading the data from memory, performing the addition, and writing the result back, all following the stored-program model.
</div>
While von Neumann solved how a computer could change tasks, another challenge remained: **how should instructions and data be represented?**

# Continuous vs Discrete | Analog vs Digital {#continuous-vs-discrete-analog-vs-digital}

_Continuous_ means values can vary smoothly and without breaks over a range. Between any two values, there are infinitely many possible intermediate values. A classic example is a mercury thermometer: if the temperature is 21 °C and then rises to 22 °C, it passes through 21.1 °C, 21.11 °C, 21.111 °C, and so on - endlessly many points. The temperature does not "jump" from one reading to another; it changes continuously.

_Discrete_ means values change in separate, well-defined steps with no possible values in between. A standard light switch is a simple example: it is either on or off - there's nothing between those two states. Likewise, a digital clock that shows 14:35 jumps straight to 14:36 with no "in-between" time displayed.

This distinction is why _digital_ systems are far more reliable than _analog_ ones. In a continuous analog system, even a tiny fluctuation - a degree in temperature or an electrical noise - can change the value. In a discrete digital system, as long as the signal is close enough to one of the two states (say, above 3 V is "1" and below 1 V is "0"), the computer will interpret it correctly. That tolerance to noise is why modern computers abandoned continuous analog signals and rely almost entirely on discrete binary states.
<div class="frame" markdown="1">

**_Example._** In an analog system, numbers 3 and 5 would be represented by physical quantities - for example, voltage levels of 3 V and 5 V. To add them, the machine might combine the voltages to produce 8 V. But if noise (e.g. temperature) affects hardware and changes voltage levels by just 0.2 V, the output might be 7.8 V or 8.2 V - which no longer corresponds exactly to 8. Repeated operations would accumulate these small errors, making the result unreliable.
</div>
The solution was to abandon continuous analog representation in favor of discrete digital states. Digital circuits only need to distinguish between a small set of clearly separated values, making them far more reliable, scalable, and resistant to noise. Once that decision was made, the simplest and most robust choice was to use two discrete states. This directly matched what electronic components could reliably detect: current flowing or not, voltage high or low, transistor open or closed. Those two states were naturally represented by 0 and 1, forming the [binary number](https://en.wikipedia.org/wiki/Binary_number) system.

# Bit, Byte, Data Units

All digital information - including instructions themselves - is expressed as _bits_ (binary digits, formally introduced by [Claude Shannon](https://en.wikipedia.org/wiki/Claude_Shannon) in the paper [A Mathematical Theory of Communication](https://en.wikipedia.org/wiki/A_Mathematical_Theory_of_Communication)). A _bit_ is the smallest unit of data and can hold one of two values: 0 or 1. Every number, letter, image, or instruction is ultimately **encoded** as sequences of bits.

With two bits, each bit can be either 0 or 1, so there are 2×2=4 [possible combinations](https://en.wikipedia.org/wiki/Cartesian_product): 00, 01, 10, and 11. With three bits, there are 2×2×2=8 combinations: 000, 001, 010, 011, 100, 101, 110, and 111. In general, if you have **N** bits, each bit doubles the number of possible combinations because it can take two independent values. Therefore, the total number of combinations is . This simple rule explains why digital systems scale so effectively: every additional bit doubles the range of values that can be represented.

Eight bits grouped together form a _byte_, the standard unit for representing a single character or small piece of data. For example, the binary sequence 01000001 represents the letter "A" in the [ASCII](https://en.wikipedia.org/wiki/ASCII) encoding system. Larger quantities of data are measured in multiples of bytes: kilobytes (KB), megabytes (MB), gigabytes (GB), and beyond - but all are built on the same binary foundation.

| **Data Unit**      | **Size (in bytes)**     |
|-------------------|--------------------------|
| Bit (b)           | 1 bit                    |
| Byte (B)          | 8 bits                   |
| Kilobyte (KB)     | 10³ bytes  = 1,000 bytes |
| Megabyte (MB)     | 10⁶ bytes  = 1,000,000 bytes |
| Gigabyte (GB)     | 10⁹ bytes  = 1,000,000,000 bytes |
| Terabyte (TB)     | 10¹² bytes = 1,000,000,000,000 bytes |
| Petabyte (PB)     | 10¹⁵ bytes |
| Exabyte (EB)      | 10¹⁸ bytes |
| Zettabyte (ZB)    | 10²¹ bytes |
| Yottabyte (YB)    | 10²⁴ bytes |

<div class="frame" markdown="1">

**_Exercise:_** How many different colors can be represented in an RGB image if each of the three color channels (Red, Green, Blue) is stored using 8 bits?
</div>
# Number Systems

Every piece of data inside a computer - numbers, letters, images, even videos - is represented using _number systems_. A number system defines how we represent and interpret numerical values using a specific set of symbols (digits) and a _base_ that indicates how many symbols are available.

<div class="table-wrapper" markdown="1">

| **System** | **Base** | **Digits Used** | **Example** | **Usage** |
| --- | --- | --- | --- | --- |
| **Decimal (Base-10)** | 10  | 0-9 | 245₁₀ | Used by humans for everyday counting and arithmetic. |
| --- | --- | --- | --- | --- |
| **Binary (Base-2)** | 2   | 0, 1 | 101101₂ | Used internally by all digital computers. |
| --- | --- | --- | --- | --- |
| **Hexadecimal (Base-16)** | 16  | 0-9, A-F | 2AF₁₆ | Used in memory addressing, machine instructions, representing colors, etc. Requires less symbols for describing large numbers. |
| --- | --- | --- | --- | --- |

</div>
**_Decimal System (Base-10)_**

The decimal system uses ten digits (0-9). Each position represents a power of 10.

_Example:_ 245₁₀ = (2 × 10²) + (4 × 10¹) + (5 × 10⁰) = 200 + 40 + 5 = 245₁₀

**_Binary System (Base-2):_**

The binary system uses only two digits: 0 and 1. Each position represents a power of 2.

_Example:_ 1011<sub>2</sub> = (1×2<sup>3</sup>) + (0×2<sup>2</sup>) + (1×2<sup>1</sup>) + (1×2<sup>0</sup>) = 8 + 0 + 2 + 1 = 11<sub>10</sub>

**_Hexadecimal System (Base-16):_**

The hexadecimal system uses digits 0-9 and letters A-F, representing values 10-15.  
Each hex digit equals 4 binary bits.

_Example:_ 2AF<sub>16</sub> = (2×16<sup>2</sup>) + (A×16<sup>1</sup>) + (F×16<sup>0</sup>) = (2×256) + (10×16) + (15×1) = 687<sub>10</sub>

<div class="table-wrapper" markdown="1">

| Decimal | Binary | Hexadecimal | Decimal | Binary | Hexadecimal |
|:------:|:------:|:-----------:|:------:|:------:|:-----------:|
| 0  | 0000 | 0 | 8  | 1000 | 8 |
| 1  | 0001 | 1 | 9  | 1001 | 9 |
| 2  | 0010 | 2 | 10 | 1010 | A |
| 3  | 0011 | 3 | 11 | 1011 | B |
| 4  | 0100 | 4 | 12 | 1100 | C |
| 5  | 0101 | 5 | 13 | 1101 | D |
| 6  | 0110 | 6 | 14 | 1110 | E |
| 7  | 0111 | 7 | 15 | 1111 | F |

</div>

<div class="frame" markdown="1">

**Examples.**

**Decimal → Binary:** To convert **13₁₀** to binary, write it in the powers of two (...16,8,4,2,1): 8+4+1=13. Hence, there is one 8, one 4, zero 2, and one 1: **1101₂**

**Binary → Decimal:** 1011<sub>2</sub> means that there is one 1, one 2, zero 4, and one 8. 1+0+2+8 = 11<sub>10</sub>

**Binary ↔ Hexadecimal:** Group binary digits into 4-bit sets and then convert. 10101110<sub>2</sub> = 1010 1110<sub>2</sub> = AE<sub>16</sub> (1010<sub>2</sub> \= 10<sub>10</sub> = A<sub>16</sub> and 1110<sub>2</sub> \= 14<sub>10</sub> = E<sub>16</sub>)
</div>
<div class="frame" markdown="1">

**Exercise.** Write down different numbers and convert back and forth in different number systems.
</div>
# Binary Arithmetic and Two's Complement

Just like in the decimal system, numbers in the binary system can be added together - but since binary uses only 0 and 1, the addition rules are simpler. Binary addition is one of the most fundamental operations performed by the Arithmetic Logic Unit (ALU) in a computer's CPU.

| **Addition** | **Result** | **Carry** |
| --- | --- | --- |
| 0 + 0 | 0   | 0   |
| --- | --- | --- |
| 0 + 1 | 1   | 0   |
| --- | --- | --- |
| 1 + 0 | 1   | 0   |
| --- | --- | --- |
| 1 + 1 | 0   | 1   |
| --- | --- | --- |

In digital systems, subtraction is often performed using addition. To make this possible, computers represent negative numbers in _two's complement_ form, allowing a single adder circuit to handle both addition and subtraction. A - B → A + (-B)

With 3 bits, we can represent 8 different patterns (. How we interpret those patterns depends on whether we want only positive numbers or both positive and negative. If we choose **unsigned representation**, all 3 bits are used for positive numbers. The patterns go from 000 to 111, which correspond to the numbers 0 through 7.

If we decide to include negative numbers, we can, for example, use one bit as a sign. The first bit indicates whether the number is positive (0) or negative (1), and the remaining two bits show the magnitude: 000 represents +0, 001 is +1, 010 is +2, 011 is +3, and the negative side goes from 100 (-0) to 111 (-3). This wastes one code for "-0" and makes arithmetic incorrect (try subtracting 2 from 1 in with sign bit representation).

**Two's complement** avoids two zeros (-0, and +0) and arithmetic issues. With three bits, the positive numbers still go from 000 (0) to 011 (3), but the negatives start from 100 (-4) to 111 (-1). There is only one zero, and addition or subtraction works naturally without special rules. _To find the negative of any number, we will invert the bits (0 becomes 1, and 1 becomes 0) and add 1 to the result. If there is_ [_overflow_](https://en.wikipedia.org/wiki/Integer_overflow)_, we discard that bit._ That is two's complement.

Instead of memorizing the actions below, see the shared slides on the course page and the study materials for clear understanding.

**_Example 1: Positive Result._** A=7, B=5. Compute A-B using 4-bit binary.

| **Step** | **Operation** | **Result** |
| --- | --- | --- |
| 1   | Write in binary | ( A = 0111₂ ), ( B = 0101₂ ) |
| --- | --- | --- |
| 2   | Invert B → Add 1 | 0101 = 1010 → 1010 + 0001 → **1011₂** |
| --- | --- | --- |
| 3   | Add A + (Two's complement of B) | 0111 + 1011 = **10010₂** |
| --- | --- | --- |
| 4   | Discard carry (leftmost bit) | Result = **0010₂** |
| --- | --- | --- |
| 5   | Convert to decimal | **2₁₀** |
| --- | --- | --- |

**_Example 2: Negative Result._** A=7, B=5. Compute B-A using 4-bit binary.

| **Step** | **Operation** | **Result** |
|---|---|---|
| 1 | Write in binary | A = `0101`<sub>2</sub>, B = `0111`<sub>2</sub> |
| 2 | Two's complement of B | `0111` → invert `1000` → `1000 + 0001` → **`1001`<sub>2</sub>** |
| 3 | Add A + (Two's complement of B) | `0101 + 1001` = **`1110`<sub>2</sub>** |
| 4 | No carry → negative. Find two's complement of result | `1110` → invert `0001`, then `+ 0001` → **`0010`<sub>2</sub>** |
| 5 | Convert to decimal and attach negative sign | **−2**<sub>10</sub> |

<div class="frame" markdown="1">

**Exercise.** Subtract any two numbers in binary.
</div>
# Transistors and Moore's Law

[Transistor](https://en.wikipedia.org/wiki/Transistor) is a tiny electronic switch that controls the flow of electricity. Because computers use binary, transistors are the physical parts that store and process bits. Transistors can turn current on or off, just like a light switch, but they do this automatically using voltage. When a transistor is "on," electricity passes (1), when it's "off," electricity is blocked (0). An _NPN_ transistor has layers forming three parts called the **collector (C)**, **base (B)**, and **emitter (E)**. Giving small charge to base opens up the "gate" for electrons to pass. 
<p align="center">
  <img src="{{ '/assets/images/lecture02/2.png' | relative_url }}" alt="">
</p>
_Figure 2: Symbol for an NPN transistor by Omegatron. This symbol was created with Inkscape by user Omegatron., CC BY-SA 3.0._ [_Wikimedia Commons_](https://en.wikipedia.org/wiki/Transistor#/media/File:BJT_NPN_symbol.svg)_._

Modern computer chips contain billions of transistors packed into an area smaller than a fingernail. In 1965, Intel co-founder Gordon Moore observed that the number of transistors on a chip was roughly doubling every two years, which became known as [Moore's Law](https://en.wikipedia.org/wiki/Moore%27s_law) (which is not a law). It meant that computers kept getting faster, smaller, and cheaper at a steady pace for decades. Although transistor growth has slowed recently due to physical limits (_what kind of limits?_).

# Boolean Logic

All digital logic is based on a simple idea called [Boolean algebra](https://en.wikipedia.org/wiki/Boolean_algebra), named after [George Boole](https://en.wikipedia.org/wiki/George_Boole). In this system, everything can be only **true** or **false**, or in computer terms, **1** or **0**.

There are three main logical operations. **NOT** simply flips the value: 1 becomes 0, and 0 becomes 1. **AND** gives 1 only if both inputs are 1. **OR** gives 1 if at least one input is 1. For example, if one switch is on (1) and another is off (0), AND gives 0 because both are not on.

These simple operations are what every computer uses. Inside a processor, they are built as small electronic parts called **logic gates**, and every complex calculation you see - from adding numbers to running software - comes from millions of these tiny logical steps happening very fast.

### NOT 

<p align="center">
  <img src="{{ '/assets/images/lecture02/3.png' | relative_url }}" alt="">
</p>

| **A** | **Q** |
| --- | --- |
| **0** | **1** |
| --- | --- |
| **1** | **0** |
| --- | --- |

_Figure 3: NOT logic gate symbol. Source: Inductiveload, "NOT symbol,"_ [_Wikimedia Commons_](https://commons.wikimedia.org/wiki/File:NOT_ANSI_Labelled.svg%20-%20/media/File:NOT_ANSI_Labelled.svg) _(Public Domain)._

### AND 

| **A** | **B** | **Q** |
| --- | --- | --- |
| 0   | 0   | 0   |
| --- | --- | --- |
| 0   | 1   | 0   |
| --- | --- | --- |
| 1   | 0   | 0   |
| --- | --- | --- |
| 1   | 1   | 1   |
| --- | --- | --- |

<p align="center">
  <img src="{{ '/assets/images/lecture02/4.png' | relative_url }}" alt="">
</p>

_Figure 4: AND logic gate symbol. Source: Inductiveload, "AND symbol,"_ [_Wikimedia Commons_](https://commons.wikimedia.org/wiki/File:AND_ANSI_Labelled.svg%20-%20/media/File:AND_ANSI_Labelled.svg) _(Public Domain)._

### OR

| **A** | **B** | **Q** |
| --- | --- | --- |
| 0   | 0   | 0   |
| --- | --- | --- |
| 0   | 1   | 1   |
| --- | --- | --- |
| 1   | 0   | 1   |
| --- | --- | --- |
| 1   | 1   | 1   |
| --- | --- | --- |

<p align="center">
  <img src="{{ '/assets/images/lecture02/5.png' | relative_url }}" alt="">
</p>

_Figure 5: OR logic gate symbol. Source: Inductiveload, "OR symbol,"_ [_Wikimedia Commons_](https://commons.wikimedia.org/wiki/File:OR_ANSI_Labelled.svg%20-%20/media/File:OR_ANSI_Labelled.svg) _(Public Domain)._

### XOR

| **A** | **B** | **Q** |
| --- | --- | --- |
| 0   | 0   | 0   |
| --- | --- | --- |
| 0   | 1   | 1   |
| --- | --- | --- |
| 1   | 0   | 1   |
| --- | --- | --- |
| 1   | 1   | 0   |
| --- | --- | --- |

<p align="center">
  <img src="{{ '/assets/images/lecture02/6.png' | relative_url }}" alt="">
</p>

_Figure 6: XOR logic gate symbol. Source: Inductiveload, "XOR symbol,"_ [_Wikimedia Commons_](https://commons.wikimedia.org/wiki/File:XOR_ANSI_Labelled.svg%20-%20/media/File:XOR_ANSI_Labelled.svg) _(Public Domain) ._

<div class="frame" markdown="1">

**Exercise.** How would you implement XOR by using the three main gates? You can use online [digital logic simulator](https://logic.ly/demo/).

**Exercise.** Use logic gates to add any two single-bit binary numbers. Which gates would you use? _Hint:_ See addition table above.
</div>
# Additional Material

- [Describe the Principles of the von Neumann architecture](https://adauniversity-my.sharepoint.com/:v:/g/personal/ayusubov_ada_edu_az/EY0jD-kzL_1KnAYt8403P5cB9rNOnHgwPyJCxyCTa4K9ag)
- [Define bit as the smallest unit of data in digital systems, as well as byte and larger units](https://adauniversity-my.sharepoint.com/:v:/g/personal/ayusubov_ada_edu_az/EaQCABFq1uJHpGxHdLqjcMIB8CBsE6Vryo8qqXijXu87pw)
- [Describe the binary/hexadecimal representation of positive integer numbers](https://adauniversity-my.sharepoint.com/:v:/g/personal/ayusubov_ada_edu_az/EY4brFptD3tDsdOLZWJGvYoBaeqrapmvRes_xb7CMtMd3Q)
- [Convert positive integers from decimal to binary and vice-versa](https://adauniversity-my.sharepoint.com/:v:/g/personal/ayusubov_ada_edu_az/EQZhHivqHSRCiTL2fXCoq0IBZ1tV_QSUiKwbhOHIBn9ALQ)
- [Convert positive integers from decimal to hexadecimal and vice-versa](https://adauniversity-my.sharepoint.com/:v:/g/personal/ayusubov_ada_edu_az/EcP8UWDFXgBBlnQe5QfA05AB-kpScwGfBlYrBE32BCGkkA)
- [Describe and compare basic logic operations i.e. NOT, AND, OR, XOR](https://adauniversity-my.sharepoint.com/:v:/g/personal/ayusubov_ada_edu_az/EW5JvN8DqqpIo_zhJ0VObGEBnhj-NsxbAWucTZ3p07znrg)
- [Explain addition of two binary numbers (positive integers)](https://adauniversity-my.sharepoint.com/:v:/g/personal/ayusubov_ada_edu_az/EfdT23BQClJOrU3O3QCRRjEBaX5FtZl0sYb15bRn6YHcEw)
- [Explain subtraction of two binary numbers (positive integers) and the use of two's complement](https://adauniversity-my.sharepoint.com/personal/ayusubov_ada_edu_az/_layouts/15/stream.aspx?id=%2Fpersonal%2Fayusubov_ada_edu_az%2FDocuments%2FSITE-SITE-1101%2Fweek-03-binary-subtraction.mp4&ga=1&startedResponseCatch=true&referrer=StreamWebApp.Web&referrerScenario=AddressBarCopied.view.b6f8c953-c10d-4205-96e7-d25b1511b265)
<hr>

{% include lecture-footer.html %}

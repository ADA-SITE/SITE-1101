# 02. Binary Representation, Arithmetic & Logic Operations

:material-account: Nilufar Ismayilova, Ismayil Shahaliyev  
:material-calendar: Oct 23, 2025 :material-calendar-edit: Jan 30, 2026

## Digital vs Analog

_Discrete_ means values change in separate, well-defined steps with no possible values in between _Continuous_ means values can vary smoothly and without breaks over a range — between any two values, there are infinitely many possible intermediate values.

!!! note
    A standard light switch is either on or off — there is nothing between those two states — hence, is discrete. Likewise, a digital clock that shows `14:35` jumps straight to `14:36` with no "in-between" time displayed. In a mercury thermometer, however, if the temperature is $21°C$ and then rises to $22°C$, it passes through $21.1°C$, $21.11°C$, $21.111°C$, and so on. The temperature does not "jump" from one reading to another. It changes continuously.

This distinction is why _digital_ systems are far more reliable than _analog_ ones. In a continuous analog system, even a tiny fluctuation (temperature drift or electrical noise) can change the value. In a discrete digital system, as long as the signal is close enough to one of the two states (for example, above $3V$ is $1$ and below $1V$ is $0$), the system will interpret it correctly. This tolerance to noise is why modern computers rely almost entirely on discrete binary states.

!!! note
    In an analog system, numbers $3$ and $5$ could be represented by physical quantities such as voltage levels of $3V$ and $5V$. To add them, the machine might combine the voltages to produce $8V$. But if noise shifts levels by just $0.2V$, the output might become $7.8V$ or $8.2V$, which no longer corresponds exactly to $8$. Repeated operations would accumulate these errors, making the result unreliable.

Digital circuits only need to distinguish between a small set of clearly separated values, which makes them more reliable, scalable, and resistant to noise. The simplest and most robust choice for that was the usage two discrete states. This directly matches what electronic components can reliably detect: current flowing or not, voltage high or low, transistor open or closed. Those two states are naturally represented by $0$ and $1$, forming the [binary number](https://en.wikipedia.org/wiki/Binary_number) system.

## Bit, Byte, Data Units

All digital information — including instructions themselves — is expressed as _bits_ (binary digits, formally introduced by [Claude Shannon](https://en.wikipedia.org/wiki/Claude_Shannon) in [A Mathematical Theory of Communication](https://en.wikipedia.org/wiki/A_Mathematical_Theory_of_Communication)). A _bit_ is the smallest unit of data and can hold one of two values: $0$ or $1$. Every number, letter, image, or instruction is ultimately encoded as a sequence of bits.

With two bits, there are `2×2=4` possible combinations: `00`, `01`, `10`, and `11`. With three bits, there are `2×2×2=8` combinations: `000`, `001`, `010`, `011`, `100`, `101`, `110`, and `111`. In general, with $N$ bits, the total number of combinations is $2^N$. Each additional bit doubles the range of values that can be represented.

Eight bits grouped together form a _byte_, the standard unit for representing a single character or a small piece of data. For example, the binary sequence `01000001` represents the letter $A$  in [ASCII](https://en.wikipedia.org/wiki/ASCII). Larger quantities of data are measured in multiples of bytes: kilobytes (KB), megabytes (MB), gigabytes (GB), and beyond.

| **Data Unit** | **Size** | **Data Unit** | **Size** |
| --- | --- | --- | --- |
| Bit (b) | $1$ | Byte (B) | $8$ bits |
| Kilobyte (KB) | $10^3$ bytes | Megabyte (MB) | $10^{6}$ bytes |
| Gigabyte (GB) | $10^{9}$ bytes | Terabyte (TB) | $10^{12}$ bytes |
| Petabyte (PB) | $10^{15}$ bytes | Exabyte (EB) | $10^{18}$ bytes |
| Zettabyte (ZB) |$10^{21}$ bytes | Yottabyte (YB) | $10^{24}$ bytes |


!!! success "Exercise"
    How many different colors can be represented in an [RGB image](https://en.wikipedia.org/wiki/RGB_color_model) if each of the three color channels (Red, Green, Blue) is stored using 8 bits?

## Number Systems

Every piece of data inside a computer — numbers, letters, images, even videos — is represented using _number systems_. A number system defines how we represent and interpret numerical values using a specific set of symbols (digits) and a _base_ that indicates how many symbols are available.

| **System** | **Base** | **Digits Used** | **Example** | **Usage** |
| --- | --- | --- | --- | --- |
| **Decimal** | 10 | 0–9 | 245₁₀ | Everyday counting and arithmetic. |
| **Binary** | 2 | 0, 1 | 101101₂ | Used internally by digital computers. |
| **Hexadecimal** | 16 | 0–9, A–F | 2AF₁₆ | Memory addresses, machine code, colors, compact notation. |

!!! note
    In decimal, binary, hexadecimal systems, each position represents a power of 2, 10, 16, respectively.Hexadecimal system uses 0–9 and A–F for values 10–15. Each hex digit equals 4 binary bits.

    - 245₁₀ = (2×10²) + (4×10¹) + (5×10⁰) = 200 + 40 + 5 = 245₁₀
    - 1011₂ = (1×2³) + (0×2²) + (1×2¹) + (1×2⁰) = 8 + 0 + 2 + 1 = 11₁₀
    - 2AF₁₆ = (2×16²) + (A×16¹) + (F×16⁰) = (2×256) + (10×16) + (15×1) = 687₁₀

| **Decimal** | **Binary** | **Hex** | **Decimal** | **Binary** | **Hex** |
| --- | --- | --- | --- | --- | --- |
| 0 | 0000 | 0 | 8 | 1000 | 8 |
| 1 | 0001 | 1 | 9 | 1001 | 9 |
| 2 | 0010 | 2 | 10 | 1010 | A |
| 3 | 0011 | 3 | 11 | 1011 | B |
| 4 | 0100 | 4 | 12 | 1100 | C |
| 5 | 0101 | 5 | 13 | 1101 | D |
| 6 | 0110 | 6 | 14 | 1110 | E |
| 7 | 0111 | 7 | 15 | 1111 | F |

!!! note
    **Decimal → Binary:** Convert 13₁₀ by writing it as powers of two: 8+4+1=13. Hence 1101₂.
    
    **Binary → Decimal:** 1011₂ means 8+2+1=11, so it is 11₁₀.
    
    **Binary ↔ Hexadecimal:** Group into 4-bit chunks: 10101110₂ = 1010₂ 1110₂ = AE₁₆.

!!! success "Exercise"
    Write down different numbers and convert back and forth between decimal, binary, and hexadecimal.

## Two’s Complement

Just like in the decimal system, numbers in binary can be added together. Since binary uses only $0$ and $1$, the addition rules are simple. Binary addition is a core operation performed by the [Arithmetic Logic Unit (ALU)](../03_hardware) in a CPU.

| **Addition** | **Result** | **Carry** |
| --- | --- | --- |
| 0 + 0 | 0 | 0 |
| 0 + 1 | 1 | 0 |
| 1 + 0 | 1 | 0 |
| 1 + 1 | 0 | 1 |

In digital systems, subtraction is often performed using addition:
$A − B = A + (−B)$. To make this work with the same adder circuit, computers represent negative numbers using [two's complement](https://en.wikipedia.org/wiki/Two%27s_complement).

With 3 bits, there are $2^3 = 8$ different bit patterns. In **unsigned** representation, they represent $0$ to $7$. A naïve "sign bit" approach (one sign bit + magnitude bits) creates two zeros (+0 and −0) and breaks arithmetic in practice. Two's complement avoids these issues. With 3 bits, positives go from `000` (0) to `011` (3), and negatives go from `100` (−4) to `111` (−1). There is only one zero, and addition/subtraction works naturally. To find the negative of a number in two’s complement:

1. Invert the bits
2. Add 1
3. Discard any overflow carry

### Example 1: Positive result

$A=7$, $B=5$. Compute $A - B$ using 4-bit binary.

| **Step** | **Operation** | **Result** |
| --- | --- | --- |
| 1 | Write in binary | A = 0111₂, B = 0101₂ |
| 2 | Two’s complement of B | 0101 → 1010 → 1010 + 0001 = 1011₂ |
| 3 | Add | 0111 + 1011 = 10010₂ |
| 4 | Discard carry | 0010₂ |
| 5 | Convert | 2₁₀ |

### Example 2: Negative result

Compute $B−A$ using 4-bit binary.

| **Step** | **Operation** | **Result** |
| --- | --- | --- |
| 1 | Write in binary | 5 = 0101₂, 7 = 0111₂ |
| 2 | Two’s complement of 7 | 0111 → 1000 → 1000 + 0001 = 1001₂ |
| 3 | Add | 0101 + 1001 = 1110₂ |
| 4 | Interpret as negative | 1110₂ is negative in 4-bit two’s complement |
| 5 | Magnitude (optional) | 1110 → 0001 → +1 = 0010₂ → 2₁₀, so result is −2₁₀ |

!!! success "Exercise"
    Subtract any two numbers in binary using two’s complement.

## Transistors and Moore’s Law


<figure style="margin: 1em 0; text-align: center;">
  <img src="../../assets/images/lecture02/transistor.svg" alt="npn transistor" style="max-width: 80%; height: auto;">
  <figcaption style="margin-top: 0.5em; font-size: 0.9em; opacity: 0.85;">
    By <a href="//commons.wikimedia.org/wiki/User:Omegatron" title="User:Omegatron">Omegatron</a> - <span typeof="mw:File"><a href="//commons.wikimedia.org/wiki/File:W3C_grn.svg" class="mw-file-description"></a></span>&nbsp;The <a href="//commons.wikimedia.org/wiki/Help:SVG" title="Help:SVG">SVG</a> code is <span class="plainlinks" style="background:var(--background-color-success-subtle, #dff2eb); color: inherit;"><a rel="nofollow" class="external text" href="https://validator.w3.org/check?uri=https%3A%2F%2Fcommons.wikimedia.org%2Fwiki%2FSpecial%3AFilepath%2FBJT_NPN_symbol.svg&amp;doctype=Inline">valid</a></span>.<span typeof="mw:File"><a href="//commons.wikimedia.org/wiki/File:Inkscape-yes.svg" class="mw-file-description"></a></span>&nbsp;This symbol was created with <a href="https://en.wikipedia.org/wiki/Inkscape" class="extiw" title="w:Inkscape">Inkscape</a> by user&nbsp;<a href="//commons.wikimedia.org/wiki/User:Omegatron" title="User:Omegatron">Omegatron</a>., <a href="https://creativecommons.org/licenses/by-sa/3.0" title="Creative Commons Attribution-Share Alike 3.0">CC BY-SA 3.0</a>, <a href="https://commons.wikimedia.org/w/index.php?curid=2792640">Link</a>
  </figcaption>
</figure>


Modern computer chips contain billions of transistors packed into an area smaller than a fingernail. In 1965, Intel co-founder [Gordon Moore](https://en.wikipedia.org/wiki/Gordon_Moore) observed that the number of transistors on a chip was roughly doubling every two years, which became known as [Moore’s Law](https://en.wikipedia.org/wiki/Moore%27s_law) (it is not a physical law). This trend made computers faster, smaller, and cheaper for decades.

!!! note
    Transistor scaling has slowed due to physical and engineering constraints such as heat dissipation (power density), leakage currents at very small geometries, and the increasing difficulty and cost of manufacturing at nanometer scales.

## Logic Gates

All digital logic is based on [Boolean algebra](https://en.wikipedia.org/wiki/Boolean_algebra), named after [George Boole](https://en.wikipedia.org/wiki/George_Boole). In this system, everything is either `true` or `false`, or in computer terms, $1$ or $0$. Logic operations are implemented using [logic gates](https://en.wikipedia.org/wiki/Logic_gate). Every complex computation — from addition to running software — reduces to many fast gate operations.

<div style="
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1rem;
  margin: 1em auto;
  max-width: 900px;
  text-align: center;
">

  <figure>
    <img src="../../assets/images/lecture02/not.svg" alt="NOT gate" style="max-width: 100%; height: auto;">
    <figcaption style="margin-top: 0.4em; font-size: 0.85em; opacity: 0.85;">
      NOT gate, By <a href="//commons.wikimedia.org/wiki/User:Inductiveload" title="User:Inductiveload">Inductiveload</a> –
      <span class="int-own-work" lang="en">Own work</span>, Public Domain,
      <a href="https://commons.wikimedia.org/w/index.php?curid=5729018">Link</a>
    </figcaption>
  </figure>

  <figure>
    <img src="../../assets/images/lecture02/and.svg" alt="AND gate" style="max-width: 100%; height: auto;">
    <figcaption style="margin-top: 0.4em; font-size: 0.85em; opacity: 0.85;">
      AND gate, By <a href="//commons.wikimedia.org/wiki/User:Inductiveload" title="User:Inductiveload">Inductiveload</a> –
      <span class="int-own-work" lang="en">Own work</span>, Public Domain,
      <a href="https://commons.wikimedia.org/w/index.php?curid=5729013">Link</a>
    </figcaption>
  </figure>

  <figure>
    <img src="../../assets/images/lecture02/or.svg" alt="OR gate" style="max-width: 100%; height: auto;">
    <figcaption style="margin-top: 0.4em; font-size: 0.85em; opacity: 0.85;">
      OR gate, By <a href="//commons.wikimedia.org/wiki/User:Inductiveload" title="User:Inductiveload">Inductiveload</a> –
      <span class="int-own-work" lang="en">Own work</span>, Public Domain,
      <a href="https://commons.wikimedia.org/w/index.php?curid=5729019">Link</a>
    </figcaption>
  </figure>

  <figure>
    <img src="../../assets/images/lecture02/xor.svg" alt="XOR gate" style="max-width: 100%; height: auto;">
    <figcaption style="margin-top: 0.4em; font-size: 0.85em; opacity: 0.85;">
      XOR gate, By <a href="//commons.wikimedia.org/wiki/User:Inductiveload" title="User:Inductiveload">Inductiveload</a> –
      <span class="int-own-work" lang="en">Own work</span>, Public Domain,
      <a href="https://commons.wikimedia.org/w/index.php?curid=5729022">Link</a>
    </figcaption>
  </figure>

</div>

**Truth tables** are a precise way to describe how a logical operation behaves. They list all possible input values (usually 0 and 1) and show the exact output produced for each case. This makes the behavior of a logic gate or logical rule completely unambiguous and easy to verify. Below are standard truth tables for basic logic gates.

The **NOT gate** inverts its input.

| **A** | **Q** |
| --- | --- |
| 0 | 1 |
| 1 | 0 |

Both **AND gate** and **OR gate** take two inputs. AND outputs 1 only if both inputs are 1. OR outputs 1 if at least one input is 1.

| **A** | **B** | **AND (Q)** | **OR (Q)** |
| --- | --- | --- | --- |
| 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 |

The **XOR (exclusive OR) gate** outputs 1 only when the inputs are different.

| **A** | **B** | **Q** |
| --- | --- | --- |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

!!! success "Exercise"
    How would you implement XOR using only NOT, AND, and OR? You can use an online [digital logic simulator](https://logic.ly/demo/).
    
!!! success "Exercise" 
    Use logic gates to add any two single-bit binary numbers. Which gates would you use? Hint: use the addition table provided in the section dedicated to "two's complement".

## Additional Material

- [Early Computing: Crash Course Computer Science #1](https://www.youtube.com/watch?v=O5nskjZ_GoI)
- [Electronic Computing: Crash Course Computer Science #2](https://www.youtube.com/watch?v=LN0ucKNX0hc)
- [Boolean Logic & Logic Gates: Crash Course Computer Science #3](https://www.youtube.com/watch?v=gI-qXk7XojA)
- [Binary: Plusses & Minuses (Why We Use Two’s Complement) - Computerphile](https://www.youtube.com/watch?v=lKTsv6iVxV4&)
- [Why It Was Almost Impossible to Make the Blue LED](https://www.youtube.com/watch?v=AF8d72mA41M)
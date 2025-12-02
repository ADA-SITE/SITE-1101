---
layout: page
title: Week 05 — Software, Operating Systems, Algorithmic Actions
order: 3
---

{% include lecture-styles.html %}

**Authors:** Rahida Asadli, Nilufar Ismayilova, Rahman Karimov, Ismayil Shahaliyev

**Created / Updated:** Oct 25 2025 **/** Oct 30 2025
{% include reading-time.html %}


<button id="toc-toggle">☰ Sections</button>

<div id="toc-panel">
  <h4>On this page</h4>
  <ul>
    <li><a href="#software">Software</a></li>
    <li><a href="#operating-systems-os">Operating Systems (OS)</a></li>
    <li><a href="#algorithmic-actions">Algorithmic Actions</a></li>
    <li><a href="#additional-material">Additional Material</a></li>
  </ul>
</div>

# Software

[_Software_](https://en.wikipedia.org/wiki/Software) consists of computer programs that instruct the execution of a computer (Stair), also including design documents and specifications ([documentation](https://en.wikipedia.org/wiki/Software_documentation)). Software converts user commands into machine-level instructions ([machine language](https://en.wikipedia.org/wiki/Machine_code): 1s and 0s) and enables computers to perform everything from calculations to complex design simulations.

[System software](https://en.wikipedia.org/wiki/System_software) manages and operates the computer hardware so that other programs can run. It provides a platform for application software.

| **Type** | **Purpose** | **Examples** |
| --- | --- | --- |
| Operating Systems (OS) | Manage hardware and software resources, provide user interface | Windows, macOS, Linux |
| --- | --- | --- |
| Device Drivers | Control and communicate with specific hardware devices | Printer driver, GPU driver |
| --- | --- | --- |
| Utility Programs | Perform maintenance and optimization tasks | File Manager, Disk Cleanup, Antivirus |
| --- | --- | --- |

<div class="frame" markdown="1">

**_Example 1._** When you turn on a laptop, the operating system (e.g., Windows, macOS, Linux) loads first. It checks the keyboard, touchpad, and memory, and loads drivers for your hardware. Only then can you open applications such as Google Chrome, Microsoft Word, or VS Code.

**_Example 2._** When you power on a smartphone, Android or iOS initializes the display, touchscreen, and sensors. After that, you can launch applications like WhatsApp, Spotify, or Instagram.

</div>

[Application software](https://en.wikipedia.org/wiki/Application_software) consists of programs designed for end users to perform particular functions. This includes everything from productivity tools to entertainment and educational programs (e.g., Microsoft Word, Adobe Photoshop, Spotify, Duolingo).

<div class="frame" markdown="1">

**_Example._** A mechanical engineer might design a 3D model in _AutoCAD_ (application software) running on _Windows 11_ (system software) using a _NVIDIA driver_ (device driver) to process the graphics - demonstrating how all software layers interact to perform a task efficiently.

</div>
In addition to the distinction between system and application software, programs can also be categorized by how they are licensed and distributed, as _proprietary_ or **open-source** _(off-the-shelf)_ software.
<div class="frame" markdown="1">

**_Example._** Many private companies choose proprietary software such as _Microsoft Office 365_ because it offers professional customer support, cloud integration, and regular security updates. For instance, an accounting firm may rely on Excel's advanced data analysis tools and seamless synchronization with Microsoft Teams to manage client reports efficiently. In contrast, public institutions and schools often adopt _open-source_ alternatives like _LibreOffice_ or _Google Workspace (free edition)_ to reduce licensing costs while still providing students and staff with essential tools for document creation and collaboration. This demonstrates how the choice between proprietary and open-source software often depends on an organization's budget, technical needs, and support requirements.

**Exercise.** What are the advantage/disadvantages of proprietary and open-source software?

</div>

## Operating Systems (OS)


The [_operating system_](https://en.wikipedia.org/wiki/Operating_system) is the core software that manages all hardware and software resources. It acts as a bridge between user commands and physical hardware components.

<p align="center">
  <img src="{{ '/assets/images/lecture03/OS.png' | relative_url }}" alt="Operating Systems">
</p>


The operating system acts as an intermediary between users, applications, and the computer hardware. It translates high-level user commands into machine-level operations and manages system resources such as memory, processing time, and device communication to ensure efficient coordination across all components.

_Figure 2: Diagram showing the placement of the operating system between hardware and user applications.  
Adapted from "Operating system placement," Wikimedia Commons, [Wikimedia Source](https://commons.wikimedia.org/wiki/File:Operating_system_placement.svg). Licensed under CC BY-SA 3.0._

<div class="frame" markdown="1">

**_Example._** Suppose a user is editing a document in Microsoft Word while listening to music on Spotify and downloading a file from the Internet. The operating system coordinates these simultaneous activities by dividing processor time among the programs, allocating memory to each, and managing input/output requests so that the music continues playing without interruptions and the document remains responsive.
</div>
Operating systems can vary based on ownership, licensing model, and intended device type. The table below summarizes the most common examples across different platforms.

| **Operating System** | **Type** | **Common Use** |
| --- | --- | --- |
| Windows | Proprietary | Desktops, laptops |
| --- | --- | --- |
| macOS | Proprietary | Apple computers |
| --- | --- | --- |
| Linux | Open-source | Servers, embedded systems |
| --- | --- | --- |
| Android | Open-source | Smartphones, tablets |
| --- | --- | --- |
| iOS | Proprietary | Apple mobile devices |
| --- | --- | --- |

The **kernel** is the core part of an operating system. It acts as a bridge between the hardware (like CPU, memory, and devices) and the software (programs you use).When an application wants to do something - like save a file or use the internet - it doesn't talk directly to the hardware. Instead, it asks the kernel to do it safely and efficiently.
<div class="frame" markdown="1">

**_Example._** In Windows, the kernel controls how programs share memory and access files. In Linux, the Linux kernel manages processes like running the terminal, browsers, or servers. In Android, which is built on Linux, the kernel handles the touchscreen, battery, and camera operations.
</div>
# Algorithmic Actions

Algorithmic actions describe the fundamental operations that make up any computer program. These actions determine how a program makes decisions, repeats steps, organizes tasks, and manages data. The five main algorithmic actions are **selection**, **repetition**, **modularization**, **recursion**, and **name binding**.

**Selection** means choosing between different paths of execution based on a condition. It allows the program to "decide" what to do depending on input or data values.
<div class="frame" markdown="1">

**_Example._** If the temperature is above 30 °C, the system turns on the air conditioner; otherwise, it keeps it off.

In programming (pseudo-code):
{% highlight c %}

if (temperature > 30) {

turnOnAC();

} else {

turnOffAC();

}
{% endhighlight %}

</div>
**Repetition** means performing the same set of instructions multiple times until a certain condition is met. This prevents code duplication and makes programs efficient.
<div class="frame" markdown="1">

**_Example._** Printing numbers from 1 to 5 using a loop.

In programming (pseudo-code):
{% highlight c %}

for (int i = 1; i <= 5; i++) {

print(i);

}
{% endhighlight %}

</div>
**Modularization** means dividing a complex program into smaller, manageable, and reusable parts, called modules. This improves readability, debugging, and reusability.
<div class="frame" markdown="1">

**_Example._** A billing program may have:

**calculateTax()**\- computes tax on a purchase

**printBill()**\- prints the final receipt

Each module performs one well-defined task, making the program organized and easier to maintain.
</div>
At a deeper level, modularization is a principle of system organization, not limited to programming. It refers to the act of decomposing any complex system - software, mechanical, social, or educational - into smaller subsystems that can be developed, understood, or replaced independently.

In programming, modularization starts with **functions**, which perform a single, well-defined task. Related functions can be grouped into **classes**, which represent objects or abstract entities. Several classes and functions together form a **module**, typically a single file in a programming language like Python. A **package** is a collection of related modules organized in a directory (folder) structure, and multiple packages can form a **library** or **framework**, representing a higher level of modular organization. At the top level, systems or applications integrate many libraries and frameworks, sometimes developed by entirely different teams or companies.

In **engineering**, a car is designed in modules such as the engine, transmission, and electrical system, each of which can be developed or replaced independently. In **education**, a curriculum may be modularized into separate courses or subjects, each focusing on a distinct domain of knowledge but contributing to an integrated learning goal. In **management**, an organization may be divided into departments - finance, marketing, research, operations - each acting as a module with a specific role but coordinated under one structure. In **architecture**, buildings are designed with modular components such as prefabricated walls or units that can be rearranged or replaced.

At even higher levels, modularization can be systemic or societal. Complex infrastructures - transportation networks, communication systems, and governance structures - are modularized into interacting parts [so that local failures do not collapse the entire system](https://en.wikipedia.org/wiki/Financial_crisis_of_2007%E2%80%932008).

Modularization is about **complexity management**: dividing a whole into parts that are **independent in function** and **cooperative in purpose**.
<div class="frame" markdown="1">

**_Exercise._** _Take a major goal of yours for the next 6 months and divide it into manageable modules._
</div>
**Recursion** occurs when a function calls itself to solve smaller parts of the same problem. Each recursive step reduces the problem size until it reaches a **base case**, the simplest situation where the function stops calling itself. Base case is NOT the starting point, it is the STOPPING CONDITION.

You can imagine of **real-life recursion**: tree has branches, branches have their smaller branches, those branches have their own smaller branches, etc. But this recursion may go infinitely and you usually need to stop at some point. That stopping condition is the base case. Let's say, after four-five branching steps a tree will stop growing any branches. With that logic, there is no base case in the case of two mirrors oppositely directed to each other. There is no base can and you will see infinite reflections. Or: _infinite recursion._

In case of **factorial**, we know that the factorial of n is the factorial of the previous number multiplied by n. That means:

_factorial(5) = factorial(4) \* 5_

_factorial(4) = factorial(3) \* 4_

_factorial(3) = factorial(2) \* 3_

_factorial(2) = factorial(1) \* 2_

Or, as a general case:

_factorial(n) = factorial(n-1) \* n_

We can write the following recursive function:
<div class="frame" markdown="1">
{% highlight c %}

factorial(n) {

return n * factorial(n - 1);

}
{% endhighlight %}

</div>

But this pseudo-code has an issue. It is akin to two mirrors looking at each other - it will never stop. It will return the following functions:

_factorial(1) = factorial(0) \* 1_

_factorial(0) = factorial(-1) \* 0_

_factorial(-1) = factorial(-2) \* -1_

_ad infinitum_

Not only _factorial(-1)_ doesn't make sense, but also you will be in an infinite recursion. To fix it, you need to add a halting (stopping) condition: Base case.

<div class="frame">
{% highlight c %}
factorial(n) {
  if (n == 1 || n == 0) {
    return 1; // base case
  } else {
    return n * factorial(n - 1); // recursive call
  }
}
{% endhighlight %}
</div>

So, your code will work in the following way, given that n is a non-negative number (in this case n=4): _factorial(4) = factorial(3) \* 4 = factorial(2) \* 3 \* 4 = factorial(1) \* 2 \* 3 \* 4 = 1 \* 2 \* 3 \* 4 = 24._

<div class="frame" markdown="1">

**_Exercise._** Write a pseudo-code for recursive algorithm to find the sum of natural numbers.
</div>
**Name binding** refers to the process of connecting _identifiers_ (names) to specific objects, values, or **memory locations** in a program. It defines _where_ and _when_ a variable's name is linked to the data it represents. This action allows the program to store, access, and update information consistently.
<div class="frame" markdown="1">

**_Example._** When you type:

**70**

Somewhere in the memory an **object** is created. For example in memory cell represented with hexadecimal number 0x21A95BC, bytes will allocated to represent 70 in binary. Then, if you want to reuse that value in the future, you need to **assign** (not equalize) that value to an identifier.

**speed = 70**

the name speed becomes bound to the value 70 stored in memory. If later the value changes (speed = 50), the same name now refers to a different value but the same memory binding.
</div>
There are two main types of binding: **Static (compile-time)**: the link between name and value is fixed before execution (e.g., variable types in C or Java (e.g. _int speed = 70_). **Dynamic (run-time)**: the link occurs while the program is running (e.g., variable reassignment in Python).

# Additional Material

- [The real reason Boeing's new plane crashed twice](https://www.youtube.com/watch?v=H2tuKiiznsY)
- [Ariane 5 rocket launch explosion](https://www.youtube.com/watch?v=PK_yguLapgA)
- [eIntro to Algorithms: Crash Course Computer Science #13](https://www.youtube.com/watch?v=rL8X2mlNHPM)
- [What's an algorithm? - David J. Malan](https://www.youtube.com/watch?v=6hfOvs8pY1k)
- [Operating Systems: Crash Course Computer Science #18](https://www.youtube.com/watch?v=26QPDBe-NB8)
- [Programming myths that waste your time](https://www.youtube.com/watch?v=niWpfRyvs2U)
<hr>

{% include lecture-footer.html %}


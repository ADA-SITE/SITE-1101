---
layout: page
title: Week 04 — Hardware, CPU, Input/Processing/Output/Storage Devices
order: 2
---

{% include lecture-styles.html %}

**Authors:** Rahida Asadli, Nilufar Ismayilova, Rahman Karimov

**Created / Updated:** Oct 25 2025 **/** Nov 10 2025


<button id="toc-toggle">☰ Sections</button>

<div id="toc-panel">
  <h4>On this page</h4>
  <ul>
    <li><a href="#hardware">Hardware</a></li>
    <li><a href="#cpu">CPU</a></li>
    <li><a href="#memory-devices">Memory Devices</a></li>
    <li><a href="#volatile-and-non-volatile-memory">Volatile vs Non-Volatile</a></li>
    <li><a href="#classification-of-physical-storage-media">Storage Media Types</a></li>
    <li><a href="#storage-hierarchy">Storage Hierarchy</a></li>
    <li><a href="#additional-material">Additional Material</a></li>
  </ul>
</div>

{% include reading-time.html %}

### Hardware

[_Hardware_](https://en.wikipedia.org/wiki/Computer_hardware) refers to the **physical components** of a computer system, the parts you can see and touch. It includes all electronic and mechanical elements that work together to input, process, store, and output data.

| **Unit** | **Function** |
| --- | --- |
| Input Devices | Allow users to enter data or commands (keyboard, mouse, scanner, microphone). |
| --- | --- |
| Processing Unit (CPU) | Executes instructions, performs calculations, and controls system operations. |
| --- | --- |
| Memory (Primary Storage) | Temporarily stores data and instructions for quick access by the CPU. |
| --- | --- |
| Storage Devices (Secondary Storage) | Permanently store data and software (SSD, HDD, optical discs). |
| --- | --- |
| Output Devices | Present processed data to users (monitor, printer, speakers). |
| --- | --- |





<p align="center">
  <img src="{{ '/assets/images/lecture04/1.png' | relative_url }}" alt="">
</p>
_Figure 1._ _Image of computer motherboard model DellT3600. Adapted from Motherboard, Wikipedia, Wikimedia Commons,_ [_https://en.wikipedia.org/wiki/Motherboard_](https://en.wikipedia.org/wiki/Motherboard)_. Licensed under_ [_CC BY 2.5_](https://creativecommons.org/licenses/by/2.5)

The **motherboard** is the **main circuit board** and backbone of the computer, responsible for connecting and coordinating all hardware components. It provides the electrical pathways (called _buses_) and controllers that allow the CPU, memory (RAM), storage devices (SSD or HDD), and input/output components to communicate quickly and in the correct sequence. The motherboard ensures that data flows smoothly between these parts, much like a central highway system linking different parts of a city. The **CPU socket** is the slot where the processor is installed; through tiny metal contacts, it connects directly to the motherboard so the CPU can fetch, decode, and execute instructions from memory. Beside it are the **memory slots**, where **RAM modules** are inserted. RAM temporarily holds the data and instructions the CPU is currently working with, allowing for fast access and efficient processing.

<p align="center">
  <img src="{{ '/assets/images/lecture04/motherboard.png' | relative_url }}" alt="">
</p>


  _Figure 1._ A high-end consumer CPU made by [Intel](https://en.wikipedia.org/wiki/Intel): an [Intel Core i9-14900KF](https://en.wikipedia.org/wiki/Intel_Core_i9-14900KF)_. Adapted from Central Processing Unit, Wikipedia, Wikimedia Commons,_[_https://en.wikipedia.org/wiki/Central_processing_unit_](https://en.wikipedia.org/wiki/Central_processing_unit)_. Licensed under_ [_CC BY 2.5_](https://creativecommons.org/licenses/by/2.5)

<div class="frame" markdown="1">

**_Example._** Imagine you are editing a photo on your laptop. When you move the mouse to open the image, it acts as an input device, sending a signal to the CPU through the motherboard. The CPU, which is the brain of the computer, begins its machine cycle - it fetches the instruction from memory, decodes what action to perform, executes the command (such as cropping or adjusting color), and then stores the result. While you make changes, the RAM keeps the image and editing information temporarily, so the CPU can access them quickly. The CPU's internal cache memory helps it repeat similar operations faster, and the control unit makes sure each step happens in the correct order. As you view your edits, the updated image is sent to the monitor, which works as an output device. Finally, when you click "Save," the finished picture is written from RAM to your SSD or hard drive, where it remains permanently stored. This simple action shows how the CPU, memory, storage, and input/output devices, all connected through the motherboard, work together to carry out a complete computing task.
</div>
### CPU

[_Central Processing Unit_](https://en.wikipedia.org/wiki/Central_processing_unit) **-** The **Central Processing Unit (CPU)** is often called the brain of the computer because it does all the thinking work. It follows instructions from programs and performs the steps needed to complete any task - from typing a word to playing music. The CPU also controls and coordinates the work of all other parts of the computer, making sure everything happens in the right order.Every action the CPU performs follows four main steps, known as the **machine cycle**. This cycle repeats millions of times every second.

- **Fetch** - The CPU gets an instruction from **memory (RAM)**.  
    For example, if you click on a calculator app, the CPU fetches the instruction "open calculator" from memory.
- **Decode** - The CPU **figures out what the instruction means**.  
    It decides what action must be taken - for example, "add two numbers."
- **Execute** - The CPU **carries out the action**.  
    The **Arithmetic Logic Unit (ALU)** does the actual work, such as adding, subtracting, or comparing two numbers.
- **Store** - The CPU **saves the result**.  
    The result of the operation is placed back into **memory** or sent to an **output device** (such as the screen).

This process - **fetch, decode, execute, store** - happens automatically and continuously. Even a simple action like pressing a key on the keyboard can make the CPU repeat this cycle many times in just one second.

| **Component** | **Function** |
|--------------|--------------|
| **Arithmetic Logic Unit (ALU)** | The Arithmetic Logic Unit (ALU) is the mathematical brain of the CPU. It performs all arithmetic operations (addition, subtraction, multiplication, division) and logical operations (comparisons: equal to, greater than, AND, OR, NOT). When the CPU executes an instruction like "Add 2 + 3," the Control Unit sends this task to the ALU. The ALU performs the calculation and sends the result back to the registers or memory.<br><br>**Example:** When you use a spreadsheet formula (=A1 + B1), the ALU does the actual calculation. |
| **Control Unit (CU)** | This part manages and directs the activities inside the CPU. It tells the computer when to fetch data, when to execute an instruction, and where to send the results. It works like a traffic controller, ensuring every step in the machine cycle happens in the correct order. |
| **Registers** | Registers are tiny, high-speed memory locations inside the CPU. They store data and instructions temporarily — for example, the current instruction being executed or the result of an ALU calculation. Because they are inside the CPU, they are much faster than RAM.<br><br>Each register has a specific purpose:<br>• **Instruction Register (IR):** holds the current instruction<br>• **Program Counter (PC):** stores the address of the next instruction<br>• **Accumulator (ACC):** stores intermediate results<br><br>**Example:** For (4 × 3) + 2, the ALU may store 12 in the accumulator before adding 2. |

<div class="frame" markdown="1">

**_Example._** When a computer needs to add two numbers, several internal components work together in a carefully coordinated sequence.

**The Control Unit (CU)** is the part of the CPU that manages this process. It first fetches the instruction from main memory-this is simply the binary code telling the CPU what to do. Then it **decodes** the instruction to understand the operation (in this case, addition) and identifies which data to use. After decoding, the CU sends control signals to the rest of the CPU. These signals tell each component when to act-for example, instructing the **Arithmetic Logic Unit (ALU)** to perform the addition, and telling the registers to load or output data at the correct moment.

The ALU performs the actual arithmetic (addition, subtraction, etc.) or logical (comparison, AND, OR, etc.) operations. It receives the two numbers from the registers, adds them in binary form, and produces the result.

Meanwhile, the **registers** act as small, extremely fast storage locations inside the CPU. Before the ALU starts, the numbers to be added are placed in registers. After the ALU finishes, the result is stored in another register, ready to be sent back to main memory or used for the next operation.

Throughout the process, the CU ensures proper timing and order, making sure that data moves only when it should and that all components work in sync. This precise coordination-fetching, decoding, executing, and storing-is what allows even the simplest task, such as adding two numbers, to happen billions of times per second without error.

**_Analogy._** Think of the CPU as a master chef in a busy restaurant kitchen. The recipe represents the instructions stored in memory. The ingredients are the data needed for the task. The ALU (Arithmetic Logic Unit) is where the _actual cooking_ happens, mixing, cutting, calculating. The Control Unit (CU) acts like the _head waiter or kitchen manager_, making sure each step of the recipe happens in the correct order and that nothing is missed. The Registers and Cache are like the _chef's counter_, where frequently used ingredients are kept within arm's reach for speed. Just like a chef repeatedly reads a recipe, prepares ingredients, and produces dishes for customers, the CPU fetches, decodes, and executes instructions to produce useful results.
</div>
<table>
  <thead>
    <tr>
      <th><p><strong>Property</strong></p></th>
      <th><p><strong>Description</strong></p></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><p>Clock</p></td>
      <td>
        <p>The <strong>clock</strong> is the timing system of the CPU. It sends out a steady stream of <strong>electrical pulses</strong> that set the pace for all operations. The faster the clock, the more instructions the CPU can handle each second. For example, a CPU with a 3.0 GHz clock can perform about 3 billion steps per second. The clock ensures that all parts of the CPU work together in perfect rhythm.</p>
      </td>
    </tr>

    <tr>
      <td><p>Clock Speed</p></td>
      <td>
        <p>The <strong>clock speed</strong> shows how fast the CPU can carry out its steps in the <strong>machine cycle</strong> - fetching, decoding, executing, and storing instructions. The CPU's internal <strong>clock</strong> sends out electronic pulses to coordinate every action. Each pulse is called a <strong>cycle</strong>, and the number of cycles per second is measured in <strong>Hertz (Hz)</strong>.</p>
        <p><strong>Example:</strong></p>
        <p>A CPU running at <strong>3 GHz</strong> performs <strong>3 billion cycles per second</strong>. This means it can complete three billion small steps - like adding two numbers, comparing values, or moving data - in just one second.</p>
      </td>
    </tr>

    <tr>
      <td><p>Word Size</p></td>
      <td>
        <p><strong>Word size</strong> means the number of <strong>bits</strong> (binary digits, 0s and 1s) the CPU can process in one operation. The most common sizes are <strong>32-bit</strong> and <strong>64-bit</strong>. A 64-bit CPU can handle larger chunks of data at once and can also use much more memory than a 32-bit CPU.</p>
      </td>
    </tr>

    <tr>
      <td><p>Core Count</p></td>
      <td>
        <p>Modern CPUs contain more than one <strong>core</strong>, which means multiple <strong>processing units</strong> inside a single chip. Each core can run its own instructions independently, allowing the computer to work on several tasks at once - a process called <strong>parallel processing</strong>.</p>
        <p><strong>Example:</strong></p>
        <p>A <strong>dual-core</strong> CPU can work on two tasks at the same time (like playing music while browsing the internet). A <strong>quad-core</strong> CPU can handle four tasks, and an <strong>octa-core</strong> CPU can handle eight - ideal for heavy work such as gaming or video editing.</p>
      </td>
    </tr>

    <tr>
      <td><p>Cache Memory</p></td>
      <td>
        <p><strong>Cache memory</strong> is a very small, <strong>ultra-fast memory</strong> built directly inside the CPU. It stores data and instructions that are <strong>used often</strong>, so the CPU doesn't have to fetch them repeatedly from the slower main memory (RAM). SRAM is used as a cache memory.</p>
        <p>There are usually three levels of cache:</p>
        <ul>
          <li><strong>L1 cache</strong> - the smallest and fastest, located right next to each CPU core.</li>
          <li><strong>L2 cache</strong> - larger but slightly slower, shared by a few cores.</li>
          <li><strong>L3 cache</strong> - the largest, shared by all cores in the processor.</li>
        </ul>
        <p><strong>Example:<br></strong>When you edit a photo or play a game, certain instructions are used again and again - the cache keeps them ready for instant access.</p>
      </td>
    </tr>

    <tr>
      <td><p>Instruction Set Architecture (ISA)</p></td>
      <td>
        <p>The <strong>Instruction Set Architecture (ISA)</strong> is the <strong>built-in language</strong> of the CPU - it defines the exact set of commands the CPU can understand and execute.Each CPU family has its own instruction set that determines how it performs basic operations, communicates with memory, and runs programs. Common examples include:</p>
        <ul>
          <li><strong>x86 / x86-64</strong> - used in most desktop and laptop computers (Intel and AMD).</li>
          <li><strong>ARM</strong> - used in smartphones, tablets, and many modern laptops because it's designed for efficiency and low power use.</li>
        </ul>
        <p><strong>Example: </strong>Just as people speak different languages, an Intel CPU "speaks" x86 instructions, while a smartphone CPU "speaks" ARM. Programs must be written or compiled in the correct instruction set so the CPU understands them.</p>
      </td>
    </tr>
  </tbody>
</table>

### Memory Devices

Every computer must **store data and instructions** so the CPU can use them. The place where this information is kept is called [memory](https://en.wikipedia.org/wiki/Computer_data_storage) or **storage**. Different kinds of memory serve different purposes - some are very fast but temporary, while others are slower but permanent.

### Volatile and Non-Volatile Memory

- **Volatile memory** means that its contents are lost when power is turned off.  
    Example: RAM (Random Access Memory).  
    Used for temporary data that the CPU is currently working on.
- **Non-volatile memory** keeps its contents even when the power is off.  
    Example: ROM, hard drives, SSDs, and optical discs.  
    Used for storing data and programs permanently.

## Classification of Physical Storage Media

According to computer architecture, physical storage is often divided into three levels:

**Primary Storage** - the fastest memory, located close to or inside the CPU (registers, cache, and RAM). It is volatile and used for immediate processing.

- **Read-Only Memory (ROM)** is a _non-volatile memory_ that permanently stores the essential instructions a computer needs to start up. Unlike RAM, it _retains data even when power is off_. When the computer is turned on, the _CPU reads the firmware_ stored in ROM-known as the _BIOS or UEFI_-which checks the hardware (like memory, keyboard, and drives) and then loads the _operating system_ into main memory. ROM is usually _preprogrammed by the manufacturer_ and can't be easily changed, though modern types like _EEPROM and Flash ROM_ can be updated electronically. In short, ROM is the computer's _built-in instruction manual_, guiding it through the startup process every time it powers on. ROM is part of **primary memory**, even though it is **non-volatile**. Primary memory refers to how closely it works with the CPU, not whether it loses data when power is off. ROM stores essential startup programs (firmware), while RAM and cache handle temporary processing data.**RAM (Random Access Memory)** is the computer's main working memory. It temporarily stores data and instructions that the CPU is currently using, allowing quick access for ongoing tasks. RAM is volatile, which means all data is lost when power is turned off. There are two main types of RAM: DRAM (Dynamic RAM) and SRAM (Static RAM).
- **Dynamic Random Access Memory (DRAM)** stores each bit of data in a _tiny capacitor_ that holds an electrical charge - charged for 1, empty for 0. Because these capacitors _leak energy_, DRAM must be _constantly refreshed_ to retain data. Its simple design (just _one transistor and one capacitor per bit_) allows it to hold large amounts of data at a low cost, but this also makes it _slower_ than other memory types. DRAM serves as the _main system memory_ in computers, holding all the programs and files you're currently using - like open browser tabs or a running video - so the CPU can access them quickly.
- **Static Random Access Memory (SRAM)**, on the other hand, uses _flip-flop circuits_ made of transistors that keep data stable as long as power is on - no refreshing needed. This makes SRAM _much faster_ and more reliable, but also _larger and more expensive_. Because of its speed, it's used inside the _CPU as cache memory (L1, L2, L3)_ to store data and instructions the processor uses most often. For example, during gaming or video rendering, SRAM keeps repeating instructions close to the CPU, so the system responds instantly without waiting for slower DRAM.
<div class="frame" markdown="1">

**_Example._** Imagine you're working on a laptop with several browser tabs open - one for email, one for an online document, and one for a video. All of these open tabs, along with the data they're displaying, are stored in DRAM (Dynamic RAM). DRAM acts as your computer's active workspace - it holds the information and programs you're currently using so the CPU can quickly access them. Every time you switch from your email to the document tab, the CPU retrieves that page's data directly from DRAM instead of reloading it from the slower hard drive or SSD. However, since DRAM is volatile, if the computer loses power, all those open tabs and unsaved work disappear because the data is cleared from memory.

At the same time, the CPU is using SRAM (Static RAM) inside it - specifically the cache memory - to store the most frequently needed instructions and pieces of data it uses while running those browser tabs. For example, when you play a short video clip or repeatedly load parts of a webpage, the CPU keeps those decoding instructions or small data chunks in its SRAM cache. This allows the CPU to reuse them instantly instead of fetching them again from the slower DRAM. In other words, DRAM is like your whole work desk, where all your open documents and tabs are spread out, while SRAM is like the few key notes you keep right under your hand - the things you reach for over and over without even looking away.
</div>
**Secondary Storage** - slower but non-volatile, used for long-term storage of data and programs (e.g., SSDs, HDDs, flash drives).

- A **Hard Disk Drive (HDD)** stores data using _magnetic platters_ that spin at very high speeds, usually between 5,400 and 7,200 revolutions per minute (RPM). Data is written and read by a tiny magnetic _head_ that moves across the surface of the _spinning disks_ without touching them. Because of its mechanical structure, an HDD can hold a large amount of data - typically between 1 and 20 terabytes - but it is slower than modern Solid State Drives (SSDs). HDDs are also more affordable per gigabyte, which makes them a cost-effective choice for storing large files such as videos, backups, or archives. However, since the disk and read/write head involve physical movement, they can wear out over time and are more vulnerable to shocks or drops. The device allows direct or _random access,_ meaning the magnetic head can move to any specific location on the disk to read or write data, rather than having to go through information sequentially.
- A **Solid State Drive (SSD)** stores data using _flash memory chips_ and has _no moving parts,_ which makes it much faster and more reliable than traditional hard drives. Data is stored electronically in millions of tiny _transistors,_ similar to the technology used in USB flash drives, but with far faster interfaces and controllers. SSDs provide very fast boot times, quick application loading, and instant file access, which is why they are now the standard in most laptops and modern computers. Since there are no spinning disks or moving heads, SSDs are also _silent, lighter, and more resistant to physical shock_, making them ideal for portable devices. However, their cost per gigabyte is higher than that of HDDs. SSDs use _direct (random) access_, meaning the controller can jump instantly to any data block on the drive without scanning other areas, allowing extremely quick read and write speeds.

**Tertiary Storage** - the slowest, also non-volatile, mainly used for backups and archives. Tertiary storage is used for _long-term backups or archives_ and is not accessed frequently. Examples include _optical discs (CD, DVD, Blu-ray_**)** and _magnetic tapes_ used in large data centers. These devices are slower because they use _sequential access_, meaning data is read or written in order from start to end. Although slower, they offer _very large capacities_ at very _low cost_ per unit of data.

## Storage hierarchy
<p align="left">
  <img src="{{ '/assets/images/lecture04/image.png' | relative_url }}" alt="">
</p>
The storage hierarchy shows how different types of memory and storage are organized based on **speed**, **cost**, and **capacity**. At the **top of the pyramid**, we have **cache memory** - it is the **fastest** and most **expensive** type of storage but also the **smallest** in size. Cache sits inside the CPU and provides data almost instantly. Below it is **main memory (RAM)**, which is slightly slower and cheaper, used to store data that the CPU is currently working on. Moving further down, **flash memory** (such as solid-state drives and USB drives) is **non-volatile**, meaning it keeps data even when power is off. It is slower than RAM but much faster than magnetic or optical storage. Next comes the **magnetic disk** (hard drives), which provides **large capacity** at a **lower cost**, but because it has mechanical moving parts, its access speed is slower. Below that are **optical disks** (like CDs, DVDs, and Blu-ray), mainly used for media storage or backups - they are inexpensive but have limited capacity and slower access. At the **bottom of the pyramid** is **magnetic tape**, which stores massive amounts of data very cheaply but is extremely slow, as it reads data **sequentially** instead of directly. In this hierarchy, as you **move upward**, **speed and cost increase** while **storage capacity decreases**. As you **move downward**, **capacity increases** and **cost per bit decreases**, but **access time becomes slower**. This layered design allows computers to balance **performance and storage needs** efficiently - keeping frequently used data in faster, smaller memory and less-used data in slower, larger storage.![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVR4XmP4//8/AwAI/AL+GwXmLwAAAABJRU5ErkJggg==)
<div class="frame" markdown="1">

**_Example._** Your laptop's SSD stores the OS and programs for quick boot, while an external HDD is used for backups.

**_Example._** Imagine you're working on a school project: While you type, your document is stored in RAM, which is fast but temporary, like a whiteboard you can easily erase. When you click "Save," the file moves to your SSD or hard drive, which is permanent storage, like placing your finished report into a filing cabinet for safekeeping. If you back up the file to a USB drive or cloud storage, it's like keeping a copy at home and one in your email, so you can still retrieve it if one copy is lost.
</div>
Storage devices use two main data-retrieval methods.

| **Method** | **Description** | **Example** |
| --- | --- | --- |
| Sequential Access | Data read in fixed order; slower but simple. | Optical discs, magnetic tapes |
| --- | --- | --- |
| Direct (Random) Access | Jumps instantly to any data location. | HDDs, SSDs, USB drives |
| --- | --- | --- |

<div class="frame" markdown="1">

**_Example._** When you watch a movie online, the data is read in sequence, each video frame is loaded one after another. This is called sequential access, because the computer must go through the data in order, just like reading a book from the first page to the last.

However, when you search for a friend's name in a contacts app or look up a specific file on your computer, the system jumps directly to the needed data without reading everything else. This is direct (random) access, similar to flipping straight to a page in a dictionary instead of reading it all.
</div>
# Additional Material

- [Describe the components of the central processing unit (CPU) and how they work together](https://adauniversity-my.sharepoint.com/personal/ayusubov_ada_edu_az/_layouts/15/stream.aspx?id=%2Fpersonal%2Fayusubov%5Fada%5Fedu%5Faz%2FDocuments%2FSITE%2DSITE%2D1101%2Fweek%2D02%2Dcpu%2Dcomponents%2Emp4&ga=1&referrer=StreamWebApp%2EWeb&referrerScenario=AddressBarCopied%2Eview%2E38ec1b6f%2D2acf%2D48b9%2Db379%2Df3ca248f2fd9)
- [Describe different processing characteristics and physical characteristics of the CPU](https://adauniversity-my.sharepoint.com/personal/ayusubov_ada_edu_az/_layouts/15/stream.aspx?id=%2Fpersonal%2Fayusubov_ada_edu_az%2FDocuments%2FSITE-SITE-1101%2Fweek-02-cpu-characteristics.mp4&ga=1&startedResponseCatch=true&referrer=StreamWebApp.Web&referrerScenario=AddressBarCopied.view.bcb66950-9bb8-448c-a0e3-24a79b50c2b5)
- [Describe and differentiate various types of memory devices e.g. ROM, RAM, cache memory](https://adauniversity-my.sharepoint.com/personal/ayusubov_ada_edu_az/_layouts/15/stream.aspx?id=%2Fpersonal%2Fayusubov%5Fada%5Fedu%5Faz%2FDocuments%2FSITE%2DSITE%2D1101%2Fweek%2D03%2Dmemory%2Ddevices%2Emp4&ga=1&referrer=StreamWebApp%2EWeb&referrerScenario=AddressBarCopied%2Eview%2Ee210092d%2D3030%2D449f%2D9511%2D04b78aebecbc)
- [Describe and differentiate between DRAM and SRAM technologies](https://adauniversity-my.sharepoint.com/personal/ayusubov_ada_edu_az/_layouts/15/stream.aspx?id=%2Fpersonal%2Fayusubov_ada_edu_az%2FDocuments%2FSITE-SITE-1101%2Fweek-03-storage-tech.mp4&ga=1&startedResponseCatch=true&referrer=StreamWebApp.Web&referrerScenario=AddressBarCopied.view.75af8065-9945-4767-ae46-0cce830b893b)
- [Describe and differentiate between various technologies used in secondary storage devices](https://adauniversity-my.sharepoint.com/personal/ayusubov_ada_edu_az/_layouts/15/stream.aspx?id=%2Fpersonal%2Fayusubov%5Fada%5Fedu%5Faz%2FDocuments%2FSITE%2DSITE%2D1101%2Fweek%2D03%2Dstorage%2Dtech%2Emp4&ga=1&referrer=StreamWebApp%2EWeb&referrerScenario=AddressBarCopied%2Eview%2E3c5a80d7%2Df9f6%2D4b8d%2D8e34%2D804a88793fd2)
- [How do Transistors Build into a CPU? 🖥️🤔 How do Transistors Work? 🖥️🤔](https://www.youtube.com/watch?v=_Pqfjer8-O4)
- [How do Hard Disk Drives Work? 💻💿🛠](https://www.youtube.com/watch?v=wtdnatmVdIg)
- [How does Computer Memory Work? 💻🛠](https://www.youtube.com/watch?v=7J7X7aZvMXQ)
- [How Computers Calculate - the ALU: Crash Course Computer Science #5](https://www.youtube.com/watch?v=1I5ZMmrOfnA)
- [How a CPU Works in 100 Seconds // Apple Silicon M1 vs Intel i9](https://www.youtube.com/watch?v=vqs_0W-MSB0)

<hr>

{% include lecture-footer.html %}

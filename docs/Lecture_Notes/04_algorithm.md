---
layout: page
title: Algorithm & Algorithmic Actions
order: 3
week: 5
authors: "Nilufar Ismayilova, Ismayil Shahaliyev"
created: "Oct 25 2025"
updated: "Dec 22 2025"
---

{% include lecture-styles.html %}

{% include lecture-header-info.html %}

<!-- 
<button id="toc-toggle">☰ Sections</button>

<div id="toc-panel">
  <h4>On this page</h4>
  <ul>
    <li><a href="#algorithmic-actions">Algorithmic Actions</a></li>
     <li><a href="#dijkstra-shortest-path">Dijkstra's Shortest Path Algorithm</a></li>
    <li><a href="#additional-material">Additional Material</a></li>
  </ul>
</div> -->

An [algorithm](https://en.wikipedia.org/wiki/Algorithm) is a step-by-step procedure or set of rules to solve a specific problem or perform a task. It is like a recipe in cooking: you follow a clear sequence of actions to achieve a specific result. In computer science, algorithms receive some _input_, _process_ it in a logical way, and produce an _output_. What makes a **good algorithm** is that it has a clear starting point, a clear ending point, and every step is unambiguous - there is no confusion about how it should be executed.

<div class="frame" markdown="1">

**_Example._** Imagine you want to find the largest of three numbers: A, B, and C. A simple algorithm would say: first compare A and B. If A is greater than or equal to B, then compare A with C. If A is still the greatest, then A is the largest number. Otherwise, C is the largest. But if in the very first comparison B was already greater than A, then compare B with C, and whichever is larger is the answer. This exact set of steps can be written in code or performed by a person.

**_Exercise._** Bring an example of an algorithm from your daily life.

</div>

The word _algorithm_ traces back to the name of the mathematician [Al-Khwarizmi](https://en.wikipedia.org/wiki/Al-Khwarizmi), whose systematic approach to calculation and problem-solving became foundational to modern mathematics and computing. Similarly, the word algebra comes from his mathematical treatise _Al-Jabr_, translated as "completion" or "rejoining".

[Turing Award](https://en.wikipedia.org/wiki/Turing_Award) winner computer scientist [Donald Knuth](https://en.wikipedia.org/wiki/Donald_Knuth) is best known for the book _The Art of Computer Programming_. His work helped establish _algorithmic analysis_ as a discipline.

[Computational complexity](https://en.wikipedia.org/wiki/Computational_complexity) of an algorithm describes how the resources an algorithm needs (e.g. time, memory, etc.) grow as the input size increases. **Time complexity** tracks how many computational steps are required. **Space complexity** tracks how much memory is used. Within these, we distinguish worst-case, average-case, and best-case behavior depending on how the input might vary. [Asymptotic (Big O) notation](https://en.wikipedia.org/wiki/Big_O_notation) provides a language for comparing growth rates when inputs become large. Big O gives an upper bound: it states that the algorithm grows no faster than some function up to constant factors. Big O abstracts away hardware, implementation details, and constants, focusing only on how the algorithm scales with input size.

<p align="center">
  <img src="{{ '/assets/images/lecture04/image.png' | relative_url }}" alt="">
</p>

Knuth also wrote a [special foreword](https://cs.stanford.edu/~knuth/azerbaijan.pdf) publication for participants of the International Olympiad in Informatics ([IOI 2019](https://stats.ioinformatics.org/olympiads/2019)) held in Azerbaijan. _A Book of Tasty Algorithms_ is a playful recipe book based on dishes from Azerbaijani cuisine, representing algorithmic ideas through the familiar structure of cooking, drawing a parallel between writing algorithms and following recipes.

## Algorithmic Actions

Algorithmic actions describe the fundamental operations that make up any computer program. These actions determine how a program makes decisions, repeats steps, organizes tasks, and manages data. The five main algorithmic actions are **selection**, **repetition**, **modularization**, **recursion**, and **name binding**.

**Selection** means choosing between different paths of execution based on a condition. It allows the program to "decide" what to do depending on input or data values.

<div class="frame" markdown="1">

**_Example._** If the temperature is above 30 °C, the system turns on the air conditioner; otherwise, it keeps it off. In programming (pseudo-code):

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

**_Example._** Printing numbers from 1 to 5 using a loop. In programming (pseudo-code):

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

**_Exercise._** _Take a major goal of yours for the next six months and divide it into manageable modules._

</div>

**Recursion** occurs when a function calls itself to solve smaller parts of the same problem. Each recursive step reduces the problem size until it reaches a **base case**, the simplest situation where the function stops calling itself. Base case is NOT the starting point, it is the STOPPING CONDITION.

You can imagine of **real-life recursion**: tree has branches, branches have their smaller branches, those branches have their own smaller branches, etc. But this recursion may go infinitely and you usually need to stop at some point. That stopping condition is the base case. Let's say, after four-five branching steps a tree will stop growing any branches. With that logic, there is no base case in the case of two mirrors oppositely directed to each other. There is no base can and you will see infinite reflections. Or: _infinite recursion._

In case of **factorial**, we know that the factorial of n is the factorial of the previous number multiplied by n. That means:
{% highlight c %}

factorial(5) = factorial(4) * 5

factorial(4) = factorial(3) * 4

factorial(3) = factorial(2) * 3

factorial(2) = factorial(1) * 2

{% endhighlight %}

Or, as a general case:

factorial(n) = factorial(n-1) \* n_

We can write the following recursive function:
<div class="frame" markdown="1">

{% highlight c %}

factorial(n) {

return n * factorial(n - 1);}

{% endhighlight %}
</div>

But this pseudo-code has an issue. It is akin to two mirrors looking at each other - it will never stop. It will return the following functions:

factorial(1) = factorial(0) \* 1_

factorial(0) = factorial(-1) \* 0_

factorial(-1) = factorial(-2) \* -1_

_ad infinitum_

Not only factorial(-1)_ doesn't make sense, but also you will be in an infinite recursion. To fix it, you need to add a halting (stopping) condition: Base case.
<div class="frame" markdown="1">

{% highlight c %}

factorial(n) {

if (n == 1 or n == 0) return 1; // base case

else return n * factorial(n - 1); // recursive call

}
{% endhighlight %}

</div>

So, your code will work in the following way, given that n is a non-negative number (in this case n=4): factorial(4) = factorial(3) \* 4 = factorial(2) \* 3 \* 4 = factorial(1) \* 2 \* 3 \* 4 = 1 \* 2 \* 3 \* 4 = 24._

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

## Dijkstra's Shortest Path Algorithm {#dijkstra-shortest-path}

In many information systems, a common task is to search for an item. In some systems, the problem involves navigating networks, such as transportation systems or computer networks, where components are connected by links with different costs, delays, or capacities. In these cases, the goal is not merely to locate an item, but to determine an _optimal path_ through the network.

[Edsger W. Dijkstra](https://en.wikipedia.org/wiki/Edsger_W._Dijkstra) was a Dutch computer scientist and one of the founders of modern computer science. [Dijkstra's algorithm](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm) is a classic solution that computes the shortest path from a starting node to all other nodes in a [weighted graph](https://en.wikipedia.org/wiki/Graph_%28discrete_mathematics%29) where all edge weights are non-negative. The algorithm maintains a set of nodes whose minimum distance from the start is already known. At each step, it selects the node with the smallest temporary distance, finalizes its distance, and then updates (relaxes) its neighbors by checking whether passing through this node yields a shorter path.

![](data:image/gif;base64,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)

_Dijkstra's algorithm to find the shortest path between a and b. It picks the unvisited vertex with the lowest distance, calculates the distance through it to each unvisited neighbor, and updates the neighbor's distance if smaller. Mark visited (set to red) when done with neighbors._

_By Ibmua - Work by uploader., Public Domain,_ [_https://commons.wikimedia.org/w/index.php?curid=6282617_](https://commons.wikimedia.org/w/index.php?curid=6282617)

A [priority queue](https://en.wikipedia.org/wiki/Priority_queue) is often used to efficiently select the next node with the smallest distance, which allows the algorithm to scale well for large graphs. The algorithm finishes when all nodes have been processed or when the destination node is finalized. The output is both the shortest distance and the actual path taken.

# Additional Material

- [Intro to Algorithms: Crash Course Computer Science #13](https://www.youtube.com/watch?v=rL8X2mlNHPM)
- [What's an algorithm? - David J. Malan](https://www.youtube.com/watch?v=6hfOvs8pY1k)
- [What on Earth is Recursion? - Computerphile](https://www.youtube.com/embed/Mv9NEXX1VHc)
- [Binary, Hanoi and Sierpinski, part 1](https://www.youtube.com/embed/2SUvWfNJSsM)
- [Dijkstra's Algorithm - Computerphile](https://www.youtube.com/watch?v=GazC3A4OQTE)

{% include lecture-footer.html %}


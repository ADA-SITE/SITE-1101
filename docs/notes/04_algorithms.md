# 04. Algorithm & Algorithmic Actions

:material-account:
<span class="meta-text">Nilufar Ismayilova, Ismayil Shahaliyev</span>  
:material-calendar:
<span class="meta-text">Oct 25, 2025</span>
&nbsp;&nbsp;
:material-calendar-edit:
<span class="meta-text">Jan 30, 2026</span>


An [algorithm](https://en.wikipedia.org/wiki/Algorithm) is a step-by-step procedure or set of rules to solve a specific problem or perform a task. It is like a recipe in cooking: you follow a clear sequence of actions to achieve a specific result. In computer science, algorithms receive some _input_, _process_ it in a logical way, and produce an _output_. What makes a **good algorithm** is that it has a clear starting point, a clear ending point, and every step is unambiguous - there is no confusion about how it should be executed.

!!! note
    Imagine you want to find the largest of three numbers: A, B, and C. A simple algorithm would say: first compare A and B. If A is greater than or equal to B, then compare A with C. If A is still the greatest, then A is the largest number. Otherwise, C is the largest. But if in the very first comparison B was already greater than A, then compare B with C, and whichever is larger is the answer. This exact set of steps can be written in code or performed by a person.

!!! success "Exercise"
    Bring an example of an algorithm from your daily life.

The word _algorithm_ traces back to the name of the mathematician [Al-Khwarizmi](https://en.wikipedia.org/wiki/Al-Khwarizmi), whose systematic approach to calculation and problem-solving became foundational to modern mathematics and computing. Similarly, the word algebra comes from his mathematical treatise _Al-Jabr_, translated as "completion" or "rejoining".

[Turing Award](https://en.wikipedia.org/wiki/Turing_Award) winner computer scientist [Donald Knuth](https://en.wikipedia.org/wiki/Donald_Knuth) is best known for the book _The Art of Computer Programming_. His work helped establish _algorithmic analysis_ as a discipline.

[Computational complexity](https://en.wikipedia.org/wiki/Computational_complexity) of an algorithm describes how the resources an algorithm needs (e.g. time, memory, etc.) grow as the input size increases. **Time complexity** tracks how many computational steps are required. **Space complexity** tracks how much memory is used. Within these, we distinguish worst-case, average-case, and best-case behavior depending on how the input might vary. [Asymptotic (Big O) notation](https://en.wikipedia.org/wiki/Big_O_notation) provides a language for comparing growth rates when inputs become large. Big O gives an upper bound: it states that the algorithm grows no faster than some function up to constant factors. Big O abstracts away hardware, implementation details, and constants, focusing only on how the algorithm scales with input size.


<figure class="w50">
  <img src="../../assets/images/lecture04/abota.jpg" alt="A Book of Tasty Algorithms (foreword by Donald Knuth)">
  <figcaption></figcaption>
</figure>

Knuth also wrote a [special foreword](https://cs.stanford.edu/~knuth/azerbaijan.pdf) publication for participants of the International Olympiad in Informatics ([IOI 2019](https://stats.ioinformatics.org/olympiads/2019)) held in Azerbaijan. _A Book of Tasty Algorithms_ is a playful recipe book based on dishes from Azerbaijani cuisine, representing algorithmic ideas through the familiar structure of cooking, drawing a parallel between writing algorithms and following recipes.

## Algorithmic Actions

Algorithmic actions describe the fundamental operations that make up any computer program. These actions determine how a program makes decisions, repeats steps, organizes tasks, and manages data. The five main algorithmic actions are **selection**, **repetition**, **modularization**, **recursion**, and **name binding**.

### Selection
_Selection_ means choosing between different paths of execution based on a condition. It allows the program to "decide" what to do depending on input or data values. In the pseudo-code below, if the temperature is above 30°C, the system turns on the air conditioner; otherwise, it keeps it off:

```c
if (temperature > 30) {
  turnOnAC();
} else {
  turnOffAC();
}
```

### Repetition
_Repetition_ means performing the same set of instructions multiple times until a certain condition is met. This prevents code duplication and makes programs efficient. In programming (pseudo-code), printing numbers from 1 to 5 using a loop will look like:

```c
for (int i = 1; i <= 5; i++) {
  print(i);
}
```

### Modularization
_Modularization_ means dividing a complex program into smaller, manageable, and reusable parts, called modules. This improves readability, debugging, and reusability.

!!! note
    A billing program may have modules `calculateTax()` and `printBill()` for computing tax on a purchase and printing the final receipt. Here, each module performs one well-defined task, making the program organized and easier to maintain.

At a deeper level, modularization is a principle of system organization, not limited to programming. It refers to the act of decomposing any complex system - software, mechanical, social, or educational - into smaller subsystems that can be developed, understood, or replaced independently.

In programming, modularization starts with [**functions**](https://en.wikipedia.org/wiki/Function_(computer_programming)), which perform a single, well-defined task. Related functions can be grouped into **classes**, which represent objects or abstract entities. Several classes and functions together form a **module**, typically a single file in a programming language like Python. A **package** is a collection of related modules organized in a directory (folder) structure, and multiple packages can form a **library** or **framework**, representing a higher level of modular organization. At the top level, systems or applications integrate many libraries and frameworks, sometimes developed by entirely different teams or companies.

```python
class Calculator:
    function add(a, b):
        return a + b
    function subtract(a, b):
        return a - b
```

In engineering, a car is designed in modules such as the engine, transmission, and electrical system, each of which can be developed or replaced independently. In education, a curriculum may be modularized into separate courses or subjects, each focusing on a distinct domain of knowledge but contributing to an integrated learning goal. In management, an organization may be divided into departments - finance, marketing, research, operations - each acting as a module with a specific role but coordinated under one structure. In architecture, buildings are designed with modular components such as prefabricated walls or units that can be rearranged or replaced.

Modularization is about **complexity management**: dividing a whole into parts that are independent in function and cooperative in purpose. At even higher levels, modularization can be systemic or societal. Complex infrastructures - transportation networks, communication systems, and governance structures - are modularized into interacting parts [so that local failures do not collapse the entire system](https://en.wikipedia.org/wiki/Financial_crisis_of_2007%E2%80%932008).


!!! success "Exercise"
    Take a major goal of yours for the next six months and divide it into manageable modules.

### Recursion

_Recursion_ occurs when a function calls itself to solve smaller parts of the same problem. Each recursive step reduces the problem size until it reaches a **base case**, the simplest situation where the function stops calling itself. The base case is **not** the starting point, it is the stopping condition

!!! note
    You can imagine real-life recursion: a tree has branches, branches have smaller branches, those branches have their own smaller branches, etc. But this recursion may go infinitely and you usually need to stop at some point. That stopping condition is the base case. Let's say, after four-five branching steps a tree will stop growing any branches. With that logic, there is no base case in the case of two mirrors oppositely directed to each other. There is no base case and you will see infinite reflections. Or: _infinite recursion._

We know that the factorial of `n` is the factorial of the previous number multiplied by `n`. That means:
```c
factorial(5) = factorial(4) * 5
factorial(4) = factorial(3) * 4
factorial(3) = factorial(2) * 3
factorial(2) = factorial(1) * 2
```

Or, as a general case:

```c
factorial(n) = factorial(n-1) * n
```

We can write the following recursive function:

```c
factorial(n) {
  return n * factorial(n - 1);
}
```

But this pseudo-code has an issue. It is akin to two mirrors looking at each other - it will never stop. It will return the following functions:

```c
factorial(1) = factorial(0) * 1
factorial(0) = factorial(-1) * 0
factorial(-1) = factorial(-2) * -1

// ad infinitum
```

Not only `factorial(-1)` doesn't make sense, but also you will be in an infinite recursion. To fix it, you need to add a halting (stopping) condition: Base case.

```c
factorial(n) {
  if (n == 1 or n == 0) return 1; // base case
  else return n * factorial(n - 1); // recursive call
}
```

So, your code will work in the following way, given that `n` is a non-negative number (in this case `n=4`): 

```c
factorial(4) = factorial(3) * 4 = factorial(2) * 3 * 4 = factorial(1) * 2 * 3 * 4 = 1 * 2 * 3 * 4 = 24.
```

!!! success "Exercise"
    Write a pseudo-code for recursive algorithm to find the sum of natural numbers.

### Name Binding

_Name binding_ refers to the process of connecting _identifiers_ (names) to specific objects, values, or _memory locations_ in a program. It defines where and when a variable's name is linked to the data it represents. This action allows the program to store, access, and update information consistently.

When a program needs to store the value `70`, it allocates memory to represent it. For example in memory cell represented with hexadecimal number `0x21A95BC`, bytes will be allocated to represent `70` in binary. Then, if you want to reuse that value in the future, you need to **assign** (not equalize) that value to an identifier. 

```c
speed = 70
```

The identifier speed becomes bound to the value `70` stored in memory. If later the value changes (`speed = 50`), the same name now refers to a different value, possibly stored in a different memory location.

## Dijkstra's Shortest Path Algorithm

In many information systems, a common task is to search for an item. In some systems, the problem involves navigating networks, such as transportation systems or computer networks, where components are connected by links with different costs, delays, or capacities. In these cases, the goal is not merely to locate an item, but to determine an _optimal path_ through the network.

[Edsger W. Dijkstra](https://en.wikipedia.org/wiki/Edsger_W._Dijkstra) was a Dutch computer scientist and one of the founders of modern computer science. [Dijkstra's algorithm](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm) is a classic solution that computes the shortest path from a starting node to all other nodes in a [weighted graph](https://en.wikipedia.org/wiki/Graph_%28discrete_mathematics%29) where all edge weights are non-negative. The algorithm maintains a set of nodes whose minimum distance from the start is already known. At each step, it selects the node with the smallest temporary distance, finalizes its distance, and then updates (relaxes) its neighbors by checking whether passing through this node yields a shorter path.

<figure>
  <img src="../../assets/images/lecture04/dijkstra.gif" alt="Dijkstra's shortest path algorithm">
  <figcaption>
    Dijkstra’s algorithm to find the shortest path between a and b. It picks the unvisited vertex with the lowest distance, calculates the distance through it to each unvisited neighbor, and updates the neighbor’s distance if smaller. Mark visited (set to red) when done with neighbors. By
    <a href="//commons.wikimedia.org/w/index.php?title=User:Ibmua&amp;action=edit&amp;redlink=1"
       title="User:Ibmua (page does not exist)">Ibmua</a> –
    Work by uploader, Public Domain,
    <a href="https://commons.wikimedia.org/w/index.php?curid=6282617">Link</a>
  </figcaption>
</figure>

A [priority queue](https://en.wikipedia.org/wiki/Priority_queue) is often used to efficiently select the next node with the smallest distance, which allows the algorithm to scale well for large graphs. The algorithm finishes when all nodes have been processed or when the destination node is finalized. The output is both the shortest distance and the actual path taken.

## Additional Material
- [Intro to Algorithms: Crash Course Computer Science #13](https://www.youtube.com/watch?v=rL8X2mlNHPM)
- [What's an algorithm? - David J. Malan](https://www.youtube.com/watch?v=6hfOvs8pY1k)
- [What on Earth is Recursion? - Computerphile](https://www.youtube.com/embed/Mv9NEXX1VHc)
- [Binary, Hanoi and Sierpinski, part 1](https://www.youtube.com/embed/2SUvWfNJSsM)
- [Dijkstra's Algorithm - Computerphile](https://www.youtube.com/watch?v=GazC3A4OQTE)


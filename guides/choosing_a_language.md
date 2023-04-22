# How to Choose a Programming Language
## For Chemists and the Chemistry-Adjacent

{This will initially be a long document, but later it can be chunked into multiple .md files with links or a TOC.
See [this guide](https://github.com/luong-komorebi/Markdown-Tutorial/blob/master/README.md) for an example of a TOC and general organization.}

{TODO: edit for 1st vs 3rd person consistency.
If this will be collaborative, 3rd is better.}

If you are interested in programming,
but don't know where to start,
answering the question "What programming language should I learn?" 
is the first obstacle to overcome. 

This is an (opinionated, non-authoritative) guide 
to help people answer that question for themselves. 
The author will try to make their personal opinions 
and lack of knowledge clear as warranted. 
Corrections and additions to this guide are welcome!

This guide will mention the most commonly-encountered languages 
that are either particularly useful to chemists, 
or are particularly well suited for new programmers to get their feet wet.

Whatever language you choose, 
once you dive into it you will also learn all sorts of tools, skills and habits 
that are not language-specific. 
If you spend some time learning one language, and decide to try another, 
you will have the pieces in place to pick up the next language 
and start working with it.

### What are you most interested in?

This guide is structured around the likely answers to that question.
Most of this guide will be for people that already have some idea 
of what they want to do with their new coding superpowers.
However, maybe you just think coding sounds useful, 
intellectually stimulating, or fun. 
If that is the case, 
the author's *opinionated* answer is:

**<p align=center>[Python.](https://www.python.org/)</p>**

Python has been described as being "the second-best language for everything".
In particular, it's a top-tier language for data processing and visualization, 
machine learning (ML), and artificial intelligence (AI).
There is a huge ecosystem of scientific and numeric packages for Python as well.
Plus, (in the author's opinion), Python is easy to pick up 
and start doing useful things with. 
The language is *expressive*, almost reading like "pseudo-code" at times. 
For example, let's say you wanted to tell the computer:

"for each name in my list of guests: Amy, Bob, Cathy and Doug,
print "Hi, (name of guest!)"

This is what it would look like in Python:

```python
for name in ['Amy', 'Bob', 'Cathy', 'Doug']:
    print(f'Hi, {name}!')
```

In contrast, this is what it would look like written in c:

```c
#include <stdio.h>
#include <stdlib.h>
int main(void) {
    char guests[4][10] = {"Amy", "Bob", "Cathy", "Doug"};
    for (int i = 0; i < 4; i++) {
        printf("Hello, %s!\n", guests[i]);
    }
    return EXIT_SUCCESS;
}
```

An honorable mention goes to 
[the Julia programming language](https://julialang.org). 
The author does not have Julia experience, 
and the Julia community is much smaller than the Python community. 
However, it is a multi-purpose language 
that seems particularly well-suited for scientific computing, 
data science and visualization, machine learning and numerical computation. 
It is also much faster than Python, if computation speed is a concern.

#### When might "Python" not be the best answer?

{This section is indulgent, too wordy, and most likely redundant with the application-specific sections to follow. For now, I'll vent my opinions and then re-write to something useful to others, and to-the-point }

There are a few applications where Python is **not** a top-tier choice. 
It may be *possible* to accomplish in Python, 
but inefficient, awkward, difficult, or requiring arcane knowledge. 
The following list is in roughly increasing order 
of Python being unsuitable to the task (in the author's opinion).

- running on multiple CPUs ("multithreading"): 
  this is possible, but Python has the notorious 
  [Global Interpreter Lock (GIL)](https://www.python.org/) 
  that makes this cumbersome.
- speed-critical applications: Python is a slow language. 
  However, it can interface with faster languages. 
  For example, the widely-used `numpy` libary for numerical computation 
  uses Fortran libraries "under the hood", 
  and its possible to write Python code 
  where the faster language is performing most of the work. 
  However, if you are designing a computer 
  to perform stock market micro-transactions so fast 
  that your speed is limited by how long the wire is 
  between your computer and the stock exchange across the street, 
  you don't want to be using Python.
- creating cross-platform desktop applications. 
  This is very doable, but Python has to use non-Python GUIs 
  via libraries such as `tkinter` or`PySides/PyQt`. 
  These libraries inherit the quirks of their original languages, 
  such as C++, and don't have a "pythonic" feel. 
  There are many examples of "toy" Python apps online, 
  but for more complicated applications you'll find less guidance.
- packaging cross-platform applications 
  as a one-file "MyAwesomeApp.exe" or "MyAwesomeApp.app" program, 
  that another person can just download, double-click, and run.
  The difficulty ranges from "a bit of fuss required" 
  to "well-nigh impossible without arcane knowledge".
- writing applications for mobile devices. VERY DIFFICULT. Possible (Google 'kivy' and 'beeware', but Here Be Dragons)

Specific use cases for programming, with specific recommendations, now follow.

{stubs for future content follow; 
keep in mind why a chemist would want to take a language up}

{TODO: order list subjectively from most to least interest that most chemists would have in the activity}

{maybe state somewhere what languages you're including, 
based on some criterion such as StackOverflow annual surveys. 
Don't need to include the more fringe languages such as Kotlin, Haskell etc.}

### Data Collection, Cleaning, Processing, and Visualization

Python and [R](https://www.tidyverse.org/) are excellent choices. 

An advantage of R is that there is a 
"[tidyverse](https://www.tidyverse.org/)" of widely-adopted packages, 
where there is a clear favorite way to do something, 
such as make a plot or a web application. A disadvantage is that is focused on working with data.

Python has the advantage of being useful in many contexts beyond data science. However, you may find yourself spoiled for choice when selecting tools, e.g. what library to use for plotting graphs. 

Other considerations:

- Julia 
- [SQL(structured query language)](https://en.wikipedia.org/wiki/SQL): 
  If you find yourself needing to work with databases, adding some SQL knowledge on top of your preferred programming language will be useful. 
- See also 
  [this article on Codecademy](https://www.codecademy.com/resources/blog/data-science-languages/) 
  describing these and other options.

### ML/AI

You will find more ML/AI resources that use Python than any other language. There is a lot to learn in this field, so my suggestion is start learning using Python to get up to speed before considering another language.

### Systems Programming and Scripting
{bash; python; many of the C-like languages like Go, Rust, C++, Java(ew); 
probably not languages like Swift and C# that are closely tied to an OS. 
The lower the language level, the less noob-friendly}

If your interest is working with the nuts and bolts of a computer system
(working with files and directories, scheduling automated tasks, etc.)
then Python is a great place to start. 
There is even 
[a book written about automating tasks with Python](https://automatetheboringstuff.com).

It is also extremely useful for programmers in general 
to learn how to use the command line interface ('CLI'; 'terminal'). 
On Unix-like systems (macOS; linux) this means learning bash 
or a closely-related variant 
(Macs recently switched from bash to zsh, but they are mostly the same). 
Windows comes with PowerShell, but you can install a bash CLI as well.

As a motivational example, here is a one-line command that will: 
- recursively search through a tree of nested NMR data folders; 
- find the temperature each experiment was run at; and 
- save a .csv that lists all NMR jobs and temperatures:

```bash
$ grep -r "##\$TE=" --include="*acqus" . | cut -c 3- | sort | sed -e 's/:##\$TE= /,/' > T_pH7.csv
```

That may look incomprehensible, 
but it's composed from several individual bash commands 
that you would learn in any basic bash guide. 
With very little bash experience, 
I could accomplish in one terminal command 
what would require many lines of Python or equivalent code.

Both Python and Bash are widely used for writing executable "scripts" 
to automate common tasks.

There is a large family of "curly-brace" languages 
that are all good "professional programmer" choices for system programming: 
c++, Go, Java, Rust, etc. 
However, the author's advice is to avoid languages that are so "low-level" 
that you have to constantly consider fussy things, such as:
- where and how variables are stored in memory and accessed; 
- how to manage memory allocation;
- determining "which one of these nine types of integers is best 
  to represent my number?". 

However, if you really want to learn programming 
from the viewpoint of a computer scientist or a software engineer, 
a language such as c/c++ will make you learn 
what goes on "under the hood" of your computer.

### Instruments and Devices

If you want to get started with devices, microcontrollers, 
and Internet of Things (IoT) projects, Python is a good choice. 
It's the default choice if you are working on a Raspberry Pi. 
Many controllers can be programmed with Python 
or a subset of Python (e.g. [CircuitPython](https://circuitpython.org)).

[Arduino microcontrollers](https://www.arduino.cc) use a variant of c++ for their programs, but Python is also supported (via [MicroPython](https://docs.arduino.cc/learn/programming/arduino-and-python)).

It's not possible to generalize across scientific instrumentation,
but you may find low-level languages like c being used. 

### Numerical Computation

{python good if e.g. vectorized numpy, CUDA etc. 
Do homework but probably c/c++/Rust/Julia/MATLAB. Zig?  
Avoid proprietary, e.g. MATLAB. 
Probably Python > Julia > c++, Rust > field for a beginner scientist. FORTRAN is still great performance-wise but not something to recommend to a new programmer}

Even though Python is a slow language, 
it can make use of libraries that run faster code 
(e.g. FORTRAN, c) "under the hood". 
An example of this is 
[the `numpy` library](https://numpy.org) for numerical computation. 
With optimization, Python can often be fast enough for your needs. 

There are libraries that can help speed up your code, 
e.g. by [implementing "just-in-time" compiling](https://numba.pydata.org) 
or [GPU acceleration](https://cupy.dev).
There is also a version of Python, 
[PyPy](https://www.pypy.org), that runs faster than standard Python. 

If your code needs to run faster than Python is capable of, here are some alternatives to consider:

- Julia 
- MATLAB is widely used by scientists and engineers, 
  but it's proprietary. 
  If your workplace has bought a license for it, 
  and you do a lot of numerical work (e.g. linear algebra), 
  it can be very useful. 
- You could consider the "curly-brace" languages such as c/c++, 
- but the learning curve will be steeper. 
  If others in your field use one of these languages, 
  it may be worth it.

### Web Programming

If your primary interest in things Web-related 
(creating web pages, webservers, online databases etc.), 
JavaScript (JS) is ubiquitous in Web programming. 
It is also a great choice for a first language to learn. 
It can be used for both "front-end" web development 
(writing JS/HTML/CSS code for display in a web browser), 
and in "back-end" development (setting up a web server). 
Most beginners will be interested in the front-end work of creating a website, and let a web hosting service take care of the back end.

Python is also a good choice, especially for back-end work.
Popular web frameworks include Flask, Django, and FastAPI. 
For example, 
if you have data in a database
that you want to make available over the internet, 
you can use one of these frameworks 
to create a web API (Application Programming Interface) 
that will let people around the world access and use your data.

If you are not programming in a language that is native to mobile devices
(e.g Swift for iOS or Java for Android),
another way to get your program onto users' phones
is to create a web application.

### Desktop Applications

{python if you must; JS Electron; Java/c++?(ew). 
Personally don't recommend native-app languages e.g.Swift, C# 
unless you are a huge Mac or PC fan. 
REMEMBER THE CAUTIONARY TALE OF VISUAL BASIC 6.}

# How to Choose a Programming Language
## For Chemists and the Chemistry-Adjacent

"What programming language should I learn" 
is a common question asked by people that are interested in programming, 
but don't know where to start. 
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

<center>**Python.**</center>

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

{Consider adding the "Pythonic French Deck" from the Fluent Python introduction, 
or better yet adding it as code example}

There are a few
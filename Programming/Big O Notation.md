---
tags: 
- computer_science
- programming
- analysis
created: Tuesday, March 12, 2024 2:37 PM
created_at: 2024-03-12T14:37:47-04:00
---
## What is Big O Notation?

Big O Notation is a way to notate the worst-case performance scenario of an algorithm in terms of run time or memory used as the size of the input data grows.

## Terminology

- algorithm = steps to solve a problem (think of it as the body of a function)
- input = the dataset given to an algorithm
- performance = a comment on the time spent or memory used by an algorithm (this will be used to refer to "time and/or space" in sections below)
- space = amount of memory on disk

## Notations

### O(1)

This means performance will have the same time or use the same space no matter how much the input grows.

One example from Rob Bell, changing one element in a list:
```
bool IsFirstElementNull(IList<String> elements)
{
    return elments[0] == null;
}
```

### O(N)

This means as the size of the input grows so will performance in a linear fashion.

Rob Bell's example, searching through a list for an element:
```
bool ContainsValue(IEnumerable<string> elements, string value)
{
    foreach (var element in elements)
    {
        if (element == value) return true; 
    }     
    return false; 
}
```

### O(N^2)

This implies a direct exponential relationship between input and performance.

An example is a function that uses a nested for-loop. Rob Bell's example is a function that checks if a list has a duplicate:

```
bool ContainsDuplicates(IList<string> elements)
{
    for (var outer = 0; outer < elements.Count; outer++) 
    {
        for (var inner = 0; inner < elements.Count; inner++) 
        { 
            // Don't compare with self 
            if (outer == inner) continue;             
            
            if (elements[outer] == elements[inner]) return true; 
        }
    }    
    return false;
}
```

The nested for-loop is a nice way to remember this type of complexity. Essentially, working with 2D arrays is a nice example. This leads to, "What if there's a third, fourth, or Nth level of nesting?" It's as you're probably imagining: N^3, N^4, N^N.

### O(2^N)

This also implies an exponential relationship between input and performance, however instead of the performance being directly proportional to the input, the performance doubles as the input grows.

If we imagine a graph and graph out `O(N^2)` and `O(2^N)` we'll see the latter has a less steep slope and thus better performance than `O(N^2)`.

Rob Bell's example of this is recursively figuring out Fibonacci numbers:
```
int Fibonacci(int number)
{
    if (number <= 1) return number;
       
    return Fibonacci(number - 2) + Fibonacci(number - 1); 
}
```

NeetCode's video on Big-O notation also uses recursion as an example here but pointed out an important aspect on why the naive Fibonacci implementation is O(2^N): it has two branches to follow. For every number, this Fibonacci algorithm has two call itself twice.

Similarly to [O(N^2)](Big%20O%20Notation.md#O(N%202)), the more branches you have the bigger the constant will be. If there were 3 branches, then the runtime would be O(3^N), 4 would be O(4^N), etc.

### O(log N) / Logarithmic

This seems tricky to imagine, but think of what a logarithm is and what it looks like on a graph.

A logarithm answers the question, "how many times do you have to multiply a base value by itself to get a certain number?"

Let's look at an example: log<sub>2</sub>8 = y. Another way to word this question is, "how many times do I have to multiply 2 by itself to get 8?". 3! Thus, log<sub>2</sub>8 = 3.

Now graph out y = log<sub>2</sub>(x) ([Desmos' calculator](https://www.desmos.com/calculator) is wonderful - click the keyboard icon in the bottom of the page, then "functions", and scroll to the "Calculus" section to see "log<sub>a</sub>"). Zoom out a bit and notice how the line looks as X grows. For comparison, add another line, y = x, to the graph. Big difference, huh?

An algorithm with this type of complexity implies a non-significant change in performance as the input grows. This is great! But what does it mean for an algorithm to be logarithmic? What does that look like?

Binary search and other operations on balanced binary trees are noted as having logarithmic run time. (See below for [What is a balanced binary tree?](Big%20O%20Notation.md#What%20is%20a%20balanced%20binary%20tree?)) Consider a simple balanced binary tree where the nodes are numbers and there are only 2 levels of nodes down from the root (meaning a height of 2, just like the example in the section below). What would you do if you were looking for a specific number? You'd start at the root and ask "is the number I'm looking for greater than or less than the root?" Whatever the answer is, you can completely disregard the other part of the tree.

To put numbers on this, our original tree has 7 nodes altogether. If the number we're looking for is greater than 5, we can not only disregard the root node, but also the node to the left of 5 and all of its sub-nodes. That's 4 nodes we can disregard, leaving us with just 3 nodes to check, less than half of the original tree to work through!

Now imagine a slightly bigger tree, let's say with a height of 3 (so 4 total levels including the root). It's a binary tree so the total number of elements is 2<sup>4</sup>-1 which is 15. Any time we traverse that tree we're cutting out about half of the remaining elements per level. That's a big reduction!

At this point you can imagine how performance will remain pretty similar as a tree grows (and remains balanced).

Aside: I wonder how lazy evaluation impacts this!

#### What is a balanced binary tree?

Balanced binary trees means the number of sub-levels on one side is equal to the other side and the same applies to sub-trees. Below is a  rough ASCII example:
```
     5
   /   \
  2     8
 / \   / \
1   3 7   9
```

The left side of the tree has 2 levels as does the right side of the tree. There is a total of *2 edges* (the lines connecting the numbers, or *nodes*, to each other) from the top (*root*) to any bottom value (*leaf*). Thus, the *height* of the tree is 2.

### O(n log N) and similar



## Questions

### Is there a direct relationship between time and space?

Physics aside, are time and space interchangeable in the context of algorithm performance? Is there a one-to-one correlation where if the time for an algorithm to run increases it is implied that the space used for the algorithm also increases and vice versa? I would guess so, since if an algorithm is taking more time to process a dataset a logical explanation would be more memory is used, whether it's because of the size of the input data or because of memory created and used as a byproduct of the algorithm.

### What is the practical use of Big O Notation? When should you use it?

## Resources

- [A beginner's guide to Big O Notation by Rob Bell](https://robbell.io/2009/06/a-beginners-guide-to-big-o-notation)
- [CS Dojo's Introduction to Big O Notation and Time Complexity (Data Structures & Algorithms #7)](https://www.youtube.com/watch?v=D6xkbGLQesk)
- [NeetCode's Big-O Notation - For Coding Interviews](https://www.youtube.com/watch?v=BgLTDT03QtU)
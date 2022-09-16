---
layout:     post
title:      For-loop in Python and C
subtitle:   About variable assignment in for-loop
date:       2022-05-20
author:     Jade Wu
header-img: img/post-bg-cook.jpg
catalog: true
tags:
    - Python
    - C
---

## They Look Different

When I learned python, I found that for-loop in Python was completely different from C.

For example, in C:
```c
for (int i = 0; i < 10; i++){
    //statement
}
```
and in Python:
```python
for i in range(1,10):
    # statement
```

## Why the Output is Different

What's even more interesting is that when you execute the following code, they have different results:
C:
```c
for(int i = 0; i < 5; i++){
    printf("%d ", i);
    i = 5;
}

// Output:
>>>0
```
Python:
```python
for i in range(0, 5):
    print(i)
    i = 5

# Output:
>>>0
>>>1
>>>2
>>>3
>>>4
```

These codes seem to do the same thing, but why are their results totally different?

## Reason 

We can know that the statement "i=5" assigns value 5 to the variable i, so the loop runs only once, outputting the initial value of i as 0, 

and then the value of i is changed so the loop ends.

However, the result of the Python code shows that the value of i is not changed, so it prints all numbers from 0 to 4.

Why is the value of variable i not changed? This is exactly the difference of for-loop between C and Python that I want to mention.

Let's look into Python 3's document: `https://docs.python.org/3/reference/compound_stmts.html#the-for-statement`

In part 8.3, we can see it written that "The for-loop makes assignments to the variables in the target list. This overwrites all previous 

assignments to those variables including those made in the suite of the for-loop."

My understanding is that range(0, 5) produces a list from 0 to 4, and then each time i is taken from this list before entering the loop, 

so the assignment to variable i in the statement is overwritten, which is very different from C. Interesting fact, right? 



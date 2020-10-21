# Data from User

Now that we understand that our calculator is able to do some arithmetic operations, it's still boring that the calculator just accepts code. It's time to upgrade our childhood from arithmetic to algebra. Yes, we want the calculator to take some input from user while executing the code.

## Extending the Instruction set

Let's say we teach our calculator a new instruction: '**accept**'. But wait, what do we do with the accepted number? Remember the heap. We'll put it somewhere on the **heap**.

Okay, once we put it on the heap, how do we get it back? Heap need not be as as unorganizad as we think. Do you know about the security guard at the mall entrances who snatches away your bag as you are not allow to carry your bag inside? How does he return your bag when you come back? Yes, you got it! The token number! Hurray, this is also something that calculator loves - '**Number**'!!

However, we are not so happy with numbers, we'll give it some names. Our old friends, x, y, z from algebra, they are good for us.

Okay now we have a small problem. Our calculator doesn't know to work with the heap. If you say 'add', it will look for numbers on the stack. So we need few more instructions that calculator needs to understand, let me list them below, along with their task.

- **accept** - accept a number from user and put it on stack
- **save < name >** - save the number from stack to heap with a name
- **load < name >** - load the number from heap to stack using the name

## Trying out the new tricks from our monkey

Now the calculator knows to do a little more things, let's see how code looks like for an algebraic expression:

> a + b

```
accept
save a

accept
save b

load a
load b
add
```

Let me know if I really need to explain this! Just a small clarification though. These a and b are replaced with unique numbers in the sight of the calculator. They are just like the token numbers from the security guard.

Now let's try something different.

> c = a + b

```
accept
save a

accept
save b

load a
load b
add
save c
```

Yes that's right. 'save' instruction will just pick up from top of the stack and save it.

There is an important thing you need to remember here. Our stack is very real. By real I mean, if you take an item from the top, it's no more in the stack. Like a real stack. But our heap is magical. When you take the item from there, you get a clone and the item still stays there. That item will vanish only when another item is placed there. Let me explain with the code example.


```
put 10
save a

put 20
save a

put 30
load a
add

put 50
load a
multiply
```

We saved 'a' twice here. Which means, 10 was replaced with 20 on the second save. When add instruction is reached, value of 20 is loaded from the heap. Also, when 'a' is loaded again, it still has the value of 20, is it doesn't vanish there, but the clone is what you get.

See! our calculator is acquiring some memory now. Exciting isn't it?

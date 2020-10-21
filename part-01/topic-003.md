# Simple is Complicated, Complicated is Simple

You might be thinking that our calculator is very naive and can't do anything beyond add or subtract 2 numbers. If you thought that way, there is a surprise for you. Will you believe if I tell you that this machine can do any complicated arithmetic operation? But yes, it can definitely perform, but the code gets a little complicated. Although machine is simple, it can do pretty complicated stuff, but only if you tell it how.

Remember we added 10 and 20 in our last code. Now imagine we had to multiply the result with 50. How do we do it? Well, it's just a couple more instructions!

```
put 10
put 20
add

put 50
multiply

show result
```

Did that surprize you? You know the result of 10 + 20 (30) was already on the stack. All you had to do was to put 50 on stack and call the multiply operation. Again the machine would pickup 50 and 30 from top of the stack and perform the multiplication. Get it? I'll leave it to you to try out some complicated expressions here. Something like:

> (10 + 20) * 50 / 100 - 35

```
put 10
put 20
add

put 50
multiply

put 100
divide

put 35
subtract

show result
```

## A Little trouble

It was a cheating, the above example was very simple and straight forward. Remember the famous [BODMAS rule](https://en.wikipedia.org/wiki/Order_of_operations) from childhood? If you have forgotton, time to do some hunting on wikipedia. Use the link to find out.

Say the expression was **10 + 30 x 50**. According to math rules, multiplication has to be done before addition. So the sequence of instructions needs to change a bit.

```
put 30
put 50
multiply

put 10
add
```

Although technically the code is correct, it is performing **30 x 50 + 10**. Isn't it? But how do we write the exact code, probably? Look below for the clue, there is a small change in the program. Maybe it can trigger something!

```
put 10

put 30
put 50
multiply

add
```

Got the trick? Let me explain.

By the time calculator got to multiply instruction, there are 3 items on the stack. However, executing multiply instruction takes just 2 items from top and puts back the result. So when it gets to the add instruction, stack contains 10 and the multiplication result.

## Okay, it's getting a little complicated

I hear you. It's kind of not straightforward to convert the complicated expressions into the code that this dumb calculator can understand. Especially with all the BODMAS stuff. But hold on. As long as you can put down the right order of the operations and get the result, it's fine for now. We'll figure out a way to derive this a little later. Anyways, try coding this expression:

> (10 + 20) x (30 + 40)

Don't cheat, try before you see the answer.

```
put 10
put 20
add

put 30
put 40
add

multiply
```

Wonderful! Isn't it?

[Next: Data from user](/part-01/topic-004)

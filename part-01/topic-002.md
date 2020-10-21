# First steps in coding

## What all can the calculator do?

Firstly, we'll look at what all this machine can do. As I mentioned earlier, it will be able to add, subtract, multiply and divide. But we know that all these operations needs 2 numbers to work with. Remember the toys we discussed? Calculator will pick up 2 numbers from the stack and put back the result there. So this means, we have to put the numbers into the stack first before we can ask the calculator to perform an operation. Simple isn't it?

## Special Instructions

We'll define 2 more instructions the calculator to be able to do to perform all the calculations we need. First one is to put a number into the stack. Second one is to show whatever is on top of the stack. Remember, the machine always puts back result on the stack? Most of the times, final result will be on top of the stack, even when we perform complicated tasks. Interesting isn't it?

## First piece of code

```
put 10
put 20
add
show result
```

I just wrote a piece of code before I explain anything. I guess things are obvious if you read it. Don't worry if you didn't get it.

Just pretend to be the calculator. Read the instructions one by one, and perform the task. After you executed the first 2 tasks, you should have 10 and 20 on your stack. When you execute the third task, you take out 2 items from the stack, add them and put the result back. Now the stack has the result 30. On the final task, you just share the result with the world, which is the item on top.

## Machine capabilities

Based on the program, I am just writing down the language of the calculator. Basically, the instructions that the calculator do. Popularly known as Instruction Set.

```
put <number>
show result

add
subtract
multiply
divide
```

Remember those 10 and 20 in our code? They are the constants, magical toys in the sealed shelf. They can't change while calculator is doing it's job.

Every machine has it's ways. We are looking at calculator's way of understanding things. Even modern computers are based on ways like this. I mentioned that in the calculator's world everything is a number, but here we are writing things like put, add, etc. Don't be confused. For the calculator, each instruction is just given a number. For eg. put is 1, show result is 2, add is 3 and so on. The calculator would have seen our code like this:

```
1 10
1 20
3
2
```

Now you get it? However, we are not very comfortable with numbers like the machine is. Just remember that for machine it's numbers, but we will use a bit of the language that we understand to tell the machine what we must do. However, we are writing direct instructions for the machine here. So this can also be called machine code. Modern computers have Assembly language equivalent to this.

## Some more examples

Lets practise a little more so that we understand the calculator's language. Just look at the examples below and see if it makes sense:

#### Calculate: 1 x 2
```
put 1
put 2
multiply
show result
```

#### Calculate: 4 / 2
```
put 4
put 2
divide
show result
```

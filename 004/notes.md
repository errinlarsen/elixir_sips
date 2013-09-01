Notes
=====

* What is a "y-combinator"?
* Have you explained what the purpose of the stabby ('->') operator is?

##### The 'add' function example was confusing for me.
* re: using functions as first-class types 
* I had to watch that section 3 times
* You said "add is a funtion that takes an argument ..." but you didn't
  explain that 'num' is that argument
  * Also, you didn't say that when a single argument is passed, the 'add'
    funtion will return an anonymous function
  * oh, wait, yes you did

* Maybe re-iterating certain points during your typing of the 'add' function
  (or any important message, in the future) would be helpful
* Also, smaller, more concise sentences that avoid too much "data density"
  might help (at least, it would help me)
  * As an example, the sentence, "Here, 'add' is a function that takes an
    argument, and returns a function that will add that argument to the new
    function's single argument."
  * There is a *lot* happening in the code that that sentence is describing.
  * Just breaking it up into multiple sentences can help clarify:
  * "Here, 'add' is a function. That function takes an argument. It returns a
    second function. The second function will add its single argument to the
    first function's argument."

* caveat 1: I am frequently dumb
* caveat 2: especially when discussing/learning functional programming!
  
* Writing a modified "script" for that section was helpful for me (see below)


Modified script:
================

## Using Functions as First-Class Types

Since functions are first-class in Elixir, you can pass them as arguments or
return them from other functions. Let's play with that **by defining a function
that returns an anonymous function**.

```elixir
add = fn
  num -> (fn num2 -> num + num2 end)
end
```

Here, `add` is a function that takes a **single argument, 'num',** and returns
a **different anonymous function. This second anonymous function itself accepts
a single argument, 'num2', which, in turn, returns the result of adding the
original 'num' argument to its own 'num2' argument**

**When we call the `add` function, the return value is a function**

```elixir
iex(2)> add.(3)
#Function<6.80484245 in :erl_eval.expr/5>
```

**Therefore, if we want to add two numbers together, we must call this second,
returned function with another argument**

```elixir
iex(3)> add.(3).(5)
8
```

We can use this to generate a function that adds 3 to its argument:

```elixir
add3 = add.(3)
```

**Here, `add3` is being defined as the function returned by calling `add` with
the argument '3'. We can then call the `add3` function with any number as an
argument to add that number to '3'.**

```elixir
iex(5)> add3.(5)
8
```

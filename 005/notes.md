Notes
=====

* I feel like you glossed-over/sped-through the intro on this episode.
  * What are modules in relation to *projects* and/or *applications*
  * What is the ```mix``` command's primary purpose - where does it fit in a
    developer's workflow?
  * If I wanted to immediately run the "modules_example" project, could I?
    should I?
  * What exactly did I do when I ran ```mix modules_example```
  * What is a **OTP** application?
  * What is the difference between an '.exs' file and a '.ex' file?
* Also, have you ever mentioned how to quit out of ```iex```? I had to figure
  it out
* I don't think I learn as fast as you do. You sped through the creation of
  that module without much discussion of the pieces.
  * ```defmodule``` creates a module
  * clearly, ```publish``` creates a function
  * maybe some discussion of these pieces and how the fit into *Modules*,
    *Projects*, and/or *Applications*
  * Perhaps I should ask you who your target audiance is.
  * I'll continue to assume you are talking to new(er) programers choosing
    Elixir as their first (next) language.
* With the last point in mind, what's a *REPL*?
* What's a *binary*?
  * I know what binary means, I even think I understand what binary means in
    this context (a file? anonymous file?), but what is it *really* in this
    context?
  * I don't think the tuple returned describes the last function described, I
    think it's the last return value evaluated

  ```elixir
  iex(4)> defmodule Foo do
  ...(4)> def bar do
  ...(4)> "this is bar"
  ...(4)> end
  ...(4)> fiz = 10
  ...(4)> end
  iex:4: redefining module Foo
  iex:11: variable fiz is unused
  {:module, Foo,
   <<70, 79, 82, 49, 0, 0, 7, 136, 66, 69, 65, 77, 65, 116, 111, 109, 0, 0, 0,
   106, 0, 0, 0, 12, 10, 69, 108, 105, 120, 105, 114, 46, 70, 111, 111, 8, 95,
   95, 105, 110, 102, 111, 95, 95, 4, 100, 111, 99, 115, 9, ...>>,
    10}
  ```
  
  * i.e., the return value of a method definition is the method's name ('bar')
    and its arity
* After all that talk about ```mix```, project creation, module creation (many
  different ways), then you skipped right to documentation!
  * I'm all for documentation, but we just did some stuff with some things, and
    then we abandoned them!


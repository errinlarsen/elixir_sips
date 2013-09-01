Notes
=====

* Should you assume that the viewer is familiar with Ruby
  * "... atoms are just like symbols in Ruby"
* I don't know if this is important, but I found the following interesting:

  ```elixir
  iex(3)> :foo == :"foo"
  true
  iex(4)> :"foo"
  :foo
  ```

* I immediately wanted to know how to reference elements in keyword lists:

  ```elixir
  iex(13)> kwd = [key: "value"]
  [key: "value"]
  iex(14)> kwd[:key]
  "value"
  ```

  * Also, does the same work for tuples?

  ```elixir
  iex(12)> tpl = {:a, 1}
  {:a, 1}
  iex(13)> tpl[:a]
  ** (UndefinedFunctionError) undefined function: :"Elixir.Access.a".access/2
      :"Elixir.Access.a".access({:a, 1}, :a)
      erl_eval.erl:569: :erl_eval.do_apply/6
      src/elixir.erl:147: :elixir.eval_forms/3

  ```

* The first thing I wanted to do after watching this episode was look at some
  API docs:
  * [Latest stable release documentation](http://elixir-lang.org/docs/stable/)
* Digging through those docs, it seems that Elixir has both a ```Keyword```
  module (which was mentioned in this episode) and a ```HashDict``` module.
  * ```Keyword``` is a list of tuples with the first element of each tuple
    being an atom and the second element is any value
  * ```HashDict``` is a true key/value store.
  * It seems to me that the later is closer to Ruby's ```Hash```
    * For example, a ```Keyword``` will allow duplicate keys

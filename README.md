# elixir-test-advanced

Advanced test task for Elixir developers.

### Introduction

The most of BEAM-based languages have dynamic type system. Elixir has dynamic type system as well. But as you know Elixir compiler provides some "half-typed" sugar like structures - fields of structure are static and if you will use wrong field name, compiler will raise error. But compiler here controls only keys and do not care about types of values.

Also there are `@type` and `@spec` type notations for Dialyzer tool. In some cases Dialyzer is useful, but it not give you any guarantees about types compatibility in your source code because it based on "successful typing" principle. Dialyzer will not generate warning if there is ANY (not 0%) possibility that types of your expressions are compatible. For example Dialyzer will not generate warning for this code:

```elixir
@spec factorial(non_neg_integer()) :: pos_integer()
def factorial(0), do: 1
def factorial(n), do: :bar
```

Code here has guaranteed type error in 2nd function clause as you see.

### Task

Let's imagine that we have Elixir project that is 100% covered with `@type` and `@spec` notations. We can access to Elixir AST of all modules used in this project. Then...

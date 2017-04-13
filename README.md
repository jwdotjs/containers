# Containers

Containers are functional data structures that help provide greater runtime safety and polymorphism.

## Protocols

  * `Appenedable` - A container that provies an interface of `append`. Safe against `nil` values.
    Namely when passing a container with the value `nil` into either the first of second argument
    to `append`, the other value is not change and there is no runtime error.
  * `Mappable` - A container that provies an interface to `map`. When `map` is called on a container that
    has a `nil` value that container just passes through with out the mapping function being called, and
    this helps prevent runtime errors.
  * `Sequenceable` - A container that provides an interface of `next`. This allows the chaining of computations.
  * `Unwrappable`  - A container that provides an interface to `safe` and `unsafe` unwrapping of inner value. Safe
    will need a default in case of `nil` value of container, helping prevent runtime errors. Unsafe will just return
    the value of the container regardless of a `nil` value potentially causing runtime errors

Since these are protocols, and highly decoupled, a developer can implement them as needed on their own structs.

## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed
by adding `containers` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [{:containers, "~> 0.1.0"}]
end
```

Documentation can be generated with [ExDoc](https://github.com/elixir-lang/ex_doc)
and published on [HexDocs](https://hexdocs.pm). Once published, the docs can
be found at [https://hexdocs.pm/containers](https://hexdocs.pm/containers).

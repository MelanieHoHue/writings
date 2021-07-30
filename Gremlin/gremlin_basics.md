# Gremlin Basics

- nearly every query starts with a `g.V()` or `g.E()`
- `g` is a graph traversal source object  ***for traversing*** the loaded graph.
> `g` is also the starting point when "travelling" and querying the graph`.
- the `.V()` step returns ***vertices***
- the `.E()` step returns ***edges***
> `.V()` and `.E()` can also take parameters to identify (or narrow down) the set of vertices or edges that ist asked for.

http://tinkerpop.apache.org/docs/current/reference/ : Apache TinkerPop´s documentation on possible query steps
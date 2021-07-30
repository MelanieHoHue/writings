# Traversing: Walking the Graph

#### "Walking the graph"
> ... describes "*starting at a vertex traversing one or more vertices and edges and ending up at a different vertex or sometimes, back where you started in the case of a circular walk.*"
>
>"*The journey we took ... is often referred to as our **path**.*"

#### Adjacent vertices
... are connected through an edge

#### Incident (vertex and edge)
"*A vertex and an edge are considered ***incident if they are connected*** to each other.*"

#### Traversal stepd and where they´re "going"
| Traversal step | Meaning | take one or more edge labels as parameter (optionally) |
| - | - | - |
| out | Outgoing adjacent ***vertices*** | yes |
| in | Incoming adjacent ***vertices*** | yes |
| both | Incoming and outgoing adjacent ***vertices*** | yes |
| outE | Outgoing incident ***edges*** | yes |
| inE | Incoming incident ***edges*** | yes |
| bothE | Both outgoing and incoming incident ***edges*** | yes |
| outV |Outgoing ***vertex*** | no |
| inV | Incoming ***vertex*** | no |
| otherV | The ***vertex*** that was not the vertex we came from | no |
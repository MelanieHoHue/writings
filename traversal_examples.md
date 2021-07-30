# Traversal Examples

> #### Where can I fly to from Austin?

// 1) find the Austin airport (with code 'AUS')
// 2) find all connected vertices (out().values('code'))
// 3) put results into a list
`g.V().has('airport', 'code', 'AUS').out('route').values('code').fold()`

**NOTE:** as there exists only one kind of edges the label in the `out()` step isn´t needed. But it´s good practice to declare the kind of edges you´re looking for.

> #### From which airports can I fly to London City Airport?

// 1) find all incoming connections into London City Airport
// 2) return their IATA codes
// 3) put results into a list
`g.V().has('airport', 'code', 'LCY').in('route').values('code').fold()`

> #### To which airport in the USA can I fly from London Heathrow ?
// 1) find the vertex with represents London Heathrow
// 2) find all it´s connected vertices with the country label 'US'
// 3) give back their airport codes
`g.V().has('code', 'LHR').out('route').has('country', 'US').values('code')`

## Path
> Showing every visited object - edges as well as vertices - is the path

// 1) start at London City Airport (LCY)
// 2) find all outgoing edges (.outE())
// 3) find all vertices on the other side of the outgoing edges (.inV())
`g.V().has('airport', 'code', 'LCY').outE().inV().path()`

**NOTE:** The same query can deliver a result in a more human readable way by the help of ***modulators*** like so:

`g.V().has('airport', 'code', 'LCY').outE().inV().path().by('dist').by('code')`
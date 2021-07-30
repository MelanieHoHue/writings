# Query examples

##### All vertices that have the label 'airport'
`g.V().hasLabel('airport')`

##### Find the DFW vertex
`g.V().has('code', 'DFW')`

##### Combinating the two previous queries (2 varaints)
`g.V().hasLabel('airport').has('code','DFW')`
`g.V().has('airport', 'code', 'DFW')`

##### Find the DFW vertex and give back it´s values/properties
`g.V().has('code', 'DFW').values()`
`g.V().has('code', 'DFW').valueMap()`
narrowed down to only some values:
`g.V().has('code', 'DFW').values('city')`
`g.V().has('code', 'DFW').values('runways', 'icao')`

##### Examples for asking for existance
`g.E().has('dist')     // all edges that have a 'dist' property`
`g.V().has('region')   // all vertices that have a 'region' property`
or ***has NOT***
`g.V().hasNot('region')  // shorthand for the following query`
`g.V().not(has('region'))`

##### Counting objects (vertices/edges)
`g.V().hasLabel('airport').count() // no of vertices that are airports`

##### Counting *outgoing* edges (routes in this example)
`g.V().hasLabel('airport').outE('route').count()`
using just *out()*:
`g.V().hasLabel('airport').out('route').count()`
or even shorter:
`g.V().out('route').count()`

##### Counting *incomming* edges (routes in this example)
`g.V().hasLabel('airport').inE('route').count()`
using just *out()*:
`g.V().hasLabel('airport').in('route').count()`
or even shorter:
`g.V().in('route').count()`

##### Counting *all edges* that are routes
`g.E().hasLabel('route').count()`

##### All airports grouped by country
`g.V().hasLabel('airport').groupCount().by('country')`

##### Routes from AUS to ARG with 2 hops
`g.V().has('code','AUS').out().out().out().has('code','AGR').path().by('code')`

###### using `.repeat()` & `.times()` instead of repeating `.out()`
`g.V().has('code', 'AUS').repeat(out()).times(3).has('code','AGR').path().by('code')`
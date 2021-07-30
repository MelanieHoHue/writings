# Counting Groups

> For large graphs it is not recommended to ask a query that looks at *ALL* vertices and edges. In those cases it´d be a better practice to use only a set of objects or a sub-graph.

###### Examples:

// how many of each type of vertex ?
`g.V().groupCount().by(label)` or: `g.V().label().groupCount()`

// how many of each edges type?
`g.E().groupCount().by(label)` ort: `g.E().label().groupCount()`

// how many airports are there in each country
`g.V().hasLabel('airport').groupCount().by('country')`

// how many airports are there in each country?
// same result as above, but look at country first
`g.V().hasLabel('country').group().by('code').by(out().count())`

// the same for each continent
`g.V().hasLabel('continent').group().by('code').by(out().count())`

// how many airports are there in France (with first counting all countries)
`g.V().hasLabel('airport').groupCount().by('country').select('FR')`
// same result could be reached by querying the airport-vetices with the label 'FR' and count them
`g.V().has('airport', 'country', 'FR'),count()`
// but if the same query shall be asked for several countries at once it´s better to use select
`g.V().hasLabel('airport').groupCount().by('country').select('FR', 'GR', 'BE')`

### More examples:
http://www.kelvinlawrence.net/book/PracticalGremlin.html#countmore 
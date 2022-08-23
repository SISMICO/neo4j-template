# neo4j-template

## Import files

### Files
`nodes.csv`
``` csv
NodeID,NodeName,NodeAttribute
1,Samsung,10
2,Dell,11
3,LG,9
4,HP,10
```

`vertices.csv`
``` csv
NodeID,NodeName,NodeAttribute
1,Samsung,10
2,Dell,11
3,LG,9
4,HP,10
```

### Load Command

``` cypher
LOAD CSV FROM 'file:///examples/nodes.csv' AS line
CREATE (:Company {id: line[0], name: line[1], rank: toInteger(line[2])})
```

``` cypher
LOAD CSV FROM 'file:///examples/buy.csv' AS line
MATCH (a:Company), (b:Company) WHERE a.ID = line[0] AND b.ID =line[1]

CREATE (:Company {id: line[0], name: line[1], rank: toInteger(line[2])})
```

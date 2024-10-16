# Playground and testing for nested sets databases implemetation 

## Context 
- Classification Tree: A tree structure with an unkown size of Nodes structured in a child-parent with no cycle.
- Items: Large number of elements attached to 1-n nodes.

## Functional requirements 
- Retreive all Items matching a filter with "AND, OR, NOT" Nodes
  - The Items in a Node's children should be retrieved if not matching an Exclusion (NOT)

## Exemple
Tree of Nodes
```
  - A 
    - AA
      - AAA 
    _ AB
      - ABA
  - C
    - CA
  - D
```
Query `(A or CA) not D` should retreive all items in `(A or AA or AAA or AB or ABA or CA) and not B`

Query `A and CA not D` should retrive all items in `CA and (A or AA or AAA or AB or ABA) and not B`


### References
- https://mikehillyer.com/articles/managing-hierarchical-data-in-mysql/
- https://www.postgresql.org/docs/current/ltree.html
- https://www.crunchydata.com/blog/tags-aand-postgres-arrays-a-purrfect-combination


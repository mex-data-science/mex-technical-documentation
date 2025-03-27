# Tools

This section is a collection of the current tools used by the L'Oréal Mex Data
Science Team.

## Drawio

[Drawio]()

---

## Mermaid

!!! tip
    Use `mermaid` functionalities for markdown in-file diagrams. Avoid usage
    for more complex visualizations.

[Mermaid](https://mermaid.js.org/intro/) lets you create diagrams and
visualizations using text and code. It counts with a [live editor](https://mermaid.live/edit)
so you can design a graph before its inclusion to the documentation.

It is particularly usefull for its plugin functionalities to markdown files,
for example:

```mermaid
graph LR
    MyDAG --> Directed
    Directed --> Acyclic
    Acyclic --> Graph
    Graph --> Directed
```

or more advanced charts:

```mermaid
gantt
    apple   :a, 2017-07-20, 1w
    banana  :crit, b, 2017-07-23, 3d
    cherry  :active, c, after b a, 2d
    kiwi    :d, after c, 1d
```

---

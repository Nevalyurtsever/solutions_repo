# Problem 1

# 🌐 Problem 4: Equivalent Resistance Using Graph Theory

---

## 🎯 Task 1: Algorithm Description for Equivalent Resistance Calculation

### 🔌 Physical and Mathematical Meaning

Electrical circuits can be represented as graphs:

- **Nodes** represent junctions or connection points.
- **Edges** represent resistors with weights as their resistance values.

The goal is to reduce the entire graph to a single equivalent resistance between two specific terminals.

### ⚙️ Algorithm Description

1. **Input**: Graph $G(V, E)$ with edge weights as resistances.
2. **Loop**:

   - Detect **series connections**: A node connected to exactly two resistors and no external terminal → combine in series: $R_{eq} = R_1 + R_2$
   - Detect **parallel connections**: Two nodes connected by multiple resistors → combine in parallel: $\frac{1}{R_{eq}} = \frac{1}{R_1} + \frac{1}{R_2} + ...$
   - Reduce and update the graph.

3. Repeat until graph reduces to one equivalent resistor between start and end nodes.

### 🔄 Pseudocode

```plaintext
function equivalent_resistance(graph, start, end):
    while graph has more than one edge between start and end:
        for node in graph:
            if node has degree 2 and not start or end:
                combine series resistors
                update graph
        for pairs of nodes:
            if multiple edges exist:
                combine in parallel
                update graph
    return weight of the single edge from start to end
```

---

## 🧮 Task 2: Full Python Implementation (Advanced)

### 📦 Libraries Used

```python
import networkx as nx
```

### 🐍 Python Code: Graph Simplification Algorithm

```python
import networkx as nx

def combine_series(graph):
    changed = False
    for node in list(graph.nodes):
        if graph.degree[node] == 2 and node not in ('A', 'B'):
            neighbors = list(graph.neighbors(node))
            if len(neighbors) == 2:
                r1 = graph[node][neighbors[0]]['resistance']
                r2 = graph[node][neighbors[1]]['resistance']
                req = r1 + r2
                graph.add_edge(neighbors[0], neighbors[1], resistance=req)
                graph.remove_node(node)
                changed = True
                break
    return changed

def combine_parallel(graph):
    changed = False
    for u, v in list(graph.edges()):
        edges = list(graph.get_edge_data(u, v).values())
        if len(edges) > 1:
            total_inv = sum(1.0 / e['resistance'] for e in edges)
            req = 1.0 / total_inv
            graph.remove_edges_from([(u, v)] * len(edges))
            graph.add_edge(u, v, resistance=req)
            changed = True
            break
    return changed

def simplify(graph, start='A', end='B'):
    while True:
        if not combine_series(graph) and not combine_parallel(graph):
            break
    return graph[start][end]['resistance']

# Example: Simple circuit
G = nx.MultiGraph()
G.add_edge('A', 'C', resistance=5)
G.add_edge('C', 'B', resistance=10)
G.add_edge('A', 'B', resistance=15)

# Simplify to single resistance
equivalent = simplify(G)
print(f"Equivalent Resistance between A and B: {equivalent:.2f} Ω")
```

---

## 📊 Task 3: Example Cases

### ✅ Example 1: Series Resistors

- A → C (5Ω), C → B (10Ω)
- Equivalent: 15Ω

### ✅ Example 2: Parallel Resistors

- A → B (15Ω) and A → B (30Ω)
- Equivalent: $R = \frac{1}{\frac{1}{15} + \frac{1}{30}} = 10Ω$

### ✅ Example 3: Series + Parallel Mixed

- Combine series, then reduce in parallel → final single resistance

---

## 🧠 Task 4: Algorithm Efficiency and Extensions

### ⏱️ Efficiency

- Depends on the number of nodes/edges
- Reductions via series/parallel detection are fast (linear in size of graph)

### 🚀 Improvements

- Use depth-first search (DFS) to identify subgraphs
- Implement Kirchhoff's laws with matrix methods for arbitrary topologies
- Extend for voltage/current analysis using Ohm’s Law

---

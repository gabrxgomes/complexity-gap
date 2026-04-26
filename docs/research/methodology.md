# Methodology

## Controlled Environment

All experiments are run in an isolated environment with the following guarantees:

- Python process with elevated priority (`nice -n -10`)
- Time measured with `time.perf_counter()` (sub-microsecond resolution)
- Each combination (algorithm × topology × size) executed **30 times**
- Mean, median, standard deviation, and p5/p95 percentiles reported
- Fixed random seed per experiment for reproducibility

## Graph Classes

### Erdős–Rényi G(n, p)
Random graph where each edge exists with probability \(p\). Used as a probabilistic baseline.

Parameters: \(n \in \{100, 500, 1000, 5000\}\), \(p \in \{0.05, 0.1, 0.3\}\)

### Sparse Graph
Graph where \(|E| = O(V)\). Generated with the Barabási-Albert model with \(m=2\).

### Dense Graph
Graph where \(|E| = O(V^2)\). Erdős–Rényi with \(p > 0.5\).

### Planar Graph
Generated via Delaunay triangulation over random points in the plane. Represents road networks and maps.

### Grid Graph
\(\sqrt{n} \times \sqrt{n}\) graph with edges to 4 neighbors. Regular structure, favorable for A*.

### Tree
Random spanning tree via Prüfer sequence algorithm. No cycles, hierarchical structure.

## Collected Metrics

| Metric | Description | Unit |
|---|---|---|
| `time_ms` | Real execution time | ms |
| `nodes_visited` | Nodes expanded/visited | count |
| `edges_relaxed` | Edges processed | count |
| `memory_kb` | Peak memory usage | KB |
| `path_length` | Length of found path | count |
| `gap_ratio` | `time_ms / theoretical_ops` | dimensionless |

## Gap Calculation

Theoretical complexity is calculated as the expected number of operations given \(V\) and \(E\):

\[
\text{gap} = \frac{T_{real}(G)}{C_{theoretical}(V, E)}
\]

Where \(C_{theoretical}\) is the algorithm's complexity function evaluated at the actual graph parameters.

## Statistical Analysis

- Linear regression between `gap_ratio` and structural graph parameters (density, diameter, clustering coefficient)
- ANOVA for gap comparison across topologies
- Visualizations: boxplot by topology, algorithm × topology heatmap, growth curves

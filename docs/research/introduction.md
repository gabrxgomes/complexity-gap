# Introduction

## Motivation

Graph search algorithms are central components of real-world systems: GPS routing, social networks, compilers, recommendation engines. Complexity analysis provides theoretical guarantees about asymptotic behavior, but observed performance in practice depends heavily on the **topological structure** of the input graph.

A sparse graph and a dense graph with the same number of vertices \(V\) behave radically differently in practice, even though \(O(V + E)\) treats them similarly in asymptotic analysis.

## Research Question

> **How does graph topology affect the gap between theoretical complexity and real performance (execution time, nodes expanded, memory usage) of the main search algorithms?**

## Hypotheses

**H1:** Algorithms with the same asymptotic complexity exhibit distinct gaps depending on graph topology.

**H2:** The ratio \(\frac{T_{real}}{T_{theoretical}(V, E)}\) is not constant across topologies, indicating that the hidden constant in Big O varies structurally.

**H3:** A* shows a smaller gap on spatially structured graphs (grid, planar) compared to random graphs.

## Expected Contributions

1. Empirical gap model per topology for each algorithm
2. Algorithm ranking by graph topology based on real performance
3. Open dataset with reproducible results
4. Practical recommendations for algorithm selection by graph type

## Scope

This research covers **path search** and **breadth/depth-first search** on undirected and directed graphs with non-negative weights. It does not cover maximum flow, matching algorithms, or NP-complete problems.

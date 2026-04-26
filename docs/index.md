# Complexity Gap

<span class="research-badge">In progress</span>

> **Core question:** Asymptotic complexity describes theoretical behavior at the limit — but how far does it diverge from real-world performance across different graph structures?

---

## What this research is about

This project empirically investigates the **gap between theoretical complexity and real performance** of graph search algorithms, systematically varying the topology of the tested graphs.

Algorithms analyzed:

| Algorithm | Theoretical Complexity |
|---|---|
| BFS | \(O(V + E)\) |
| DFS | \(O(V + E)\) |
| Dijkstra | \(O((V + E) \log V)\) |
| A* | \(O(E \log V)\) worst case |
| Bidirectional Search | \(O(b^{d/2})\) |

Topologies tested: random (Erdős–Rényi), sparse, dense, planar, grid, and tree.

---

## Contribution

The literature provides well-established asymptotic complexities, but few works systematically measure how **graph topology** affects the deviation between theoretical and observed behavior. This research builds an empirical model of that deviation.

---

## Reproducibility

All code, data, and experiments are available in the GitHub repository. To reproduce:

```bash
git clone https://github.com/gabrxgomes/complexity-gap
cd complexity-gap
pip install -r requirements.txt
python experiments/run_all.py
```

---

## Status

- [x] Project structure
- [ ] Algorithm implementation
- [ ] Graph topology generators
- [ ] Experiment pipeline
- [ ] Gap analysis
- [ ] Full paper

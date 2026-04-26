# Complexity Gap

<span class="research-badge">Em andamento</span>

> **Pergunta central:** A complexidade assintótica descreve o comportamento teórico no limite, mas quanto ela diverge do tempo real em grafos com estruturas distintas?

---

## O que é esta pesquisa

Este projeto investiga empiricamente o **gap entre complexidade teórica e desempenho real** de algoritmos de busca em grafos, variando sistematicamente a topologia dos grafos testados.

Algoritmos analisados:

| Algoritmo | Complexidade Teórica |
|---|---|
| BFS | \(O(V + E)\) |
| DFS | \(O(V + E)\) |
| Dijkstra | \(O((V + E) \log V)\) |
| A* | \(O(E \log V)\) no pior caso |
| Busca Bidirecional | \(O(b^{d/2})\) |

Topologias testadas: aleatória (Erdős–Rényi), esparsa, densa, planar, grade (grid) e árvore.

---

## Contribuição

A literatura apresenta complexidades assintóticas bem estabelecidas, mas poucos trabalhos medem sistematicamente como a **estrutura topológica** do grafo afeta o desvio entre o comportamento teórico e o observado. Esta pesquisa constrói um modelo empírico desse desvio.

---

## Reprodutibilidade

Todo o código, dados e experimentos estão disponíveis no repositório GitHub. Para reproduzir:

```bash
git clone https://github.com/gabrxgomes/complexity-gap
cd complexity-gap
pip install -r requirements.txt
python experiments/run_all.py
```

---

## Status

- [x] Estrutura do projeto
- [ ] Implementação dos algoritmos
- [ ] Geração das topologias de grafo
- [ ] Pipeline de experimentos
- [ ] Análise do gap
- [ ] Artigo completo

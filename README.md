# Complexity Gap

[![Deploy MkDocs](https://github.com/gabrxgomes/complexity-gap/actions/workflows/deploy.yml/badge.svg)](https://github.com/gabrxgomes/complexity-gap/actions/workflows/deploy.yml)
[![Python 3.12](https://img.shields.io/badge/python-3.12-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> Pesquisa empírica sobre o gap entre complexidade teórica e desempenho real em algoritmos de busca sobre diferentes topologias de grafo.

**Blog/Artigo:** https://gabrxgomes.github.io/complexity-gap

---

## Estrutura

```
complexity-gap/
├── .github/
│   └── workflows/
│       └── deploy.yml        # Deploy automático para GitHub Pages
├── docs/                     # Fonte do blog (MkDocs Material)
│   ├── index.md
│   ├── research/             # Seções do artigo
│   ├── code/                 # Documentação do código
│   ├── results/              # Tabelas e gráficos
│   ├── stylesheets/
│   └── javascripts/
├── graphs/                   # Geradores de topologias de grafo
├── algorithms/               # BFS, DFS, Dijkstra, A*, Bidirecional
├── experiments/              # Pipeline de coleta e CSVs de resultados
├── analysis/                 # Notebooks e scripts de análise
├── paper/                    # Rascunho do artigo
├── mkdocs.yml
├── requirements.txt          # Dependências de pesquisa
├── requirements-docs.txt     # Dependências de documentação
└── README.md
```

## Instalação

```bash
git clone https://github.com/gabrxgomes/complexity-gap
cd complexity-gap

# Dependências de pesquisa
pip install -r requirements.txt

# Dependências de documentação (opcional)
pip install -r requirements-docs.txt
```

## Rodando os experimentos

```bash
# Todos os experimentos
python experiments/run_all.py

# Topologia específica
python experiments/run_all.py --topology grid --size 1000

# Visualizar resultados
python analysis/plot_results.py
```

## Visualizando o blog localmente

```bash
mkdocs serve
# Acesse: http://127.0.0.1:8000
```

## Algoritmos

| Algoritmo | Arquivo | Complexidade |
|---|---|---|
| BFS | `algorithms/bfs.py` | O(V + E) |
| DFS | `algorithms/dfs.py` | O(V + E) |
| Dijkstra | `algorithms/dijkstra.py` | O((V + E) log V) |
| A* | `algorithms/astar.py` | O(E log V) |
| Bidirecional | `algorithms/bidirectional.py` | O(b^(d/2)) |

## Licença

MIT

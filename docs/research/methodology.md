# Metodologia

## Ambiente Controlado

Todos os experimentos são executados em ambiente isolado com as seguintes garantias:

- Processo Python com prioridade elevada (`nice -n -10`)
- Medição de tempo com `time.perf_counter()` (resolução sub-microsegundo)
- Cada combinação (algoritmo × topologia × tamanho) executada **30 vezes**
- Média, mediana, desvio padrão e percentis p5/p95 reportados
- Semente aleatória fixada por experimento para reprodutibilidade

## Classes de Grafos

### Erdős–Rényi G(n, p)
Grafo aleatório onde cada aresta existe com probabilidade \(p\). Usado como baseline probabilístico.

Parâmetros: \(n \in \{100, 500, 1000, 5000\}\), \(p \in \{0.05, 0.1, 0.3\}\)

### Grafo Esparso
Grafo onde \(|E| = O(V)\). Gerado com modelo Barabási-Albert com \(m=2\).

### Grafo Denso
Grafo onde \(|E| = O(V^2)\). Erdős–Rényi com \(p > 0.5\).

### Grafo Planar
Gerado via triangulação de Delaunay sobre pontos aleatórios no plano. Representa redes viárias e mapas.

### Grade (Grid)
Grafo \(\sqrt{n} \times \sqrt{n}\) com arestas nos 4 vizinhos. Estrutura regular, favorável ao A*.

### Árvore
Árvore geradora aleatória via algoritmo de Prüfer. Sem ciclos, estrutura hierárquica.

## Métricas Coletadas

| Métrica | Descrição | Unidade |
|---|---|---|
| `time_ms` | Tempo de execução real | ms |
| `nodes_visited` | Nós expandidos/visitados | contagem |
| `edges_relaxed` | Arestas processadas | contagem |
| `memory_kb` | Pico de uso de memória | KB |
| `path_length` | Comprimento do caminho encontrado | contagem |
| `gap_ratio` | `time_ms / theoretical_ops` | adimensional |

## Cálculo do Gap

A complexidade teórica é calculada como número de operações esperadas dado \(V\) e \(E\):

\[
\text{gap} = \frac{T_{real}(G)}{C_{teórico}(V, E)}
\]

Onde \(C_{teórico}\) é a função de complexidade do algoritmo avaliada nos parâmetros reais do grafo.

## Análise Estatística

- Regressão linear entre `gap_ratio` e parâmetros estruturais do grafo (densidade, diâmetro, coeficiente de clustering)
- ANOVA para comparação de gap entre topologias
- Visualizações: boxplot por topologia, heatmap algoritmo × topologia, curvas de crescimento

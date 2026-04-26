# Introdução

## Motivação

Algoritmos de busca em grafos são peças centrais de sistemas reais: roteamento GPS, redes sociais, compiladores, sistemas de recomendação. A análise de complexidade fornece garantias teóricas sobre seu comportamento assintótico, mas o desempenho observado em prática depende fortemente da **estrutura topológica** do grafo de entrada.

Um grafo esparso e um grafo denso com o mesmo número de vértices \(V\) têm comportamentos radicalmente diferentes na prática, mesmo que a fórmula \(O(V + E)\) os trate de forma similar na análise assintótica.

## Pergunta de Pesquisa

> **Como a topologia do grafo afeta o gap entre a complexidade teórica e o desempenho real (tempo de execução, nós expandidos, uso de memória) dos principais algoritmos de busca?**

## Hipóteses

**H1:** Algoritmos com mesma complexidade assintótica apresentam gaps distintos em função da topologia do grafo.

**H2:** A razão \(\frac{T_{real}}{T_{teórico}(V, E)}\) não é constante entre topologias, indicando que a constante oculta no Big O varia estruturalmente.

**H3:** A* apresenta menor gap em grafos com estrutura espacial (grade, planar) em relação a grafos aleatórios.

## Contribuições Esperadas

1. Modelo empírico do gap por topologia para cada algoritmo
2. Ranking de algoritmos por topologia de grafo com base em desempenho real
3. Conjunto de dados aberto com resultados reproduzíveis
4. Recomendações práticas de escolha de algoritmo por tipo de grafo

## Escopo

Esta pesquisa cobre **busca de caminho** (path search) e **busca em largura/profundidade** em grafos não direcionados e direcionados com pesos não negativos. Não cobre algoritmos de fluxo máximo, matching ou problemas NP-completos.

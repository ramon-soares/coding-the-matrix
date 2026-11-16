# Menor caminho em grafos

Exemplo de busca em largura para encontrar um caminho com o menor número de arestas entre dois vértices de um grafo não ponderado. A visualização usa igraph para destacar os vértices do caminho encontrado.

## Arquivos e funcionamento

| Arquivo | Papel |
| --- | --- |
| [Find Shortest Path.ipynb](Find%20Shortest%20Path.ipynb) | Versão em notebook, com explicações e saídas salvas |
| [Find Shortest Path.py](Find%20Shortest%20Path.py) | Versão em script |
| [Graph_ex.png](Graph_ex.png) e [Graph_ex_2.png](Graph_ex_2.png) | Imagens de exemplo dos grafos |
| [readme.txt](readme.txt) | Descrição original preservada |

Os grafos são dicionários de listas de adjacência. `shortest_path()` percorre uma fila de caminhos, evita revisitar vértices e retorna a lista do caminho ou `None` quando não há conexão. `path_coloring()` define as cores dos vértices, e `graph_plot()` constrói o grafo não direcionado para exibição.

## Como executar

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Instagram/find_shortest_path"
python -m pip install notebook python-igraph pycairo
python -m notebook "Find Shortest Path.ipynb"
```

Execute as células em ordem para acompanhar os caminhos e visualizar os grafos. A instalação do backend Cairo pode depender de componentes nativos do sistema.

Para executar a versão em script, na mesma pasta:

```powershell
python "Find Shortest Path.py"
```

O script imprime os resultados no terminal. Para consultar as figuras e controlar sua exibição, prefira a versão em notebook: o script não fornece um arquivo de destino para os desenhos.

## Resultados do exemplo

```text
Menor caminho grafo 1: ['A', 'C', 'D']
Menor caminho grafo 2: ['C', 'D', 'G', 'I']
```

Para experimentar, altere `graph`, `graph2`, `start`, `end`, `start2` e `end2`. Todos os vizinhos precisam existir como chaves do dicionário. O algoritmo minimiza a quantidade de arestas; não há pesos nas conexões.

Veja também a [introdução à plotagem de grafos](../../Explorando-bibliotecas-em-Python/graph_plot/README.md).

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

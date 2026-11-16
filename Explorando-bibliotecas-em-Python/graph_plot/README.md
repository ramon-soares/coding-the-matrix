# Plotagem de grafos com igraph

Exemplo de como transformar uma lista de adjacência em uma visualização de grafo com a biblioteca igraph.

## Como funciona

O [graph_plot.ipynb](graph_plot.ipynb) define a função `graph_plot(graph, x_box, y_box, color, layout_type)`. Ela cria os vértices a partir das chaves de um dicionário, adiciona as arestas sem repetir o par em sentido inverso e desenha o grafo com rótulos.

O notebook contém dois grafos: um com seis vértices, incluindo um isolado, e outro com nove vértices. Os exemplos usam os layouts `circle` e `large`, com tamanhos e cores diferentes.

## Como executar

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Explorando-bibliotecas-em-Python/graph_plot"
python -m pip install notebook python-igraph pycairo
python -m notebook "graph_plot.ipynb"
```

Execute as células em ordem. O código usa o backend de desenho baseado em Cairo; a instalação do `pycairo` pode exigir componentes nativos conforme o sistema. O notebook também contém células de instalação, que podem ser puladas se os pacotes já estiverem disponíveis no kernel.

## Resultado e personalização

Os grafos são exibidos no notebook, sem exportação automática de arquivos. Altere o dicionário `graph`, as dimensões da área, a cor dos vértices ou o layout nas chamadas da função. Todos os vizinhos citados nas listas devem existir como chaves do dicionário. O exemplo constrói grafos não direcionados.

Para aplicar uma busca de menor caminho a essa representação, consulte [Menor caminho em grafos](../../Instagram/find_shortest_path/README.md).

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

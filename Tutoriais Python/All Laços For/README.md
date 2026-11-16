# Laços e iteração em Python

Tutorial em notebook com exemplos de repetição e manipulação de coleções, avançando até operações com pandas e execução concorrente de tarefas.

## Conteúdo

O [loops.ipynb](loops.ipynb) apresenta:

- `for` com `range()` em contagem regressiva e `while` com incremento;
- condições dentro de laços para selecionar números pares;
- `enumerate()`, `zip()` e iteração sobre dicionários com `items()`;
- DataFrames com `iterrows()`, transformação de coluna com `apply()` e grupos com `groupby()`;
- cálculo de quadrados usando `ThreadPoolExecutor(max_workers=4)` e `executor.map()`.

Apesar do título da última seção mencionar `multiprocessing`, o código implementado usa threads por meio de `concurrent.futures`.

## Como executar

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Tutoriais Python/All Laços For"
python -m pip install notebook pandas
python -m notebook "loops.ipynb"
```

Execute as células em ordem. O notebook também contém uma célula `!pip install pandas`, que pode ser pulada após a instalação no ambiente do kernel. `concurrent.futures` faz parte da biblioteca padrão.

## Resultado e experimentação

As saídas mostram contagens, números pares, pares de nomes e idades, tabelas e grupos. O exemplo de threads retorna:

```text
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

Todos os dados são criados nas células; não há arquivos de entrada nem exportação. Altere os intervalos, as coleções e a função `trabalho()` para explorar o comportamento.

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

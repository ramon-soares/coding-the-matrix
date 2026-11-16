# Gráficos básicos com Seaborn

Notebook de introdução à visualização de dados com Seaborn, usando pandas para carregar uma base CSV. Faz parte do acervo do Codando a Matrix.

## O que você encontra

O exemplo lê `heart.csv` e apresenta gráficos de dispersão, linha, barras, regressão e caixa, além de um mapa de calor da matriz de correlação. As visualizações relacionam colunas como `age`, `chol`, `thall` e `thalachh`.

| Arquivo | Papel |
| --- | --- |
| [basic_commands_seaborn.ipynb](basic_commands_seaborn.ipynb) | Notebook principal com os gráficos |
| [heart.csv](heart.csv) | Dados utilizados nas células |
| [o2Saturation.csv](o2Saturation.csv) | Arquivo adicional do acervo, não utilizado pelo notebook |

## Como executar

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Explorando-bibliotecas-em-Python/basic_commands_seaborn"
python -m pip install notebook seaborn pandas
python -m notebook "basic_commands_seaborn.ipynb"
```

Execute as células de cima para baixo. Mantenha `heart.csv` na pasta do notebook, pois a leitura usa um caminho relativo.

## Resultado e experimentação

Os gráficos aparecem nas saídas do notebook; o código não exporta imagens. Para experimentar, altere as colunas passadas aos argumentos `x` e `y` ou o tipo de gráfico. A pasta `.ipynb_checkpoints` contém uma cópia de checkpoint do Jupyter; use o notebook principal para acompanhar o exemplo.

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

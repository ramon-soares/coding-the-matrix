# Widgets interativos no Jupyter

Notebook com dois exemplos de exploração de dados usando ipywidgets: uma tabela filtrável e um gráfico interativo de bolhas.

## Exemplos

O [widgets_jupyter.ipynb](widgets_jupyter.ipynb) combina pandas, Seaborn, Plotly Express e controles do ipywidgets:

1. **Tips:** sliders definem o valor mínimo e máximo da conta, e uma lista seleciona o sexo dos clientes. A saída mostra as linhas filtradas do DataFrame.
2. **Gapminder:** um slider seleciona o ano e caixas de seleção escolhem os continentes. O gráfico relaciona PIB per capita e expectativa de vida, com tamanho das bolhas proporcional à população.

## Como executar

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Explorando-bibliotecas-em-Python/ipywidgets_jupyter_notebook"
python -m pip install notebook pandas plotly ipywidgets seaborn
python -m notebook "widgets_jupyter.ipynb"
```

Execute as células em ordem e interaja com os controles. O conjunto `tips` é carregado por `sns.load_dataset('tips')`, que precisa de internet quando os dados ainda não estão em cache. O Gapminder é obtido por `px.data.gapminder()`; não é necessário fornecer CSVs.

## Observações do acervo

Os controles precisam de um frontend Jupyter com suporte a widgets; a visualização estática no GitHub não executa a interface. O notebook registra o comando `jupyter nbextension enable --py widgetsnbextension`, relacionado ao ambiente clássico usado no exemplo. A configuração de extensões deve corresponder à versão do Jupyter instalada.

As tabelas e os gráficos aparecem no notebook, sem gravação de arquivos. Para experimentar, altere os limites dos filtros, as colunas exibidas ou os parâmetros do gráfico.

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

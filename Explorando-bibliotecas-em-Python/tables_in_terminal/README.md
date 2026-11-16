# Tabelas no terminal com PrettyTable

Exemplo de criação e formatação de uma tabela de funcionários no terminal.

## O que o código demonstra

O [example_table.py](example_table.py) cria as colunas `Funcionario`, `Cargo`, `Idade` e `Genero`, adiciona sete registros e configura alinhamentos por coluna.

As chamadas comentadas mostram como imprimir a tabela em etapas, selecionar colunas, recortar linhas e ordenar registros. Ao final, o script define `tabela.sortby = None` e imprime a tabela; a ordenação por funcionário demonstrada anteriormente não fica ativa na impressão final.

## Como executar

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Explorando-bibliotecas-em-Python/tables_in_terminal"
python -m pip install prettytable
python example_table.py
```

## Resultado e experimentação

A tabela aparece no terminal. Os dados estão definidos no próprio script, sem arquivos de entrada ou saída. Descomente as chamadas de `print()` para comparar cada etapa ou altere os registros, alinhamentos, `sortby` e `reversesort` para explorar a formatação.

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

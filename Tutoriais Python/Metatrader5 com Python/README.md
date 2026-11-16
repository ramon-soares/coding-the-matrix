# MetaTrader 5 com Python: backtest de Bandas de Bollinger

Notebook que coleta cotações diárias via MetaTrader 5 e simula uma estratégia de compra baseada em Bandas de Bollinger. O código usa o terminal para obter dados e calcula as operações localmente.

## O que o notebook faz

O [metatrader_bollinger_bands.ipynb](metatrader_bollinger_bands.ipynb) conecta ao terminal, busca os últimos 365 dias de `PETR4`, `VALE3`, `ITUB4` e `BBDC4` e calcula bandas com média móvel de 20 períodos e dois desvios padrão.

Cada ativo é simulado separadamente com capital inicial de R$ 1.000. As regras implementadas são:

- **Entrada:** compra no fechamento quando ele está abaixo da banda inferior, usando todo o capital disponível.
- **Saída por stop:** se a mínima de um dia seguinte atingir 5% abaixo da entrada, encerra pelo preço do stop.
- **Saída pela banda:** se não houver stop e a máxima atingir a banda superior, encerra pelo valor dessa banda.
- **Fim da série:** uma posição ainda aberta é encerrada pelo último fechamento.

Quando stop e banda superior são atingidos no mesmo dia, a condição do stop é verificada primeiro. O capital é reutilizado na próxima operação do mesmo ativo.

## Preparação e execução

O ambiente do exemplo requer Windows com o terminal MetaTrader 5 instalado, conectado a uma conta que disponibilize o histórico dos ativos consultados.

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Tutoriais Python/Metatrader5 com Python"
python -m pip install notebook MetaTrader5 pandas numpy matplotlib seaborn
python -m notebook "metatrader_bollinger_bands.ipynb"
```

Abra o terminal MetaTrader 5 antes de executar as células. Confira os nomes dos símbolos usados pela sua fonte de dados e ajuste `symbols` se necessário. O notebook chama `mt5.initialize()` sem informar um caminho explícito de instalação ou credenciais.

Execute as células em ordem e finalize com `mt5.shutdown()`, presente no notebook. O código não contém chamadas de envio de ordens.

## Saídas

Os resultados aparecem no notebook: tabela de operações por ativo, gráficos de evolução do capital e um resumo com capital final, quantidade de operações, retorno total, retorno médio e taxa de acerto. Não há exportação automática para CSV ou imagens.

O intervalo é calculado a partir de `datetime.now()`, portanto muda a cada execução. As saídas já salvas representam a execução original.

## Particularidades do exemplo

O backtest não considera custos, impostos, slippage, lotes inteiros ou restrições de execução. A curva mantém o capital registrado entre encerramentos de operações, sem atualizar diariamente o valor da posição aberta. As bandas do próprio dia são usadas nos critérios; a simulação não reconstrói a sequência intradiária dos preços.

O estilo `seaborn-darkgrid` está escrito no código, e a saída salva registra um aviso de depreciação do Matplotlib para esse nome. Se o estilo não estiver disponível no ambiente escolhido, ajuste a chamada de `plt.style.use()` para um estilo disponível.

As células que acessam `data['PETR4']` dependem de esse ativo ter sido carregado. Se ele não estiver disponível, ajuste essas consultas além da lista de símbolos. O material permite estudar coleta de dados, indicadores e simulação com essas simplificações.

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

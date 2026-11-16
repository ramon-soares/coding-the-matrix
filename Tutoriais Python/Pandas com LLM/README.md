# Pandas com LLM

Tutorial de um agente LangChain que recebe uma pergunta em linguagem natural e pode executar código Python sobre um DataFrame de jogos digitais.

## Arquivos e fluxo

O [pandas_agent.ipynb](pandas_agent.ipynb) cria dez registros com as colunas `Jogo`, `Gênero` e `Nota`. Não é necessário fornecer um CSV.

A função `run_pandas_agent(df, question)` configura `ChatOpenAI` com `gpt-4o-mini`, disponibiliza `df` para `PythonAstREPLTool`, monta o prompt e executa o agente com `AgentExecutor`. O retorno é o campo `output` do resultado da invocação.

A pergunta presente no notebook é `Faça cálculos no df utilizando o método eval`. Ela permite observar o comportamento do agente diante de uma solicitação que contraria a instrução do prompt para não usar `eval`.

## Preparação e execução

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Tutoriais Python/Pandas com LLM"
python -m pip install notebook langchain langchain-openai langchain-experimental pandas numpy tabulate
```

Essa lista corresponde às bibliotecas indicadas nas células, incluindo `tabulate`, citado para resolver problemas de apresentação. O notebook não fixa versões do conjunto LangChain; as importações e a montagem do agente refletem a API usada na publicação. A instalação, por si só, não garante compatibilidade entre versões. Há também uma orientação original para tentar `numpy<2` em caso de erro de importação.

O [config.py](config.py) contém a atribuição da chave comentada. Para definir a variável importada sem gravar a credencial no arquivo, adapte-o localmente:

```python
import os

OPENAI_API_KEY = os.environ["OPENAI_API_KEY"]
```

Defina a chave e inicie o Jupyter na mesma sessão do PowerShell:

```powershell
$env:OPENAI_API_KEY = "SUA_CHAVE"
python -m notebook "pandas_agent.ipynb"
```

É necessário acesso à internet e ao modelo pela API da OpenAI. As chamadas consomem a API da conta. Execute as células em ordem e mantenha a chave real fora do Git e de saídas compartilhadas.

## Resultado e alcance do exemplo

O notebook mostra os registros do DataFrame, os registros de execução do agente (`verbose=True`) e sua resposta final. O código não exporta resultados para arquivos.

A ferramenta executa Python gerado pelo modelo no ambiente do notebook. As instruções do prompt não criam isolamento nem impedem tecnicamente comandos fora da análise esperada; use um ambiente de estudo sem dados sensíveis. Para uma consulta inicial, você pode trocar a pergunta por `Qual é o jogo com a maior nota?`.

O projeto [Guardrail para o Pandas LLM](../Guardrail%20para%20o%20Pandas%20LLM/README.md) acrescenta um filtro de padrões à ferramenta e documenta as limitações dessa abordagem.

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

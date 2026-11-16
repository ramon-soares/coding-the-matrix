# Guardrail para um agente Pandas com LLM

Continuação do exemplo [Pandas com LLM](../Pandas%20com%20LLM/README.md), acrescentando uma verificação de padrões ao código recebido pela ferramenta Python do agente.

## Como funciona

O [guardrail_with_pandas_llm.ipynb](guardrail_with_pandas_llm.ipynb) cria um DataFrame de dez jogos, com gênero e nota, e define `SafePythonAstREPLTool`, uma subclasse de `PythonAstREPLTool`.

A classe sobrescreve `run()`, procura expressões regulares no texto recebido e lança `ToolException` quando encontra um padrão bloqueado. A lista inclui chamadas a `eval`, `exec` e `open`, importações de `os` e `sys`, além de termos como `subprocess`, `shutil`, `pip` e `conda`.

O agente usa `gpt-4o-mini` e começa com a pergunta `Qual é o jogo com a maior nota?`. Outra célula pede `import os` para verificar arquivos da pasta, demonstrando uma tentativa de acionar o bloqueio.

## Preparação e execução

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Tutoriais Python/Guardrail para o Pandas LLM"
python -m pip install notebook langchain langchain-openai langchain-experimental pandas numpy tabulate
```

Os pacotes seguem as indicações das células. Não há versões fixadas para o conjunto LangChain; as importações, a construção do agente e a integração da ferramenta precisam de versões compatíveis com o exemplo. O notebook cita `numpy<2` como tentativa em caso de erro de importação e a atualização de `tabulate` para apresentação.

O [config.py](config.py) tem apenas uma atribuição de chave comentada. Defina a variável importada; uma opção local para carregar a chave do ambiente é:

```python
import os

OPENAI_API_KEY = os.environ["OPENAI_API_KEY"]
```

Na mesma sessão do PowerShell em que iniciará o notebook:

```powershell
$env:OPENAI_API_KEY = "SUA_CHAVE"
python -m notebook "guardrail_with_pandas_llm.ipynb"
```

Tenha conexão com a internet e acesso ao modelo na API da OpenAI. As chamadas consomem a API da conta. Execute as células em ordem, mantendo credenciais fora do Git e de saídas compartilhadas.

## Resultado e limites do guardrail

Na consulta de maior nota, os dados apontam para **Red Dead Redemption 2**, com **9,9**. A resposta do agente depende da execução e do modelo. Se o código enviado à ferramenta contiver um padrão listado, a implementação lança uma exceção; a última célula não envolve a chamada em `try/except`, portanto ela pode terminar com erro no notebook.

O filtro é uma demonstração de bloqueio por texto. Ele não cria um sandbox: padrões podem deixar de detectar outras formas de executar a mesma operação ou bloquear textos que não representam uma ação perigosa. A proteção também depende de o fluxo de execução do LangChain passar pelo método sobrescrito. Execute em um ambiente de estudo sem dados sensíveis e não trate a lista como uma garantia de segurança.

Os resultados e registros de execução aparecem no notebook, sem exportação automática. Para estudar o filtro, altere a pergunta ou examine `blocked_patterns` e `_is_malicious()`.

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

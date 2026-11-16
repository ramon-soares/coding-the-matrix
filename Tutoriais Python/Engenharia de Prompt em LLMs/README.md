# Engenharia de prompt em LLMs

Tutorial de construção de um prompt para classificar sentimentos de feedbacks em positivo, negativo ou neutro e extrair a classificação de uma resposta do modelo.

## O que o exemplo demonstra

O [prompt_engineering.ipynb](prompt_engineering.ipynb) apresenta um pedido simples em texto e depois executa uma versão estruturada: define o papel `FeedbackClassifier`, fornece instruções, inclui um exemplo e pede a classificação dentro de `<response>...</response>`.

A função `chat()` usa o SDK da OpenAI com Chat Completions e o modelo `gpt-4o-mini`. Na chamada de classificação, a temperatura é `0.1`. A função `extract_response_content()` usa uma expressão regular para extrair o conteúdo da tag e retorna `None` se ela não for encontrada.

## Preparação e execução

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Tutoriais Python/Engenharia de Prompt em LLMs"
python -m pip install notebook "openai==1.77"
```

A versão do SDK é a indicada no notebook. Tenha uma chave de API da OpenAI com acesso ao modelo e conexão com a internet; a execução consome a API da conta utilizada.

O [config.py](config.py) original contém a atribuição da chave comentada. Antes de importar, defina `OPENAI_API_KEY` nesse módulo. Para carregá-la do ambiente sem gravar a credencial no código, use localmente:

```python
import os

OPENAI_API_KEY = os.environ["OPENAI_API_KEY"]
```

Na mesma sessão do PowerShell que iniciará o Jupyter:

```powershell
$env:OPENAI_API_KEY = "SUA_CHAVE"
python -m notebook "prompt_engineering.ipynb"
```

Execute as células em ordem e mantenha a chave real fora do Git e das saídas compartilhadas. A biblioteca `re`, usada na extração, faz parte do Python.

## Resultado e limitações

A saída mostra a resposta para o feedback `Achei que não fez muita diferença, mas ok` e, em seguida, o texto extraído da tag. Não há exportação de arquivos.

O formato solicitado no prompt não é validado como um esquema: a expressão regular procura a primeira tag correspondente, mas não confere se o sentimento pertence às três categorias. O notebook também não executa uma comparação automática entre o pedido simples e o estruturado. Para experimentar, altere o feedback, as instruções e o exemplo fornecido ao modelo.

Veja também a [introdução à chamada da API](../Como%20usar%20API%20Chat%20GPT/README.md).

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

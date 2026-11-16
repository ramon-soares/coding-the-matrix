# Como usar a API do ChatGPT com Python

Tutorial de chamada à API da OpenAI usando o SDK Python. O exemplo envia uma frase ao modelo e pede que ele retorne as palavras mais importantes.

## Arquivos e funcionamento

| Arquivo | Papel |
| --- | --- |
| [api_gpt.ipynb](api_gpt.ipynb) | Tutorial com a função `chat()` e uma chamada de exemplo |
| [config.py](config.py) | Origem da variável `OPENAI_API_KEY` importada pelo notebook |

A função `chat(system_prompt, prompt, model, temperature, max_tokens)` cria um cliente `openai.OpenAI` e usa `client.chat.completions.create()` com mensagens `system` e `user`. Os valores padrão do código são `gpt-4o-mini`, temperatura `0.7` e limite de `512` tokens.

## Preparação e execução

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Tutoriais Python/Como usar API Chat GPT"
python -m pip install notebook "openai==1.77"
```

A versão do SDK reproduz a indicação do notebook. É necessário acesso à internet e uma chave de API com acesso ao modelo configurado. As chamadas consomem a API da conta utilizada.

O `config.py` incluído contém apenas `OPENAI_API_KEY = 'teste'`, que é um marcador. Para usar uma variável de ambiente, adapte o arquivo local para:

```python
import os

OPENAI_API_KEY = os.environ["OPENAI_API_KEY"]
```

Defina a variável na sessão do PowerShell e inicie o notebook nessa mesma sessão:

```powershell
$env:OPENAI_API_KEY = "SUA_CHAVE"
python -m notebook "api_gpt.ipynb"
```

Substitua o marcador somente no ambiente local e mantenha a credencial fora de arquivos versionados e de saídas compartilhadas. Execute as células em ordem.

## Resultado e personalização

O notebook imprime `result.choices[0].message.content`, com as palavras selecionadas para a frase sobre Python. A resposta é gerada pelo modelo e pode variar; não há arquivo de saída.

Altere os prompts ou os parâmetros da função para experimentar. O exemplo preserva a API e o modelo escolhidos para a publicação; a reprodução depende de acesso ao modelo e compatibilidade do ambiente, sem migração automática de SDK.

Para estudar a estruturação do prompt, veja [Engenharia de prompt em LLMs](../Engenharia%20de%20Prompt%20em%20LLMs/README.md).

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

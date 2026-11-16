# Codando a Matrix

Acervo de códigos e notebooks dos conteúdos já publicados no canal [Codando a Matrix no YouTube](https://www.youtube.com/channel/UCP0U3a18twMWqj8VaeCLEiw).

O repositório reúne exemplos curtos e tutoriais em Python para consulta, estudo e experimentação. Cada pasta principal representa um ambiente de conteúdo; dentro dela, cada subpasta contém um projeto independente.

## Explore o acervo

| Ambiente | Conteúdo | Projetos |
| --- | --- | --- |
| [Explorando bibliotecas em Python](Explorando-bibliotecas-em-Python/README.md) | Gráficos, imagens, tradução, tabelas, widgets e áudio | 7 |
| [Instagram](Instagram/README.md) | Grafos, arte ASCII e automação de teclado | 3 |
| [Programação em 1 minuto](Programa%C3%A7%C3%A3o-em-1-minuto/README.md) | Demonstrações rápidas de bibliotecas | 3 |
| [Tutoriais Python](Tutoriais%20Python/README.md) | Laços, APIs, LLMs, agentes e backtest | 6 |

Os índices de cada ambiente levam aos READMEs dos 19 projetos, com descrição, arquivos, dependências, execução e resultado esperado.

## Como usar

Você pode navegar pelos arquivos e pelas saídas salvas dos notebooks no GitHub. Para experimentar localmente, use Python 3 e siga o README do projeto escolhido.

Os comandos `cd` dos READMEs de projetos partem da raiz deste repositório. Execute o código de dentro da pasta do projeto: vários exemplos usam caminhos relativos para imagens, dados e configurações.

Para manter as dependências separadas, crie um ambiente virtual dentro da pasta do projeto. No PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

Em Linux ou macOS, a ativação é `source .venv/bin/activate`. Depois, instale os pacotes indicados no README correspondente. Alguns exemplos usam recursos específicos do Windows.

Para notebooks, os comandos documentados instalam e iniciam o Jupyter. Abra o arquivo `.ipynb`, selecione o kernel do ambiente em que instalou as dependências e execute as células na ordem. Células de instalação já presentes no notebook podem ser puladas se os pacotes estiverem instalados.

## Sobre os exemplos

Os códigos foram preservados como material das publicações. Não há um ambiente único nem um conjunto de versões fixadas para todo o acervo. Quando o código indica uma versão de biblioteca, ela é registrada na documentação como referência do exemplo; os comandos não representam uma validação de compatibilidade com todas as versões de Python e sistemas operacionais.

Alguns projetos precisam de internet, chave de API, aplicativos externos ou ajustes para reproduzir o ambiente original. Os READMEs descrevem esses requisitos e os pontos de atenção identificados no código. Credenciais reais devem permanecer fora do histórico Git.

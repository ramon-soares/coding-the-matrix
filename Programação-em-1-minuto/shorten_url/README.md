# Encurtar uma URL com Python

Exemplo de uso do pyshorteners para gerar um link curto pelo serviço TinyURL.

## Como funciona

O [shorten.py](shorten.py) define uma URL, cria `pyshorteners.Shortener()`, chama `link.tinyurl.short(url)` e imprime o endereço retornado. A URL usada no exemplo é a página do próprio pacote no PyPI.

## Como executar

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Programação-em-1-minuto/shorten_url"
python -m pip install pyshorteners
python shorten.py
```

É necessário acesso à internet para enviar a URL ao TinyURL.

## Resultado e personalização

O link encurtado aparece no terminal. Não há entrada interativa nem gravação de arquivos. Altere a variável `url` para encurtar outro endereço.

O resultado depende da resposta do serviço externo; o script não implementa tratamento de falhas de rede ou do provedor.

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

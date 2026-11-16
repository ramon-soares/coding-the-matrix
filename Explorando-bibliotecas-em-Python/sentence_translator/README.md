# Tradutor de frases

Exemplo de tradução de texto no terminal com `googletrans`, organizado na classe `Tradutor`.

## Como funciona

O [sentence_translator.py](sentence_translator.py) pede uma frase, cria `Tradutor(sentenca, "en")` e imprime o texto original e a tradução para inglês. O idioma de origem não é especificado no código. O método `traduzir()` retorna o texto traduzido; `mostrar_traducao()` apresenta o resultado no terminal.

## Como executar

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Explorando-bibliotecas-em-Python/sentence_translator"
python -m pip install "googletrans==3.1.0a0"
python sentence_translator.py
```

Digite uma frase quando aparecer `Digite uma frase:`. O exemplo requer internet e não grava arquivos.

## Personalização e limitações

Para mudar o destino, altere `"en"` na criação do objeto para o código do idioma desejado. A versão `3.1.0a0` é a indicada no próprio script. O funcionamento depende do serviço externo acessado pelo googletrans; o código não implementa tratamento de falhas de conexão ou de tradução.

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

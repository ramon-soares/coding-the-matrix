# Converter imagens para tons de cinza

Exemplo curto de processamento de imagens com Pillow: abre uma foto, converte para tons de cinza e salva o resultado.

## Arquivos

| Arquivo | Papel |
| --- | --- |
| [transform_bw.py](transform_bw.py) | Script de conversão |
| [torre.jpg](torre.jpg) | Imagem de entrada |
| [torre_transformada.jpg](torre_transformada.jpg) | Resultado de exemplo já incluído no acervo |

## Como executar

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Explorando-bibliotecas-em-Python/greyscale_images"
python -m pip install Pillow
python transform_bw.py
```

O script lê `torre.jpg`, aplica `convert("L")`, grava `torre_transformada.jpg` e solicita a abertura da imagem no visualizador do sistema. A conversão produz tons de cinza, sem aplicar um limiar para transformar a imagem em apenas preto e branco.

## Resultado e personalização

A execução substitui o arquivo `torre_transformada.jpg` existente. Para usar outra foto ou preservar o resultado incluído, altere os nomes nos métodos `Image.open()` e `save()`. A exibição por `show()` depende de um ambiente gráfico com visualizador de imagens.

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

# Rotacionar uma imagem com Pillow

Exemplo curto de abertura, rotação e exibição de uma imagem em Python.

## Arquivos e funcionamento

O [rotate.py](rotate.py) lê a imagem [torre_bw.jpg](torre_bw.jpg) com `Image.open()`, aplica `rotate(90)` e abre o resultado com `show()`. A rotação é de 90 graus no sentido anti-horário.

## Como executar

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Programação-em-1-minuto/rotate_image"
python -m pip install Pillow
python rotate.py
```

Mantenha `torre_bw.jpg` na pasta do script. A exibição depende de um ambiente gráfico com visualizador de imagens.

## Resultado e personalização

O script mostra a imagem rotacionada e não salva um novo arquivo. Para experimentar, altere o ângulo em `rotate(90)` ou o nome da imagem de entrada. Como a chamada não usa `expand=True`, a área de saída mantém as dimensões originais e pode cortar partes da imagem após a rotação.

Veja também o exemplo de [conversão para tons de cinza](../../Explorando-bibliotecas-em-Python/greyscale_images/README.md).

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

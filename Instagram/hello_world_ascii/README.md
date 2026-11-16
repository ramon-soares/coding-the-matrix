# Hello World em ASCII com cores

Uma comparação entre o tradicional `print('Hello World')` e uma versão em arte ASCII com cores alternadas no terminal.

## Arquivos

| Arquivo | Papel |
| --- | --- |
| [main_simple_hw.py](main_simple_hw.py) | Imprime uma linha com `Hello World` |
| [main_hw.py](main_hw.py) | Renderiza o texto com pyfiglet e alterna cores ANSI |
| [Readme.txt](Readme.txt) | Texto original da publicação |

O exemplo usa a fonte `big` do pyfiglet. Um laço infinito percorre 16 códigos de cor, limpa o console e redesenha o texto a cada segundo.

## Como executar

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Instagram/hello_world_ascii"
python -m pip install pyfiglet
python main_simple_hw.py
python main_hw.py
```

Interrompa a animação com `Ctrl+C`.

## Personalização e ambiente

Altere `banner` para mudar o texto, `font='big'` para escolher outra fonte, `colors` para selecionar cores ou `sleep(1)` para ajustar o intervalo. O terminal precisa interpretar sequências ANSI para exibir as cores.

O script usa `os.system('cls')`, comando de limpeza do Windows. Em Linux ou macOS, adapte essa chamada para `clear`. Não há leitura nem gravação de arquivos durante a execução.

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

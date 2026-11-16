# Automação de digitação com PyAutoGUI

Exemplo de controle do teclado com PyAutoGUI, preservado na pasta original `spam_bot`. O script lê um texto local e digita suas linhas na janela que estiver com foco.

## Arquivos e comportamento

| Arquivo | Papel |
| --- | --- |
| [spam_bot.py](spam_bot.py) | Rotina de leitura e digitação |
| [py_wiki](py_wiki) | Texto de entrada sobre Python, sem extensão |
| [readme.txt](readme.txt) | Descrição original |

Após esperar três segundos, o script abre `py_wiki` e percorre o arquivo linha a linha. Apesar do nome da variável `palavra`, cada item lido é uma linha inteira. Para cada linha, chama `typewrite()`, pressiona `Enter` e espera 0,25 segundo.

## Como executar em uma janela de teste

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Instagram/spam_bot"
python -m pip install pyautogui
python spam_bot.py
```

Antes de iniciar, deixe um editor de texto local aberto. Use os três segundos iniciais para colocar o foco no documento de teste: a rotina digita e pressiona `Enter` na janela ativa, sem selecionar o destino por conta própria.

## Resultado e personalização

O resultado aparece no editor escolhido. O script não gera um arquivo de saída nem acessa uma rede social diretamente. Ao terminar de percorrer `py_wiki`, a execução acaba.

Altere o conteúdo de `py_wiki`, os intervalos de `sleep()` ou o nome do arquivo passado a `open()` para experimentar. Execute na pasta do projeto e em uma sessão gráfica com permissão para controlar o teclado. Para interromper pelo terminal, retorne a ele e use `Ctrl+C`; o fail-safe padrão do PyAutoGUI também não foi desativado no código.

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

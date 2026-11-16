# Barra de progresso em um laço

Exemplo de como acompanhar a execução de um `for` com uma barra de progresso da biblioteca tqdm.

## Como funciona

O [example_progress_bar.py](example_progress_bar.py) envolve `range(50)` com `tqdm()`. Em cada iteração, `sleep(0.05)` simula uma tarefa com duração de 50 milissegundos.

## Como executar

Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório:

```powershell
cd "Programação-em-1-minuto/progress_bar_in_loop"
python -m pip install tqdm
python example_progress_bar.py
```

## Resultado e experimentação

O terminal mostra a evolução de 0 a 50 iterações. O exemplo dura cerca de 2,5 segundos, além do tempo de inicialização, e não cria arquivos.

Altere `range(50)` para mudar a quantidade de passos ou substitua `sleep()` pela operação que deseja acompanhar.

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

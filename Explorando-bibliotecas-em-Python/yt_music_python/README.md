# Áudio do YouTube em MP3

Exemplo de download de uma faixa de áudio com pytube e conversão para MP3 com MoviePy.

## Como funciona

O [yt_music_download.py](yt_music_download.py) solicita uma URL, seleciona a stream de áudio com `get_audio_only()`, faz o download na pasta `mp4` e usa `AudioFileClip` para converter o arquivo para a pasta `mp3`. Ao final, pergunta se o arquivo intermediário deve ser apagado.

O [readme.txt](readme.txt) original foi mantido como parte do acervo.

## Como executar

O script monta caminhos com barras invertidas, seguindo o ambiente Windows do exemplo. Com Python 3 e um ambiente virtual ativo, partindo da raiz do repositório, execute no PowerShell:

```powershell
cd "Explorando-bibliotecas-em-Python/yt_music_python"
python -m pip install pytube "moviepy==1.0.2" "imageio-ffmpeg==0.2.0"
New-Item -ItemType Directory -Force -Path mp4, mp3
python yt_music_download.py
```

Informe a URL no prompt `URL:`. Quando aparecer `Deletar mp4? (S/N):`, responda `S` para remover o intermediário ou `N` para mantê-lo. É necessário acesso à internet e disponibilidade do FFmpeg usado na conversão.

## Saídas e limitações

O resultado esperado é `mp3/<título>.mp3`, com um intermediário em `mp4/<título>.mp4`. As versões de MoviePy e imageio-ffmpeg acima são as indicadas nos comentários do script.

O código presume que o nome baixado corresponde ao título da stream acrescido de `.mp4`. Caracteres ajustados no nome pelo downloader ou outro formato de stream podem exigir correção do caminho antes da conversão. O download também depende da compatibilidade do pytube com o serviço externo.

[Voltar ao ambiente](../README.md) · [Acervo](../../README.md)

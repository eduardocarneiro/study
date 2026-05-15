



4. **Automatizar: Converter e Dividir de uma vez**
Se você quer converter um arquivo grande para um formato menor e depois parti-lo, use um pequeno script ou combine os comandos.

**Exemplo:** Converter m4a para mp3 (compressão) e dividir em arquivos de 10 minutos:
```bash 
ffmpeg -i entrada.m4a -c:a libmp3lame -b:a 96k -f segment -segment_time 600 -c:a libmp3lame parte_%03d.mp3

```


**reference:**
A melhor ferramenta no Linux para converter e dividir áudios via terminal é o ==**[FFmpeg](https://www.ffmpeg.org/)**==. Ele é eficiente, rápido e permite reduzir o tamanho do arquivo ajustando a taxa de bits (bitrate) ou mudando o formato. [[1](https://www.youtube.com/watch?v=UJsoeMwjkJg), [2](https://uniconverter.wondershare.com.br/compress/compress-m4a.html), [3](https://plus.diolinux.com.br/t/conversor-de-video-para-linux-mint/55097), [4](https://www.youtube.com/watch?v=fn9WQ7k3C1w&t=39)]



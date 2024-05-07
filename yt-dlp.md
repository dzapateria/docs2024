
# Manual de yt-dlp

Descargar video en máxima calidad en códec AV1
```
yt-dlp -S "+codec:av01" https://youtu.be/a6VVrAZUnsc
```

## 2. LISTAR LOS CONTENIDOS DE UN VIDEO
```
yt-dlp -F <URL>
``` 
![](https://content.codecademy.com/courses/learn-cpp/community-challenge/highfive.gif)



### 3.1 NOMBRE DEL ARCHIVO DE SALIDA


Especificar un nombre manualmente:
```
yt-dlp -o salida https://youtu.be/a6VVrAZUnsc
```
Esto creará un archivo llamado `salida.webm`

Podemos automatizar el nombrado de la salida con la información que nos aporta el video, aqui algunos ejemplos:


| Variable        | Información         | Ejemplo                                | Resultado                 |
| --------------- | ------------------- | -------------------------------------- | ------------------------- |
| %(title)s       | Título              | yt-dlp -o "%(title)s" <URL>            | titulo.webm               |
| %(resolution)s  | resolución          | yt-dlp -o "%(title)s" <URL>            | 1920x720.webm             |
| $(date + )      | Fecha/Hora descarga | yt-dlp -o $(date +%Y.%m.%d_[%H.%M.%S]) | 2024.05.07_[02.16.37].mp4 |
| %(duration > )s | Duración del video  | yt-dlp -o %(duration>%Hh%Mm%Ss)s       | 00h01m37s.mp4             |
| %(channel)s     | Nombre del canal    | yt-dlp -o "%(channel)s" <URL>          | mtv.mp4                   |
| %(width)s       | Anchura del video   | yt-dlp -o "%(width)s" <URL>            | 1920.mp4                  |
| %(height)s      | Altura del video    | yt-dlp -o "%(height)s" <URL>           | 1080.mp4                  |
| %(ext)s         | Extensión           | yt-dlp -o "%(title)s".%(ext)s          | titulo.web                |

### 3.2 OPCIONES ADICIONALES

| opción                | Descripción                                                           |
| --------------------- | --------------------------------------------------------------------- |
| -- restrict-filenames | Evitará que los simbolos o emojis en el título pueda causar problemas |
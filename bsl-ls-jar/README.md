# BSL Language Server для проверки кода 1С в Claude

Копия `bsl-language-server-1.1.0-rc.9-exec.jar` из https://github.com/1c-syntax/bsl-language-server/releases (лицензия LGPL-3.0, авторы — сообщество 1c-syntax), разрезанная на части меньше 50 МБ, чтобы поместиться в git (лимит GitHub — 100 МБ на файл).

Собрать обратно:

```
cat bsl-language-server-1.1.0-rc.9-exec.jar.part* > bsl-language-server-1.1.0-rc.9-exec.jar
sha256sum -c SHA256
```

Windows (cmd):

```
copy /b bsl-language-server-1.1.0-rc.9-exec.jar.part00+bsl-language-server-1.1.0-rc.9-exec.jar.part01+bsl-language-server-1.1.0-rc.9-exec.jar.part02 bsl-language-server-1.1.0-rc.9-exec.jar
```

Запуск анализа:

```
java -jar bsl-language-server-1.1.0-rc.9-exec.jar --analyze --srcDir <папка с исходниками> --reporter json -o <папка отчёта> -q
```

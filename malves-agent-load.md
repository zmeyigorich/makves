# Сбор информации о папка с помощью MAKVES-агента

## Сбор данных о файлах в папке


### Требования для использования
+ Операционная система Windows 7+x64, Windows 2012+x64. Рекомендуемая Windows 10x64.1803+, Windows 2019x64
+ Права на чтение файлов из инспектируемых файлов и папок

### Запуск

Формат запуска

```

makves-agent.exe load_folder <folder> <output_file>

```

Пример запуска без выделения текста из папки

```
makves-agent.exe load_folder //<folder> <output_file>
```

Пример запуска без выделения текста из папки общего доступа

```
makves-agent.exe load_folder //server/share files.json
```


Пример запуска без выделения текста из всех папок общего доступа указанного компьютера

```

makves-agent.exe load_folder //server files.json

```


Пример запуска без выделения текста из нескольких папок общего доступа

```

makves-agent.exe load_folder //server/share;//server2/share files.json

```


Параметры:

| Имя         | Назначение                                                                   |
|-------------|------------------------------------------------------------------------------|
| folder      | Корневая папка(локальная или сетевая) или компьтер для сбора данных          |
| output_file | Имя файла результатов (нужно обязательно использовать расширение .json)      |


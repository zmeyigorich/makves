## Агент мониторинга папки с файлами Window EventLog

### Функционал 
+ Мониторинг папки с evtx-файлами и передача их на анализ в в плаьформу MAKVES по протоколу HTTP/HTTPS

### Требования для использования
+ Операционная система Windows 7+, Windows 2012+. Рекомендуемая Windows 10x64.1803+, Windows 2019x64
+ Windows PowerShell 5+, Рекомендуется Windows PowerShell 5.1

### Запуск

Запуск агента с передачей данных по протоколу HTTP
```
powershell.exe -ExecutionPolicy Bypass -Command "./folder-evtx-monitor.ps1" -url "http://10.0.0.10:8000" -user admin -pwd admin
```

Параметры:

| Имя         | Назначение                                      |
|-------------|-------------------------------------------------|
| folder | Имя папки с evtx-файлами (По-умолчанию C:\Windows\System32\winevt\Logs)                          |
| url | Адрес сервера                           |
| user | Пользователь                           |
| pwd | Пароль                           |



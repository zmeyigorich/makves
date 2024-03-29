## Сбор событий EventLog c удаленных рабочих станций

### Требования для использования
+ Операционная система Windows 7+, Windows 2012+. Рекомендуемая Windows 10x64.1803+, Windows 2019x64
+ Windows PowerShell 5+, Рекомендуется Windows PowerShell 5.1
+ Remote Server Administration Tools for Windows 10 (или другой для соответвующей версии ОС)
+ Права на чтение удаленного EventLog [Дополнительно](https://support.microsoft.com/ru-ru/help/323076/how-to-set-event-log-security-locally-or-by-using-group-policy)

### Запуск

Сбор всех типов событий с компьютера dc.acme.local
```
powershell.exe -ExecutionPolicy Bypass -Command "./export-events.ps1" -Computers dc.acme.local
```

Сбор всех типов событий (Logon/Logon) с компьютера dc.acme.local -Target Logon
```
powershell.exe -ExecutionPolicy Bypass -Command "./export-events.ps1" -Computers dc.acme.local
```


Параметры:

| Имя              | Назначение                                                                                                        |
|------------------|-------------------------------------------------------------------------------------------------------------------|
| computers        | Список компьютеров с которых необходимо собрать логи событий                                                      |
| target           | Типы собираемых событий                                                                                           |
| outfilename      | Имя файла с результатами                                                                                          |
| user             | [Необязательный] Имя пользователя под которым производится запрос. Если не заданно, то выводится диалог с запросом |
| pwd              | [Необязательный] Имя пользователя под которым производится запрос. Если не заданно, то выводится диалог с запросом |
| fwd              | [Необязательный] Имя журнала использованоого при форвардинге                                                     |
| start            | [Необязательный] Врема начиная с которого отбирать события. Формат:yyyyMMddHHmmss                                |
| count            | [По-умолчанию: 3000] количество выбираемых событий                                                               |



Типы событий:

| Имя              | Назначение                                                                                                       |
|------------------|------------------------------------------------------------------------------------------------------------------|
| All              | Все ниже перечисленные                                                                                           |
| Logon            | События авторизации                                                                                              |
| Service          | События управления службами                                                                                      |
| User             | События управления учетными данными пользователей                                                                |
| Computer         | События управления учетными данными компьютеров                                                                  |
| Clean            | События очистки журналов                                                                                         |
| File             | События работы пользователей с файлами                                                                           |
| MSSQL            | События Microsoft SQL Server                                                                                     |
| RAS              | События удаленного подключения пользователей                                                                     |
| USB              | События работы с USB устройствами                                                                                |
| Sysmon           | События от sysmon                                                                                                |
| TS               | События работы TerminalServices                                                                                  |

После запуска будет выведено окно логина на компьютер, нужно ввести логин-пароль пользователя имеющего право читать журналы событий


### Настройка журналирования файловых операций

https://www.varonis.com/blog/windows-file-system-auditing/

### Настройка аудита печати

https://mikefrobbins.com/2017/08/10/powershell-one-liner-to-audit-print-jobs-on-a-windows-based-print-server/

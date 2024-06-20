---
sidebar_label: 'Скачивание из MS Store'
sidebar_position: 1
title: ' Ошибка скачивания из MS Store:'
---

Большинство компов находятся под доменом в Синергии поэтому у них отлючено обновление и приложений и дравйверов, чтобы это исправить нужно выполнить следующие шаги:

1. Открыть **Powershell** от имени администратора.
2. Ввести команду:

```bash
Set-ItemProperty "REGISTRY::HKLM\Software\Policies\Microsoft\Windows\WindowsUpdate\AU"
```
3. Ввести команду:

```bash
UseWUserver
```

И указать значение:
```bash
-value 0
```

4. Перезапукаем сервис обновление введя команду:

```bash
Get-Service wuauserv | Restart-Service
```

## Чтобы отключить обновления:

Проделать те же шаги, что и при включении, но за одним исключением, после команды `UseWUserver`, нужно ввести значение:
```bash
-value 1
```
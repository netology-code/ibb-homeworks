# Краткое руководство по работе с терминалом

* [Введение](#введение)
* [Открытие терминала](#открытие-терминала)
	* [Linux](#linux)
	* [Mac](#mac)
	* [Windows (Git Bash)](#windows-git-bash)
	* [Windows (CMD/PowerShell)](#windows-cmdpowershell)
* [Пути](#пути)
* [Переменные окружения](#переменные-окружения)
* [Автодополнение](#автодополнение)
* [Ключевые команды](#ключевые-команды)
	* [Текущий рабочий каталог](#текущий-рабочий-каталог)
	* [Смена рабочего каталога](#смена-рабочего-каталога)
	* [Листинг каталога](#листинг-каталога)
	* [Создание файлов](#создание-файлов)
	* [Создание каталогов](#создание-каталогов)
	* [Перемещение файлов и каталогов](#перемещение-файлов-и-каталогов)
	* [Удаление файлов и каталогов](#удаление-файлов-и-каталогов)

## Введение

Данное краткое руководство демонстрирует основные команды в терминалах:
* Bash/Zsh (Linux/Mac)
* Git Bash (Windows)
* CMD (Windows)
* PowerShell (Windows)

Для удобства все команды будут приведены в трёх вариантах:
* Bash
* CMD
* PowerShell

>В Windows 10 для оболочки CMD также доступны команды из GNU CoreUtils (те, что используются в Bash). В данном руководстве, для обеспечения совместимости с Windows 7, мы их не будем использовать.

>Кроме того, PowerShell предоставляет полные имена команд и алиасы (псевдонимы). Алиасы чаще всего предлагают сокращённое именование команд. Именно их мы и будем для простоты рассматривать.

## Открытие терминала

Первая задача: открыть терминал сразу в нужном каталоге.

### Linux

В Linux достаточно щёлкнуть правой кнопкой мыши на каталоге и выбрать пункт меню `Open in Terminal` или `Открыть в терминале`:

![](pic/linux-open.png)

![](pic/linux-open-ru.png)


### Mac

В Mac всё немного сложнее, необходимо настроить отображение этого пункта меню в Finder.

Для этого необходимо перейти в `Системные настройки`, затем пункт меню `Клавиатура`, в разделе `Службы` выбрать раздел `Файлы и папки` и поставить флажок напротив `Новый терминал по адресу папки`:

![](pic/mac-settings.png)

![](pic/mac-services.png)


После чего при клике правой кнопкой мыши на каталоге появится необходимый пункт меню:

![](pic/mac-terminal.png)

### Windows (Git Bash)

В Windows всё достаточно просто, кликаете правой кнопкой мыши на каталоге и выбираете `Git Bash Here`:

![](pic/git-bash.png)

### Windows (CMD/PowerShell)

Если нужно открыть CMD/PowerShell, то при нажатой клавшие `Shift` кликаете правой кнопкой мыши на каталоге и выбираете `Оpen command window here` или `Open PowerShell window here` (в русскоязычной версии они должны называться `Открыть окно команд здесь` и `Открыть окно PowerShell здесь` соответственно):

![](pic/windows-cmd.png)


## Пути

Одно окно терминала подразумевает, что так же как в одном открытом окне `Nautilus`, `Finder` или проводника Windows вы можете в один момент времени находиться только в одном каталоге, который называется `Current Working Directory` (текущий каталог).

Вы можете выполнять команды относительно текущего каталога или относительно абсолютного пути.

Абсолютный путь — это путь, отсчитываемый от корня файловой системы. Корень файловой системы обозначается символом `/`. В Windows корень отсчитывается от диска, например, `C:\`.

> **Важно:** несмотря на то, что в Windows 10 командные оболочки нормально поддерживают `/` вместо `\ `, мы будем использовать для Windows синтаксис с `\ `.

Например, в Git Bash (Windows) абсолютный путь для каталога `Program Files`, будет чаще всего выглядеть следующим образом: `/c/Program Files/`, а в CMD: `C:\Program Files\ `

Для домашнего каталога в Ubuntu (Linux), абсолютный путь будет выглядеть следующим образом: `/home/user/`, где `user` — имя пользователя.

Bash (Git Bash в том числе) используют символ `/` для разделения каталогов. В Windows для этих же целей используется символ `\ `.

Ещё два специальных обозначения помимо корня файловой системы:
* `.` — обозначает текущий каталог
* `..` — обозначает родительский каталог

**Важно:** в терминале символ пробел является символом разделяющим команды и опции. Поэтому если в пути есть пробел, то варианта два:
1. Заключать путь в кавычки, т.е. `"Program Files"`
1. Использовать символ `backslash` для экранирования пробела: `Program\ Files` (Linux/Mac)

## Переменные окружения

Командная оболочка устанавливает ряд переменных, которые выполняют специфические функции. Так, переменная с именем `PATH` содержит список путей, в которых будет производиться поиск программы, если вы наберёте её название в терминале.

Для вывода содержимого конкретной переменной используется команда `echo`.

#### Вывод переменной окружения:
**Bash/Zsh**
```shell
$ echo $PATH
```
**CMD**
```shell
> echo %PATH%
```
**PowerShell**
```shell
> $Env:Path
```

## Автодополнение

В командных оболочках работает автодополнение по клавише `Tab`:
* дополняются имена команд
* дополняются пути

Используйте автодополнение, так как оно позволяет сократить время на набор команды.

## Ключевые команды

В этом разделе будут описаны ключевые команды, необходимые нам для работы. Естественно, список этот далеко не полный.

Примечание*: для PowerShell мы будем использовать "короткие" аналоги команд.

### Текущий рабочий каталог

`pwd` — сокращение от Print Working Directory.

#### Отображение текущего рабочего каталога:
**Bash/Zsh**
```shell
$ pwd
```
**CMD**
```shell
> cd
```
**PowerShell**
```shell
> pwd
> gl
```

### Смена рабочего каталога

`cd` — сокращение от Change Directory.

#### Переход в определённый каталог:
**Bash/Zsh**
```shell
$ cd <path>
```
**CMD**
```shell
> cd <path>
```
**PowerShell**
```shell
> cd <path>
```
`path` может быть как абсолютынм, так и относительным путём.

#### Перейти на каталог выше:
**Bash/Zsh**
```shell
$ cd ..
```
**CMD**
```shell
> cd ..
```
**PowerShell**
```shell
> cd ..
```

#### Перейти в подкаталог `src`:
**Bash/Zsh**
```shell
$ cd src
```
**CMD**
```shell
> cd src
```
**PowerShell**
```shell
> cd src
```

Если перед путём нет слэша — он трактуется как относительный (относительно текущего каталога). 

### Листинг каталога

`ls` — сокращение от List.

#### Отображение листинга (содержимого каталога):
**Bash/Zsh**
```shell
$ ls
```
**CMD**
```shell
> dir
```
**PowerShell**
```shell
> ls
> dir
```

По умолчанию, `ls` не отображает файлы, начинающиеся с `.`, например, `.gitignore`. Для отображения таких файлов нужно использовать флаг `-a`:
```shell
$ ls -a
```

### Создание файлов

Для создания файлов используются специальные программы (например, для создания текстовых файлов — текстовые редакторы).

### Создание каталогов

`mkdir` — сокращения от Make Directory.

Позволяет создавать каталоги (создаст каталог `tmp` в текущем каталоге):
```shell
$ mkdir tmp
```

В оболочках CMD и PowerShell описанный варианты команды `mkdir` работают аналогичным образом.

### Перемещение файлов и каталогов

`mv` — сокращение от Move.

#### Перемещение (переименование) файлов и каталогов:
**Bash/Zsh**
```shell
$ mv tmp temp
```
**CMD**
```shell
> move tmp temp
```
**PowerShell**
```shell
> mv tmp temp
> move tmp temp
```

### Удаление файлов и каталогов

`rm` — сокращение от Remove.

#### Удаление файла:
**Bash/Zsh**
```shell
$ rm README.txt
```
**CMD**
```shell
> del README.txt
```
**PowerShell**
```shell
> rm README.txt
> del README.txt
```

#### Удаление непустого каталога:
**Bash/Zsh**
```shell
$ rm -rf temp
```
Для удаление непустого каталога необходимо указать флаги:
* `-r` — удалять рекурсивно
* `-f` — не спрашивать подтверждения

**CMD**
```shell
> rd /S /Q temp
```
Для удаление непустого каталога необходимо указать флаги:
* `/S` — удалять рекурсивно все файлы и подкаталоги
* `/Q` — не спрашивать подтверждения

**PowerShell**
```shell
> rm -recurse -force temp
> rd -recurse -force temp
```
Для удаление непустого каталога необходимо указать флаги:
* `-recurse` — удалять рекурсивно все файлы и подкаталоги
* `-force` — включая скрытые и доступные только для чтения


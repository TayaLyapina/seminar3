# **Инструкция по работе с Git**

## Что такое Git

![Логотип](images/git.jpg)

Git - это консольная утилита, для отслеживания и ведения истории изменения файлов, в вашем проекте. Чаще всего его используют для кода, но можно и для других файлов.

С помощью Git-a вы можете откатить свой проект до более старой версии, сравнивать, анализировать или сливать свои изменения в репозиторий.

## Создание локального репозитория

Для того чтобы создать (инициализировать) локальный репозиторий необходимо в терминале, находясь в папке проекта набрать команду:
   
    git init

## Проверка состояния репозитория

Чтобы проверить состояние репозитория используют команду:

    git status
    
## Добавление файлов в репозитории

Добавить отдельный файл в область репозитория можно с помощью команды:

    git add имя файла

## Добавление всех файлов в репозитории

Для добавления всх файлов в репозитории используют флаг --all:

    git add --all

## Создание коммита

Для того чтобы зафиксировать текущее содержимое файла используют команду:

    git commit

Далее в текстовом редакторе откроется окно, в котором можно ввести подробное описание внесенного изменения. Оно может состоять из нескольких строк.

## Создание коммита с кратким описанием

При создании коммита в репозитории можно ввести однострочное сообщение. Для этого используют флаг -m. Само сообщение вводится непосредственно после флага в кавычках.

    git commit -m "Messege"

## Сохранение изменений во всех текущих файлах

Для сохраниния изменений во всех текущих файлах используется флаг -а. Новые файл при использовании данной команды не будут затронуты.

    git commit -a

## Сохранение изменений во всех текущих файлах с созданием сообщения

Если необходимо зафиксировать изменения во всех текущих файлах и создать однострочное сообщение используют команду:

    git commit -am

## Просмотр истории коммитов

Просматривать изменения внесенные в репозиторий можно с помощью команды:

    git log

## Просмотр краткой истории коммитов

Если не требуется выводить подробную информацию по каждому коммиту, можно воспользоваться сокращенным выводом с помощью флага --oneline. В результате каждый коммит выводится в одну строку.

    git log --oneline

## Просмотр краткой истории всех коммитов

Для просмотра всех коммитов внесенных в репозиторий, независимо от того в каком коммите вы в данный момент находитесь используют флаги --oneline и --all:

    git log --oneline --all

## Переключение между коммитами

Для переключения между коммитами используют команду:

    git checkout <название_ветки>

## Переключение на основную ветку

Для переключения на основную ветку используют команду:

    git checkout master

## Сравнение изменений

Для сравнения изменений между двумя коммитами используют следующую команду:

    git diff <первый_коммит> <второй_коммит>

## Ветвление

Если нужно добавить новую возможность или исправить ошибку (незначительную или серьезную), вы создаете новую ветку, в которой будут размещаться эти изменения. 

Используя ветвление, Вы отклоняетесь от основной линии разработки и продолжаете работу независимо от неё, не вмешиваясь в основную линию. Во многих СКВ создание веток — это очень затратный процесс, часто требующий создания новой копии каталога с исходным кодом, что может занять много времени для большого проекта.


### Отображение веток

Для отображения веток в репозитории используют команду:

    git branch

Команда отобразит все ветки и выделит текущуюю цветом и отметит звездочкой(*).

### Создание новой ветки

Для того чтобы создать новую ветку используют команду:

    git branch <new_branch>

Данная команда не выполняет переключения на новую только что созданную ветку. Вы остаетесь на той ветке, откуда выполняли команду.

### Удаление веток

Для удаления ветки используют команду:

    git branch -d <branch_name>

Это «безопасная» операция, поскольку Git не позволит удалить ветку, если в ней есть неслитые изменения.

## Слияние веток

Слияние используется в Git, чтобы собрать воедино разветвленную историю.

### Подготовка к слиянию

Выполните команду git status. Это позволит убедиться, что HEAD указывает на ветку, принимающую результаты слияния. При необходимости выполните команду git checkout <принимающая-ветка>, чтобы переключиться на принимающую ветку. Для примера выполним команду git checkout master.

Убедитесь, что в принимающей ветке и ветке для слияния содержатся последние изменения.

Только после этого можно переходить к слиянию.

### Выполнение слияния

После указанных выше действий можно переходить непосредственно к слиянию веток. Для этого необходимо выполнить команду:

    git merge <branch>

Где branch это ветка, которую необходимо влить в ветку master.

### Конфликты и их разрешение

При попытке объединить ветки, в которых изменена одна и та же часть того же файла, Git не сможет сделать выбор между версиями. В таком случае операция останавливается прямо перед созданием коммита слияния, чтобы пользователь вручную разрешил конфликты.

После обнаружения конфликтующих участков кода вы можете исправить их по своему усмотрению. 

Когда вы будете готовы завершить слияние, выполните команду git add для конфликтующего файла или файлов — так вы сообщите Git, что конфликт разрешен. Затем выполните обычную команду git commit, чтобы создать коммит слияния. 

## Удаленные репозитории

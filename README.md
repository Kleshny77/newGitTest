## __Гайд по иcпользованию _терминала_ и работе с _Git_ и _GitHub___
---
### __Работа с терминалом__
#### __Основные команды в терминале__  
1. `ls` выводит список файлов/директорий, которые есть в __текущей__ директории.  
2. `cd pathNewDirectory` позволяет сменить директорию на новую.
    - `_cd_ ~`меняет текущую директорию на домашнюю.
    - `cd /` меняет текущую директорию на корневую.
    - `cd ..` поднимается на одну директорию вверх.
3. `pwd` печатает директорию, в которой вы находитесь в данный момент.
4. `mkdir nameNewDirectory` создает новую директорию в текущей директории.
5. `touch nameNewFile` создание нового файла в текущей директории.
    - `touch nameNewFile1 nameNewFile1 nameNewFile1` создание нескольких новых файлов в текущей директории.
6. `cp nameFile nameNewDirectory` копирование файла в новую директорию.
7. `mv nameFile nameNewDirectory` перемещение файла в новую директорию.
8. `cat nameFile` печать содержимого файла.
9. `rm nameFile` удаление файла.
10. `rmdir nameDirectory` удаление директории.
11. `rm -r nameDirectory` удаление директории и всех файлов в ней.


#### __Полезные возможности__
1. `command1 && command2` выполнение нескольких команд в одну строку с помощью объединения ___&&___.
2. `↑ ↓` переключение между последними командами в терминале через стрелочки.
3. `tab` автозаполнение команды.

#### __Работа с SSH ключами__
1. `cd ~ && ls -la .ssh/` проверка наличия SSH ключей.
2. `ssh-keygen -t ed25519 -C "GitHubEmail"` генерация SSH ключа.
> `ssh-keygen -t rsa -b 4096 -C "GitHubEmail"` аналогичный вариант при ошибке первого. 
3. `ls -a ~/.ssh` вывод сгенерированного SSH ключа.
4. `pbcopy < ~/.ssh/id_rsa.pub` копирование содержимого ключа в буффер обмена.
> `pbcopy < ~/.ssh/id_ed25519.pub` аналогичный вариант при ошибке первого.  
> `cat ~/.ssh/id_rsa.pub` аналогичный вариант при ошибке первых двух. Надо будет скопировать вручную.
5. `ssh -T git@github.com` проверка правильности ключа.
---
### __Работа с Git__
#### __Основные команды в терминале__
1. `git version` показывает текущую версию Git, если он установлен.
2. `git config --global user.name "Name or nickname"` смена вашего имени в Git.
3. `git config --global user.email userEmail` смена вашего email в Git.
4. `cat ~/.gitconfig` вывод содержимого файла конфигурации Git.
5. `git init` создание репозитория в какой то конкретной директории.
6. `rm -rf .git` удаление репозитория в какой то конкретной директории.
    - `-r` (от англ. _recursive_ — «рекурсивно») удаляет директории вместе с файлами внутри.
    - `-f` (от англ. _force_ — «заставить») удаление вопросов уточнения (_Вы точно хотите удалить папку?_).
7. `git remote add origin "SSHKeyGitHub"` связь локального репозитория и удаленного.
8. `git remote -v` проверка связи локального репозитория с удаленным.
9. `git status` проверка статуса файлов в локальном репозитории.
10. `git add` подготовка файлов к сохранению.
    - `git add nameFile` подготовка одного файла в текущей директории к сохранению.
    - `git add .` подготовка всех файлов в текущей директории к сохранению. Не затрагивает удаленные файлы.
    - `git add --all` подготовка всей директории к сохранению, в том числе удаленные файлы.
11. `git commit -m "CommitText"` коммит изменений с информационным текстом.
    - `git commit --amend --no-edit` - добавление файла в последний коммит.
    - `git commit --amend -m "CommitNewText"` - изменение текста в последнем коммите.
12. `git push` отправка изменений на удаленный репозиторий.
    - `git push -u origin master` или `git push -u origin main` - если вы отправляете коммиты впервые.
13. `git log` просмотр истории коммитов.
    - `git log -oneline` - получить сокращенную историю коммитов одной строкой.
14. `git restore --staged <file>` - убрать файл из списка staged (после add).
    - `git restore --staged .` - убрать все файлы из списка staged (после add).
15. `  <commit hash>` - откат коммита.
16. `git restore <file>` - откат изменений в файле (modified).
17. `git diff` - позволяет посмотреть, что конкретно изменилось в файле (до add).
    - `git diff --staged` - позволяет посмотреть, что конкретно изменилось в файле (после add).
---

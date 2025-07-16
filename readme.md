##Установка на Ubuntu
sudo apt-get install git

##Установка на RedHat
sudo dnf install git

##Необходимо задать пару параметров:
git config --global user.name "Stanislav.Miller"
git config --global user.email "Stanislav.Miller@nces.by"

##Просмотр
git config -l

##Отслеживаем текущий каталог
git init .

##Что происходит, самая частая команда
git status

##Делаем снимок (коммит)
git add file
git add *
git commit -m "Initial commit, ver: 1.0"

##История коммитов
git log

##Просмотр одного (последнего) коммита и изменения
git log -1 -p

##Просмотр в одну строку
git log --pretty=oneline

##Восстанавливаем предыдущее состояние
git checkout -- file1.txt
git restore file1.txt

##Показать какие изменения будут записаны в лог
git diff --staged

##Для игнорирования файлов и каталогов создаем файл .gitignore, где указываем
*.txt
logs/
и т.п.

##Скачать репозиторий
git clone https://github.com/MillerStanislav/scripts.git

##Просмотр, какой репозиторий установлен
git remote -v

##Добавляем удаленный репозиторий
git remote add origin git@github.com:MillerStanislav/gitlesson1.git

##Меняем
git remote set-url origin git@github.com:MillerStanislav/scripts.git

##Загрузить на GitHub
git push origin

##ssh  аутентификация с GitHub
##копируем публичный ключ и вставляем на сайте: Settings -> SSH and GPG keys -> New SSH key
##Меняем git remote (смотри выше)

##Показать ветки
git branch

##Создать ветку
git branch fix_error

##Перейти на ветку
git checkout fix_error

##Удалить ветку
git branch -d fix_error

##Создать и перейти
git checkout -b fix_error

##Объединить ветки
git merge fix_error

##Перейти на определенный коммит (используем хеш коммита)
git checkout 3f4d35ca2b5f5a6f61010a35b26196d1455826b8
##возврат обратно на последний
git checkout master

##Изменить существующий коммит
git commit --amend

##Перейти на пару коммитов вниз и удалить верхние
git reset --hard HEAD~2

##Сохранить все изменения в файлах, но удалить коммиты
git reset --soft HEAD~4
##Для того чтобы запушить использовать
git push origin +master
##Еще варианты (не проверял): git merge origin/master и git rebase origin/master

##Добавление тегов
git tag v1.0.0
git push origin v1.0.0

##
# Робота з Git

**Git — це розподілена система контролю версій. **

Контроль версій дає змогу:
* Контролювати зміни, які внесені до програми
* Бачити історію всіх змін у програмі (хто, коли і що змінював), виконувати пошук у історії змін
* Значно зменшити ризик втратити змін через необережність чи помилку, а отже і зберегти виконану роботу
* Тримати кілька різних версій програми
* Ефективно працювати у команді з іншими розробниками над одним вихідним кодом програми

Звичайно, щоб отримати усі ці переваги, треба навчитися правильно   використовувати   Git.   Тут   ми   наведемо   лише   кілька прикладів роботи, та покрокову інструкцію щоб розпочати роботу з Git. Для повноцінної роботи з Git та розуміння усіх деталей ми рекомендуємо прочитати Git Magic (укр. переклад) [http://www-cs-students.stanford.edu/~blynn/gitmagic/intl/uk/](http://www-cs-students.stanford.edu/~blynn/gitmagic/intl/uk/).

## Встановлення
Для встановлення Git  на Windows  та  Mac OS X  достатньо скачати   інсталяційний   пакет   на   офіційному   сайті: [https://git-scm.com/downloads](https://git-scm.com/downloads).   
Для встановлення під Linux — скористайтеся пакетним менеджером: [https://git-scm.com/download/linux](https://git-scm.com/download/linux).

Під час встановлення (Windows) залиште налаштування за замовчуванням, як показано на малюнку.

![](https://media.githubusercontent.com/media/PLLUG/CPPQT-Roadmap/master/storage/book/development_basics/working_with_git/git-bash-setup.png) ![](https://media.githubusercontent.com/media/PLLUG/CPPQT-Roadmap/master/storage/book/development_basics/working_with_git/git-bash-setup2.png)

Після встановлення  відкрийте консоль (Linux та Mac OS). У Windows запустіть консоль з допомогою іконки **GitBash** (у головному меню). Виконайте команду  ```git --version```. Якщо встановлення пройшло успішно — ви побачите вивід з версією  Git.
```sh
alexchmykhalo@ThinkPad ~ % git --version
git version 2.5.3
```
Звичайно, ваша версія Git може відрізнятися. Але це не впливатиме на нашу роботу, оскільки  інструкції наведені тут працюватимуть зі всіма останніми версіями.

## Створюємо новий репозиторій

### Тека з проектом

Для початку — створіть теку, де ви будете тримати вихідні коди програм. Якщо ви вже маєте таку — теку перейдіть в неї. Для того, щоб навчитися працювати з командним рядком пройдіть: [http://cli.learncodethehardway.org/book/](Для початку — створіть теку, де ви будете тримати вихідні коди програм. Якщо ви вже маєте таку — теку перейдіть в неї.  Для того, щоб навчитися працювати з командним рядком пройдіть: http://cli.learncodethehardway.org/book/)

Кілька порад:
* У Windows виконайте команду ```explorer .```  (крапка після пробілу!) для того щоб відкрити перегляд поточної директорії у Windows.
* Для прикладу, якщо ви хочете перейти у Windows в директорію ```projects``` на диску ```D```, виконайте:  ```cd /d/projects```
* Активно використовуйте клавішу ```Tab```  у консолі для автозавершення команд, шляхів, параметрів  Git.

| Команда | Опис |
| -- | -- |
| ```pwd``` | Вивести поточну теку в якій працюємо |
| ```cd назва_теки``` | Перейти в іншу теку |
| ```mkdir назва_теки``` | Створити нову теку |
| ```rmdir назва_теки``` | Видалити пусту теку |
| ```ls``` | Переглянути список тек та файлів у поточній теці.|
| ```touch назва_файлу``` | Створити файл.|
| ```rm назва_файлу``` | Видалити файл.|


### Створюємо репозиторій

Для того щоб створити власний репозиторій — зареєструйтеся на GitHub: [https://github.com/](https://github.com/)

1. Залогінтеся, та зайдіть на головну сторінку GitHub.
2. Натисніть на конпку створення нового репозиторію. 
![](https://media.githubusercontent.com/media/PLLUG/CPPQT-Roadmap/master/storage/book/development_basics/working_with_git/github-new-repo.png)
3. Оберіть ім’я для репозиторію (*Repository name*).
![](https://media.githubusercontent.com/media/PLLUG/CPPQT-Roadmap/master/storage/book/development_basics/working_with_git/github-new-repo2.png)
4. При створенні нового репозиторію оберіть *“Initialize this repository with a README”*. Це ініціалізує репозиторій та дасть змогу одразу ж клонувати його.
  5. Скопіюйте адресу вашого нового репозаторію (наприклад: ```https://github.com/user/test-project.git```).             
![](https://media.githubusercontent.com/media/PLLUG/CPPQT-Roadmap/master/storage/book/development_basics/working_with_git/github-clone-repo.png)
6. Відкрийте консоль. Перейдіть у директорію де буде знаходитись ваш проект.
7. Виконайте команду git clone адреса репозиторію.
8. Перейдіть у теку репозиторія. Тепер можна розпочинати роботу.

```sh
% pwd
/home/user

% mkdir projects

% cd projects

% pwd
/home/user/projects

% git clone https://github.com/user/test-project.git
Cloning into 'test-project'...
remote: Counting objects: 3, done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
Checking connectivity... done.

% ls
test-project

% cd test-project 

% ls
README.md
```
У наведеному вище прикладі ми:
* Вивели поточну директорію
* Створили у поточній директорії нову теку з назвою projects
* Перейшли у теку projects
* Вивели поточну директорію ще раз для перевірки де ми знаходимось
* Клонували наш репозиторій Git
* Переглянули список директорій, щоб побачити, як називається директорія нашого Git  репозиторію
* Перейшли в теку репозиторію 
* Вивели список файлів у теці репозиторію


### Створення нового проекту
Для того щоб продемонструвати роботу з Git, звичайний С++ проект у Qt Creator.

При створенні, оберемо ту ж директорію, де знаходиться наш клонований репозиторій.  Для цього оберемо теку, куди ми клонували наш репозиторій (поле ```Create in```). А замість ім’я проекту, вкажемо ім’я теки репозиторію (поле ```Name:```). Таким чином QtCreator не буде створювати окрему директорію для проекту в середині директорії репозиторію. Для проекту буде використана тека нашого репозиторію і всі файли будуть додані всередину.

![](https://media.githubusercontent.com/media/PLLUG/CPPQT-Roadmap/master/storage/book/development_basics/working_with_git/new-project-already-exists.png)

### Заливаємо зміни на Git

Тепер відкриємо консоль та перевіримо статус репозиторію за допомогою команди ```git status```:
```sh
% git status
On branch master
Your branch is up-to-date with 'origin/master'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        main.cpp
        test-project.pro

nothing added to commit but untracked files present (use "git add" to track)
```
Ми бачимо, що ми маємо кілька файлів, які не є під контролем Git (*Untracked files*).  Додамо ці файли до наступного коміту з допомогою команди ```git add```:
```sh
% git add main.cpp test-project.pro 
% git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   main.cpp
        new file:   test-project.pro
```
Тепер ми бачимо, що файли з нашого проекту будуть додані до наступного коміту (*Changes to be committed*). 
Тепер ми зробити коміт з допомогою команди  ```git commit -m “коментар”```.
```sh
% git commit -m "Added project files."
[master 275127f] Added project files.
 3 files changed, 90 insertions(+)
 create mode 100644 main.cpp
 create mode 100644 test-project.pro
 ```
Для того, щоб завантажити (“залити”) зміни на GitHub (на віддалений репозиторій), виконаємо команду ```git push```. Під час виконання цієї команди вам необхідно буде ввести свій логін та пароль до GitHub.
```sh
% git push
Username for 'https://github.com': user
Password for 'https://user@github.com': 
Counting objects: 5, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 913 bytes | 0 bytes/s, done.
Total 5 (delta 0), reused 0 (delta 0)
To https://github.com/user/test-project.git
   fef3301..275127f  master -> master
```

###  Простий алгоритм для роботи з системою контролю версій (одна гілка, один розробник)
1. Клонуйте ваш репозиторій (```git clone адреса```).
2. Виконуйте необхідну роботу у середині теки репозиторію.
3. Перевірте статус репозиторію (```git status```) 
4. Додайте нові файли (```git add файл чи тека```), видаліть непотрібні файли (```git rm файл```) або додайте до коміту усі файли які були вже додані але є модифіковані (```git add -u```).
5. Перевірте статус репозиторію — які файли увійдуть до наступного коміту (```git status```).
6. Виконайте коміт. Додайте до коміта якісний коментар, який буде описувати ваші зміни. (```git commit -m “Коментар”```)

## Корисні посилання
* Креш курс роботи з командним рядком  Unix/Linux  [http://cli.learncodethehardway.org/book/](http://www-cs-students.stanford.edu/~blynn/gitmagic/intl/uk/)
* Git Magic (укр. переклад) [http://www-cs-students.stanford.edu/~blynn/gitmagic/intl/uk/](http://www-cs-students.stanford.edu/~blynn/gitmagic/intl/uk/)
* Visual Guide to Version Control [http://betterexplained.com/articles/a-visual-guide-to-version-control/](http://betterexplained.com/articles/a-visual-guide-to-version-control/)



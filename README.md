## Laboratornaya 2


** Chast 1**

1. Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).

2. Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.
`````sh
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/nixopn/lab02dzi.git
git push -u origin main
`````

`````sh
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint:
hint:   git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint:   git branch -m <name>
Initialized empty Git repository in /home/nixopn/nixopn/workspace/projects/lab02/.git/
[master (root-commit) dde68e2] added README.md
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 README.md
 Username for 'https://github.com': nixopn
Password for 'https://nixopn@github.com':
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 221 bytes | 221.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'master' on GitHub by visiting:
remote:      https://github.com/nixopn/lab02dzi/pull/new/master
remote:
To https://github.com/nixopn/lab02dzi.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
`````

3. Создайте файл hello_world.cpp в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу Hello world на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку using namespace std;.

`````sh
touch hello_world.cpp
`````

`````sh
#include<iostream>
using namespace std;
int main(){

cout<<"hello world!"<<endl;

    return 0;
}
`````

4. Добавьте этот файл в локальную копию репозитория.

`````sh
git add hello_world.cpp
`````

5. Закоммитьте изменения с осмысленным сообщением.

`````sh
git commit -m "Added initial version of hello_world.cpp with bad coding."
`````

`````sh
[main c4cdbc4] Added initial version of hello_world.cpp with bad coding.
 1 file changed, 8 insertions(+)
 create mode 100644 hello_world.cpp
`````

6. Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение Hello world from @name, где @name имя пользователя.

`````sh
#include<iostream>
#include<string>

using namespace std;

int main(){
	string name;
	cin>>name;
	cout<<"hello world from"<<name<<endl;
	return 0;
}
`````

7. Закоммитьте новую версию программы. Почему не надо добавлять файл повторно git add?

Потому что при использовании опции -a ("--all") в команде git commit, Git автоматически добавляет все измененные файлы в коммит, поэтому повторное явное добавление файлов не требуется.

`````sh
git commit -a -m "by name"
`````

`````sh
[main 0a13a5d] by name
 2 files changed, 13 insertions(+), 8 deletions(-)
`````

8. Запуште изменения в удалёный репозиторий.

`````sh
git push origin master
`````

`````sh
Username for 'https://github.com': nixopn
nixopn@github.com': //
Enumerating objects: 16, done.
Counting objects: 100% (16/16), done.
Delta compression using up to 8 threads
Compressing objects: 100% (14/14), done.
Writing objects: 100% (14/14), 3.20 KiB | 1.60 MiB/s, done.
Total 14 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), done.
To https://github.com/nixopn/lab02dzi.git
   dde68e2..a645b22  master -> master
`````

9. Проверьте, что история коммитов доступна в удалёный репозитории.

`````sh
git log origin/master
`````

`````sh
commit a645b22476d536a360f6eb7a032bbf698ce807f5 (HEAD -> master, origin/master)
Author: nixopn <eisnersandy2@gmail.com>
Date:   Sun Apr 14 21:40:40 2024 +0300

    Your commit message

commit 0a13a5dbb15bb4a493dcf401e71488f74f2906fc (main)
Author: nixopn <eisnersandy2@gmail.com>
Date:   Sun Apr 14 21:35:44 2024 +0300

    by name

commit 81d906af6a6e2319febdb3b767172f8b327cf001
Author: nixopn <eisnersandy2@gmail.com>
Date:   Sun Apr 14 21:34:33 2024 +0300

    Added initial version of hello_world.cpp with bad coding.

commit c4cdbc42f6e2cefc2130ce4f4f0e33b81dad42e4
Author: nixopn <eisnersandy2@gmail.com>
Date:   Sun Apr 14 21:11:55 2024 +0300

    Added initial version of hello_world.cpp with bad coding.

commit dde68e2b37394db3dadcfd5d2276bd0c1ef35207
Author: nixopn <eisnersandy2@gmail.com>
Date:   Sun Apr 14 20:52:29 2024 +0300

    added README.md
`````

**Chyast 2**

1. В локальной копии репозитория создайте локальную ветку patch1.

`````sh
git checkout -b patch1
`````

`````sh
Switched to a new branch 'patch1'
`````

2. Внесите изменения в ветке patch1 по исправлению кода и избавления от using namespace std;

`````sh
#include <iostream>
#include <string>

int main() {
    std::string name;
    std::cout << "Enter your name: ";
    std::cin >> name;

    std::cout << "Hello world from " << name << std::endl;
    return 0;
}
`````

3. commit, push локальную ветку в удалённый репозиторий.

`````sh
git add hello_world.cpp
git commit -m "Removed using namespace std;"
git push origin patch1

`````

`````sh
[patch1 bffb455] Removed using namespace std;
 1 file changed, 8 insertions(+), 8 deletions(-)
 
 Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 428 bytes | 214.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'patch1' on GitHub by visiting:
remote:      https://github.com/nixopn/lab02dzi/pull/new/patch1
remote:
To https://github.com/nixopn/lab02dzi.git
 * [new branch]      patch1 -> patch1
`````

4. Проверьте, что ветка patch1 доступна в удалёный репозитории.

5. Создайте pull-request patch1 -> master.

`````sh
https://github.com/nixopn/lab02dzi/pull/1
`````


6. В локальной копии в ветке patch1 добавьте в исходный код комментарии.

`````sh
#include <iostream>
#include <string>//libraries
int main() {
//enter name
    std::string name;
    std::cout << "Enter your name: ";
    std::cin >> name;
std::cout << "Hello world from " << name << std::endl;
return 0;
}
`````

7. commit, push.

`````sh
git commit -a -m "Dobavil commentarii"

git push origin patch1
`````

`````sh
[patch1 85fbedf] Dobavil commentarii
 2 files changed, 198 insertions(+), 5 deletions(-)
 
 Username for 'https://github.com': nixopn
Password for 'https://ттnixopn@github.com':
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 3.13 KiB | 3.13 MiB/s, done.
Total 4 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/nixopn/lab02dzi.git
   bffb455..85fbedf  patch1 -> pat
`````

8. Проверьте, что новые изменения есть в созданном на шаге 5 pull-request

`````sh
Проверяем в репозитории через графический интерфейс.
`````

9. В удалённый репозитории выполните слияние PR patch1 -> master и удалите ветку patch1 в удаленном репозитории.


10. Локально выполните pull.

`````sh
git pull origin master
`````

`````sh
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 904 bytes | 47.00 KiB/s, done.
From https://github.com/nixopn/lab02dzi
 * branch            master     -> FETCH_HEAD
   a645b22..23c0468  master     -> origin/master
Updating 85fbedf..23c0468
Fast-forward
`````

11. С помощью команды git log просмотрите историю в локальной версии ветки master.

`````sh
git log
`````

`````sh
Author: nixopn <eisnersandy2@gmail.com>
Date:   Mon Apr 15 15:04:18 2024 +0300

    Dobavil commentarii

commit bffb455668cba59c3175c13db1f9962551ff6734
Author: nixopn <eisnersandy2@gmail.com>
Date:   Sun Apr 14 22:54:12 2024 +0300

    Removed using namespace std;

commit a645b22476d536a360f6eb7a032bbf698ce807f5 (master)
Author: nixopn <eisnersandy2@gmail.com>
Date:   Sun Apr 14 21:40:40 2024 +0300

    Your commit message

commit 0a13a5dbb15bb4a493dcf401e71488f74f2906fc (main)
Author: nixopn <eisnersandy2@gmail.com>
`````

12. Удалите локальную ветку patch1.

`````sh
git branch -d patch1
`````

`````sh
Deleted branch patch1 (was 91f3162).
`````

**Chyast 3**

1. Создайте новую локальную ветку patch2.

`````sh
git checkout -b patch2
`````

`````sh
Switched to a new branch 'patch2'
`````

2. Измените code style с помощью утилиты clang-format. Например, используя опцию -style=Mozilla.

`````sh
clang-format -style=Mozilla -i hello_world.cpp
`````

3. commit, push, создайте pull-request patch2 -> master.

`````sh
git add hello_world.cpp
git commit -m "Clang-formatishe"
git push origin patch2
`````

`````sh
[patch2 b90d032] Clang-formatishe
 1 file changed, 10 insertions(+), 8 deletions(-)
 
 Username for 'https://github.com': nixopn
Password for 'https://nixopn@github.com':
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 8 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 1.33 KiB | 1.33 MiB/s, done.
Total 6 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'patch2' on GitHub by visiting:
remote:      https://github.com/nixopn/lab02dzi/pull/new/patch2
remote:
To https://github.com/nixopn/lab02dzi.git
 * [new branch]      patch2 -> patch2
`````

4. В ветке master в удаленном репозитории измените комментарии, например, расставьте знаки препинания, переведите комментарии на другой язык.


5. Убедитесь, что в pull-request появились конфликтны.


6. Для этого локально выполните pull + rebase (точную последовательность команд, следует узнать самостоятельно). Исправьте конфликты.

`````sh
git pull origin main
git checkout patch2
git add .
git rebase main
git add .
git rebase --continue
`````

`````sh
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 971 bytes | 161.00 KiB/s, done.
From https://github.com/nixopn/lab02dzi
   b90d032..3ea5397  patch2     -> origin/patch2

Switched to branch 'patch2'

Слияние hello_world.cpp
КОНФЛИКТ (содержимое): Конфликт слияния в hello_world.cpp
error: не удалось применить коммит ebad822... Updated code style using clang-format
hint: Resolve all conflicts manually, mark them as resolved with
hint: "git add/rm <conflicted_files>", then run "git rebase --continue".
hint: You can instead skip this commit: run "git rebase --skip".
hint: To abort and get back to the state before "git rebase", run "git rebase --abort".

1 file changed, 2 deletions(-)
`````

7. Сделайте force push в ветку patch2

`````sh
git push origin patch2 --force
`````

`````sh
Username for 'https://github.com': nixopn
Password for 'https://тшnixopn@github.com':
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 8 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 1.34 KiB | 1.34 MiB/s, done.
Total 6 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/nixopn/lab02dzi.git
 + 3ea5397...235cdfb patch2 -> patch2 (forced update)
`````

8. Убедитель, что в pull-request пропали конфликтны.


9. Вмержите pull-request patch2 -> master.

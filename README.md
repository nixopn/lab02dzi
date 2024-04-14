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

`````sh

`````

8. Запуште изменения в удалёный репозиторий.

`````sh

`````

9. Проверьте, что история коммитов доступна в удалёный репозитории.

`````sh

`````
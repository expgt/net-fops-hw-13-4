# Домашнее задание к занятию «Инструменты Git» - Розаев А.Ю.

### Цель задания

В результате выполнения задания вы:

* научитесь работать с утилитами Git;
* потренируетесь решать типовые задачи, возникающие при работе в команде. 

### Инструкция к заданию

1. Склонируйте [репозиторий](https://github.com/hashicorp/terraform) с исходным кодом Terraform.
2. Создайте файл для ответов на задания в своём репозитории, после выполнения прикрепите ссылку на .md-файл с ответами в личном кабинете.
3. Любые вопросы по решению задач задавайте в разделе "Вопросы по заданию".

------

## Задание и решение

1. Найдите полный хеш и комментарий коммита, хеш которого начинается на `aefea`.

Коммит, хэш которого начинается на aefea, имеет следующие данные:
- полный хэш коммита:
  aefead2207ef7e2aa5dc81a34aedf0cad4c32545
- комментарий коммита:
  Update CHANGELOG.md

Данную информацию можно получить с помощью команды:
```bash
git show aefea
```

![1](https://github.com/expgt/net-fops-hw-13-4/blob/main/13_4_1.png)
---

2. Ответьте на вопросы.

* Какому тегу соответствует коммит `85024d3`?

Коммит 85024d3 соответствует тегу v0.12.23

Данную информацию можно получить с помощью команды:
```bash
git show 85024d3
```

![2](https://github.com/expgt/net-fops-hw-13-4/blob/main/13_4_2.png)
---

* Сколько родителей у коммита `b8d720`? Напишите их хеши.

У коммита b8d720 два родителя.
Их полные хэши:
- 56cd7859e05c36c06b56d013b55a252d0bb7e158
- 9ea88f22fc6269854151c571162c5bcf958bee2b

Данную информацию можно получить с помощью команды:
```bash
git log --pretty=%P -n 1 b8d720
```

![3](https://github.com/expgt/net-fops-hw-13-4/blob/main/13_4_3.png)
---

* Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами  v0.12.23 и v0.12.24.

Полный список коммитов между тегами  v0.12.23 и v0.12.24 включает в себя следующие хэши и комментарии:
- 33ff1c03bb (tag: v0.12.24) v0.12.24
- b14b74c493 [Website] vmc provider links
- 3f235065b9 Update CHANGELOG.md
- 6ae64e247b registry: Fix panic when server is unreachable
- 5c619ca1ba website: Remove links to the getting started guide's old location
- 06275647e2 Update CHANGELOG.md
- d5f9411f51 command: Fix bug when using terraform login on Windows
- 4b6d06cc5d Update CHANGELOG.md
- dd01a35078 Update CHANGELOG.md
- 225466bc3e Cleanup after v0.12.23 release

Данную информацию можно получить с помощью команды:
```bash
git log v0.12.23..v0.12.24 --oneline
```

![4](https://github.com/expgt/net-fops-hw-13-4/blob/main/13_4_4.png)
---

* Найдите коммит, в котором была создана функция `func providerSource`, её определение в коде выглядит так: `func providerSource(...)` (вместо троеточия перечислены аргументы).

Искомая функция имеет вид func providerSource(services *disco.Disco)

Для ее поиска необходимо выполнить:
- поиск хэша коммита
```bash
git log -S "func providerSource(" --oneline --reverse
```
- поиск аргумента внутри этого коммита
```bash
git show 8c928e8358 | grep "func providerSource"
```

![5](https://github.com/expgt/net-fops-hw-13-4/blob/main/13_4_5.png)
---

* Найдите все коммиты, в которых была изменена функция `globalPluginDirs`.

Коммиты, в которых была изменена функция `globalPluginDirs`:
- 7c4aeac5f3 stacks: load credentials from config file on startup (#35952)
- 8364383c35 Push plugin discovery down into command package

Данную информацию можно получить с помощью команды:
```bash
git log -S "func globalPluginDirs" --oneline
```

![6](https://github.com/expgt/net-fops-hw-13-4/blob/main/13_4_6.png)
---


* Кто автор функции `synchronizedWriters`?

Автором функции synchronizedWriters является Martin Atkins

Данную информацию можно получить с помощью команды:
```bash
git log -S "func synchronizedWriters" --pretty=format:"%h - %an <%ae>, %ad : %s" --reverse
```

![7](https://github.com/expgt/net-fops-hw-13-4/blob/main/13_4_7.png)
---


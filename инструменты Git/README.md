# Результаты работы с темой инструменты Git
1. Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.
Найти хэш данного коммита можно  помощью команды  git log -1 --pretty=format:"%H %s" aefea, так же его можно найти с помощью команды git show aefea
![aefea](/%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B%20Git/1.jpg)
2. Какому тегу соответствует коммит 85024d3?
Найти тег принадлежащий данному коммиту можно с помощью команды git show 85024d3
![85024d3](/%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B%20Git/2.jpg)
Так же его можно найти с помощью ключа --points-at: git tag --points-at 85024d3
![points-at](/%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B%20Git/2.1.jpg)
3. Сколько родителей у коммита b8d720? Напишите их хеши.
При помощи команды  git log -5 b8d720 --graph, выводится дерево коммитов, в котором можно увидеть, что наш коммит состоит из двух смерженных коммитов, из чего можно сделать вывод, что родителей у данного коммита 2, а так же с помощью команды git show b8d720^, можно проверить количество родителей у коммита. Хеш первого и второго родителей соответственно: 56cd7859e05c36c06b56d013b55a252d0bb7e158, 9ea88f22fc6269854151c571162c5bcf958bee2b
![3](/%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B%20Git/3.jpg)
![3.1](/%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B%20Git/3.1.jpg)
4. Перечислите хеши и комментарии всех коммитов которые были сделаны между тегами v0.12.23 и v0.12.24
Все хеши можно посмотреть с помощью команды  git log v0.12.23...v0.12.24, а так же что бы вывести хеши коммитов укороченные можно использовать ключ --oneline.
хэши и комментарии: b14b74c493 [Website] vmc provider links; 3f235065b9 Update CHANGELOG.md; 6ae64e247b registry: Fix panic when server is unreachable; 5c619ca1ba website: Remove links to the getting started guide's old location; 06275647e2 Update CHANGELOG.md; d5f9411f51 command: Fix bug when using terraform login on Windows; 4b6d06cc5d Update CHANGELOG.md; dd01a35078 Update CHANGELOG.md; 225466bc3e Cleanup after v0.12.23 release
![4](/%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B%20Git/4.jpg)
![4.1](/%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B%20Git/4.1.jpg)
5. Найдите коммит в котором была создана функция func providerSource, ее определение в коде выглядит так func providerSource(...)
Данный коммит можно найти с помощью команды git log с ключом -S
![5](/%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B%20Git/5.jpg)
Данный коммит можно найти в два шага.  При помощи команды git grep --break --heading -n -e 'func providerSource' которая ищет совпадение по ключу -e, ключ -n выводит номер строки в файле, heading выводит название файла, а --break новую строку после каждого совпадения
![5.1](/%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B%20Git/5.1.jpg)
далее используя имя файла в котором находитс фукия можно найти нужный нам коммит
![5.2](/%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B%20Git/5.2.jpg)
6. Найдите все коммиты в которых была изменена функция globalPluginDirs.
Делайем все тоже самое что и в 5 задании по тому же методу
Ищем имя файла:
![6](/%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B%20Git/6.jpg)
И находим все коммиты
![6.1](/%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B%20Git/6.1.jpg)
7. Кто автор функции synchronizedWriters?
Чтобы найти автора данной функии используем комнду git log с ключом -S
![7](/%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B%20Git/7.jpg)
автора данной функции можно увидеть по дате первого коммита
Или можно использовать ключь --prety=format
![7.1](/%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B%20Git/7.1.jpg)
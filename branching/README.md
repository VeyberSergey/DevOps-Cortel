## Ветвления GIT
1. Создание каталока branching и двух файлов merge.sh и rebase.sh
![merge_and_reabase](/screanshots_job_2/1.jpg)
2. Подготовка файла merge.sh
* Создаем ветку git-merge, заменяем содержимое файла merge.sh, создаем коммиит merge: @ instead * и отправляем его в репозиторий
![commit_merge: @ instead *](/screanshots_job_2/2.jpg)
* Вносим еще одно изменение в merge.sh и коммитим его merge: use shift
![commit_merge_merge: use shift](/screanshots_job_2/3.jpg)
3. Подготовка файла rebase.sh
* Находим хеш нужного нам коммита prepare for merge and rebase, выполняем команду git checkout. Далее созадем ветку git-rebase
![vet_git_rebase](/screanshots_job_2/create-git-rebase.jpg)
* Изменяем в ветке git-rebase файл rebase.sh на данный скрипт и отправляем его с коммитом git-rebase 1
count=1
for param in "$@"; do
    echo "Parameter: $param"
    count=$(( $count + 1 ))
done

echo "====="
![git_rebase1](/screanshots_job_2/gitrebase11.jpg)
* И сделаем еще один коммит git-rebase 2 с пушем заменив echo "Parameter: $param" на echo "Next parameter: $param".
![git_rebase2](/screanshots_job_2/gitrebase2.jpg)
4. Промежуточный итог
![promeg_itog](/screanshots_job_2/promezj-rez.jpg)
5. Сливаем ветку git-merge и отправляем в репозиторий
![git_merge_git-merge](/screanshots_job_2/merge-git-merge.jpg)
![rezult_git_merge](/screanshots_job_2/promezj-rez.jpg)
6. Rebase
* Выполним rebase ветки git-rebase на main
![main_rebase](/screanshots_job_2/git_rebase.jpg)
* Переключаемся на ветку git-rebase и выполняем git rebase -i main. В открывшемся диалоге должно быть два выполненных нами коммита, давайте заодно объединим их в один, указав слева от нижнего fixup.
![two_commit](/screanshots_job_2/two%20commits.jpg)
![fixup](/screanshots_job_2/fixup.jpg)
* Смотрим файл rebase.sh, видим метки которые проставил сам гит, удаляем их и оставляем echo "\$@ Parameter #$count = $param"
![conf1](/screanshots_job_2/ispfilerebase.jpg)
* Сообщаем гиту что конфлик решен, далее переходим на следующий коммит и в редакторе оставляем echo "Next parameter: $param"
![conf2](/screanshots_job_2/nextconf.jpg)
* Получаем новый объединеный коммит
![obed_commit](/screanshots_job_2/continie.jpg)
* После сохранения изменения, гит сообщит: 
![sucsess](/screanshots_job_2/sucsessful.jpg)
* Выполняем git push -u origin git-rebase, он выполнится с ошибкой, потому что мы перезаписываем историю, для этого нужно обавить флаг force
![force](/screanshots_job_2/force.jpg)
* Смерживаем ветку git-rebase в main
![marge_git_rebase](/screanshots_job_2/marge-git-rebase.jpg)
* Итоговый результат 
![itog](/screanshots_job_2/rezult.jpg)
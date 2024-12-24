1. Как задать имя пользователя и адрес электронной почты <br>

Имя пользователя нужно, чтобы привязывать коммиты к вашему имени.  <br>
Это не то же самое, что имя пользователя учётной записи GitHub, с  <br>
помощью которого выполняется вход в профиль на GitHub. Задать или  <br>
изменить имя пользователя можно с помощью команды git config.  <br>
Новое имя будет автоматически отображаться в последующих коммитах, <br>
отправленных на GitHub через командную строку. Если хотите скрыть  <br>
своё реальное имя, можно использовать в качестве имени  <br>
пользователя Git произвольный набор символов.  <br>

git config --global user.name "Tara Routray"  <br>

Кроме того, командой git config можно изменять адрес электронной  <br>
почты, привязанный к вашим коммитам Git. Новый адрес электронной  <br>
почты будет автоматически отображаться во всех дальнейших  <br>
коммитах, поданных на GitHub через командную строку. <br>


git config --global user.email "dev@tararoutray.com" <br>



2. Кэширование учётных данных <br>


Кэшировать учётные данные можно с помощью параметра config с  <br>
флагом --global. Так вы избавитесь от необходимости вручную  <br>
вводить имя пользователя и пароль при создании нового коммита. <br>


git config --global credential.helper cache <br>



3. Инициализация репозитория <br>


Создать пустой репозиторий Git или вновь инициализировать  <br>
существующий можно параметром init. При инициализации он  <br>
создаст скрытую папку. В ней содержатся все объекты и ссылки,  <br>
которые Git использует и создаёт в истории работы над проектом. <br>


git init <br>



4. Добавление отдельных файлов или всех файлов в область  <br>
подготовленных файлов

Добавить отдельный файл в область подготовленных файлов можно  <br>
параметром add с указанием имени файла. Просто замените somefile.js  <br>
на актуальное имя. <br>


git add somefile.js <br>


Кроме того, можно добавить все файлы и папки в эту область,  <br>
предоставив wildcard . вместо имени файла: <br>


git add . <br>



5. Проверка статуса репозитория <br>


Просмотреть статус нужного репозитория можно по ключевому слову  <br>
status: его действие распространяется на подготовленные,  <br>
неподготовленные и неотслеживаемые файлы. <br>


git status <br>



6. Внесение изменений однострочным сообщением или через редактор <br>


При создании коммита в репозитории можно добавить однострочное  <br>
сообщение с помощью параметра commit с флагом -m. Само сообщение  <br>
вводится непосредственно после флага, в кавычках. <br>


git commit -m "Your short summary about the commit" <br>


Также можно открыть текстовый редактор в терминале для написания  <br>
полного сообщения коммита. Оно может состоять из нескольких строк  <br>
текста, в котором подробно характеризуются изменения, внесённые в  <br>
репозиторий.

git commit <br>



7. Просмотр истории коммитов с изменениями <br>


Просматривать изменения, внесённые в репозиторий, можно с помощью  <br>
параметра log. Он отображает список последних коммитов в порядке  <br>
выполнения. Кроме того, добавив флаг -p, вы можете подробно изучить  <br>
изменения, внесённые в каждый файл. <br>


git log -p <br>



8. Просмотр заданного коммита <br>


Просмотреть полный список изменений, внесённых конкретным коммитом,  <br>
можно с помощью параметра show, указав идентификатор или хеш коммита.  <br>
Значение хеша уникально для каждого коммита, созданного в вашем  <br>
репозитории. <br>


git show 1af17e73721dbe0c40011b82ed4bb1a7dbe3ce29 <br>


Также можно использовать сокращённый хеш. <br>


git show 1af17e <br>



9. Просмотр изменений до коммита <br>


Можно просматривать список изменений, внесённых в репозиторий,  <br>
используя параметр diff. По умолчанию отображаются только изменения,  <br>
не подготовленные для фиксации. <br>


git diff <br>


Для просмотра подготовленных изменений необходимо добавить флаг --staged. <br>


git diff --staged <br>


Также можно указать имя файла как параметр и просмотреть изменения,  <br>
внесённые только в этот файл. <br>


git diff somefile.js <br>



10. Удаление отслеживаемых файлов из текущего рабочего дерева <br>


Удалять файлы из текущего рабочего дерева можно с помощью  <br>
параметра rm. При этом файлы удаляются и из индекса. <br>


git rm dirname/somefile.js <br>


Можно также использовать маски файлов (например *.js) для  <br>
удаления всех файлов, соответствующих критерию. <br>


git rm dirname/*.html <br>



11. Переименование файлов <br>


Переименовать файл или папку можно параметром mv. Для него указывается <br>
источник source и назначение destination. Источник — реально существующий  <br>
файл или папка, а назначение — существующая папка. <br>


git mv dir1/somefile.js dir2 <br>


При выполнении команды файл или папка, указанные как источник, будут  <br>
перемещены в папку назначения. Индекс будет обновлён соответственно,  <br>
но изменения нужно записать. <br>



12. Отмена подготовленных и неподготовленных изменений <br>


Восстановить файлы рабочего дерева, не подготовленные к коммиту, можно  <br>
параметром checkout. Для проведения операции требуется указать путь к  <br>
файлу. Если путь не указан, параметр git checkout изменит указатель HEAD,  <br>
чтобы задать указанную ветку как текущую. <br>


git checkout somefile.js <br>


Восстановить подготовленный файл рабочего дерева можно параметром reset.  <br>
Потребуется указать путь к файлу, чтобы убрать его из области подготовленных  <br>
файлов. При этом не будет производиться откат никаких изменений или модификаций —  <br>
однако файл перейдёт в категорию не подготовленных к коммиту. <br>


git reset HEAD somefile.js <br>


Если нужно выполнить это действие для всех подготовленных файлов, путь к  <br>
ним указывать не надо. <br>


git reset HEAD <br>



13. Изменение последнего коммита <br>


Внести изменения в последний коммит можно параметром commit с флагом --amend. <br>
 Например, вы записали изменения, внесённые в ряд файлов, и поняли, что  <br>
допустили ошибку в сообщении коммита. В этом случае можете воспользоваться  <br>
указанной командой, чтобы отредактировать сообщение предыдущего коммита, не  <br>
изменяя его снимок. <br>


git commit --amend -m "Updated message for the previous commit" <br>


Также можно вносить изменения в файлы, отправленные ранее. Например, вы  <br>
изменили несколько файлов в ряде папок и хотите их записать как единый снимок,  <br>
но забыли добавить в коммит одну из папок. Чтобы исправить такую ошибку,  <br>
достаточно подготовить для фиксации остальные файлы и папки и создать коммит с  <br>
флагами --amend и --no-edit. <br>


git add dir1 <br>

git commit <br>


# Here you forgot to add dir2 to commit, you can execute the <br>

following command to amend the other files and folders. <br>


git add dir2 <br>

git commit --amend --no-edit <br>


Флаг --no-edit позволит внести в коммит поправку без изменения сообщения  <br>
коммита. В этом случае итоговый коммит заменит неполный, а выглядеть это  <br>
будет так, как будто мы отправили изменения ко всем файлам в нужных папках  <br>
как единый снимок. <br>


Внимание! Не изменяйте публичные коммиты. <br>


С помощью amend прекрасно исправляются локальные коммиты, а исправления  <br>
можно передать в общий репозиторий. Однако изменять коммиты, уже доступные  <br>
другим пользователям, не следует. Помните, что изменённые коммиты являются  <br>
совершенно новыми, а предыдущий коммит уже не будет доступен в текущей ветке.  <br>
Последствия будут такими же, как при отмене изменений публичного снимка. <br>



14. Откат последнего коммита <br>


Откатить последний коммит можно с помощью параметра revert. Создастся  <br>
новый коммит, содержащий обратные преобразования относительно предыдущего,  <br>
и добавится к истории текущей ветки. <br>


git revert HEAD <br>


▍ Разница между revert и reset <br>


Команда git revert отменяет изменения, записанные только одним коммитом.  <br>
Она не откатывает проект к более раннему состоянию, удаляя все последующие  <br>
коммиты, как это делает команда git reset. <br>


У команды revert есть два крупных преимущества по сравнению с reset. Во-первых,  <br>
она не меняет историю проекта и производит операцию, безопасную для коммитов.  <br>
Во-вторых, её объектом выступает конкретный коммит, созданный в любой момент истории,  <br>
а git reset всегда берёт за точку отсчёта текущий коммит. К примеру, если нужно  <br>
отменить старый коммит с помощью git reset, придётся удалить все коммиты, поданные  <br>
после целевого, а затем выполнить их повторно. Следовательно, команда git revert —  <br>
гораздо более удобный и безопасный способ отмены изменений. <br>



15. Откат заданного коммита <br>


Откатить проект до заданного коммита можно с помощью параметра revert и  <br>
идентификатора коммита. Создастся новый коммит — копия коммита с  <br>
предоставленным идентификатором — и добавится к истории текущей ветки. <br>


git revert 1af17e <br>



16. Создание новой ветки и переход в неё <br>


Создать новую ветку можно с помощью параметра branch, указав имя ветки. <br>


git branch new_branch_name <br>


Но Git не переключится на неё автоматически. Для автоматического перехода  <br>
нужно добавить флаг -b и параметр checkout. <br>


git checkout -b new_branch_name <br>



17. Просмотр списка веток <br>


Можно просматривать полный список веток, используя параметр branch.  <br>
Команда отобразит все ветки, отметит текущую звёздочкой (*) и выделит её цветом. <br>


git branch <br>


Также можно вывести список удалённых веток с помощью флага -a. <br>


git branch -a <br>



18. Удаление ветки <br>


Удалить ветку можно параметром branch с добавлением флага -d и указанием  <br>
имени ветки. Если вы завершили работу над веткой и объединили её с основной,  <br>
можно её удалить без потери истории. Однако, если выполнить команду удаления  <br>
до слияния — в результате появится сообщение об ошибке. Этот защитный механизм  <br>
предотвращает потерю доступа к файлам. <br>


git branch -d existing_branch_name <br>


Для принудительного удаления ветки используется флаг -D с заглавной буквой. <br>
 В этом случае ветка будет удалена независимо от текущего статуса, без  <br>
предупреждений. <br>


git branch -D existing_branch_name <br>


Вышеуказанные команды удаляют только локальную копию ветки.  <br>
В удалённом репозитории она может сохраниться. Если хотите стереть  <br>
удалённую ветку, выполните следующую команду: <br>


git push origin --delete existing_branch_name <br>


19. Слияние двух веток <br>


Объединить две ветки можно параметром merge с указанием имени ветки.  <br>
Команда объединит указанную ветку с основной. <br>


git merge existing_branch_name <br>


Если надо выполнить коммит слияния, выполните команду git merge с флагом --no-ff. <br>


git merge --no-ff existing_branch_name <br>


Указанная команда объединит заданную ветку с основной и произведёт  <br>
коммит слияния. Это необходимо для фиксации всех слияний в вашем репозитории. <br>



20. Отображение журнала фиксации в виде графика для текущей или всех веток <br>


Просмотреть историю коммитов в виде графика для текущей ветки можно с  <br>
помощью параметра log и флагов --graph --oneline --decorate. Опция --graph  <br>
выведет график в формате ASCII, отражающий структуру ветвления истории  <br>
коммитов. В связке с флагами --oneline и --decorate, этот флаг упрощает  <br>
понимание того, к какой ветке относится каждый коммит. <br>


git log --graph --oneline --decorate <br>


Для просмотра истории коммитов по всем веткам используется флаг --all. <br>


git log --all --graph --oneline --decorate <br>



21. Прекращение слияния при конфликте <br>


Прервать слияние в случае конфликта можно параметром merge с  <br>
флагом --abort. Он позволяет остановить процесс слияния и вернуть  <br>
состояние, с которого этот процесс был начат. <br>


git merge --abort <br>


Также при конфликте слияния можно использовать параметр reset,  <br>
чтобы восстановить конфликтующие файлы до стабильного состояния. <br>


git reset <br>



22. Добавление удалённого репозитория <br>


Добавить удалённый репозиторий можно параметром remote add,  <br>
указав shortname и url требуемого репозитория. <br>


git remote add awesomeapp https://github.com/someurl.. <br>



23. Просмотр удалённых URL-адресов <br>


Просматривать удалённые URL-адреса можно параметром remote с  <br>
флагом -v. Этот параметр отображает удалённые подключения к другим  <br>
репозиториям.

git remote -v <br>


Такая команда открывает доступ к интерфейсу управления удалёнными  <br>
записями, которые хранятся в файле .git/config репозитория. <br>



24. Получение дополнительных сведений об удалённом репозитории <br>


Получить подробные сведения об удалённом репозитории можно с  <br>
помощью параметра remote show с указанием имени репозитория — например, origin. <br>


git remote show origin <br>


Эта команда отображает список веток, связанных с удалённым  <br>
репозиторием, а также рабочих станций, подключённых для получения  <br>
и отправки файлов. <br>



25. Отправка изменений в удалённый репозиторий <br>


Отправлять изменения в удалённый репозиторий можно параметром push  <br>
с указанием имени репозитория и ветки. <br>


git push origin main <br>


Эта команда передаёт локальные изменения в центральный репозиторий,  <br>
где с ними могут ознакомиться другие участники проекта. <br>



26. Получение изменений из удалённого репозитория <br>


Для загрузки изменений из удалённого репозитория используется параметр  <br>
pull. Он скачивает копию текущей ветки с указанного удалённого репозитория  <br>
и объединяет её с локальной копией. <br>


git pull <br>


Также можно просмотреть подробные сведения о загруженных файлах с  <br>
помощью флага --verbose. <br>


git pull --verbose <br>



27. Слияние удалённого репозитория с локальным <br>


Слияние удалённого репозитория с локальным выполняется параметром merge <br>
 с указанием имени удалённого репозитория. <br>


git merge origin <br>



28. Отправка новой ветки в удалённый репозиторий <br>


Передать новую ветку в удалённый репозиторий можно параметром push  <br>
с флагом -u, указав имя репозитория и имя ветки. <br>


git push -u origin new_branch <br>



29. Удаление удалённой ветки <br>


Чтобы избавиться от удалённой ветки, используйте параметр push с флагом  <br>
--delete, указав имя удалённого репозитория и имя ветки. <br>


git push --delete origin existing_branch <br>



30. Использование перебазирования <br>


Для доступа к этой функции используйте параметр rebase с указанием имени  <br>
ветки. Перебазирование — это процесс объединения или перемещения  <br>
последовательности коммитов на новый родительский снимок. <br>


git rebase branch_name <br>


Эта команда изменит основу ветки с одного коммита на другой, как если  <br>
бы вы начали ветку с другого коммита. В Git это достигается за счёт  <br>
создания новых коммитов и применения их к указанному базовому коммиту.  <br>
Необходимо понимать, что, хотя ветка и выглядит такой же, она состоит из  <br>
совершенно новых коммитов. <br>


▍ Спасибо за внимание! <br>


Вы узнали 30 основных команд интерфейса командной строки Git. Теперь,  <br>
при условии регулярной практики, у вас есть всё необходимое, чтобы достичь  <br>
мастерства в управлении репозиториями GitHub. <br>


---

---

# А теперь ребята пример правильного оформления файла README.md:


# Шпаргалка markdown

## Выделение текста

Вы можете выделять текст в markdown с помощью символов `_` или `*`. Например:

Пример _курсива_ и **жирного** текста.

## Заголовки

Заголовки можно создавать с помощью символа `#`. Чем больше `#`, тем меньше заголовок. Например:

# Заголовок первого уровня
## Заголовок второго уровня
### Заголовок третьего уровня

## Выделение кода

Чтобы выделить текст как код, поместите его в тройные кавычки `````. 

```
mkdir my_project
cd my_project
git init
```
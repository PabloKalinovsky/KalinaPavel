# Что я могу рассказать про то как пользоваться Git

Начну с того, что это просто отвал башки и раньше я такого никогда не делал.

Чтобы git начал отслеживать твои изменение версий его надо инициировать и указать тот файл, который ты хочешь, чтобы он отслеживал:

*git init* тебе в этом поможет. Просто набирай команду и он ответит взаимоностью.

После того как инициировал, надо добавить файл, который git будет отслеживать.

*git add TAB* - переключай кнопкоф TAB файлы, пока не выберешь нужный

Ну вот, пока делал, забыл сохранить файл, в котором делаю изменения а commit пишу.
Не забывай сохранять файл Ctrl+S тебе в помощь.

После того как добавил файл и внес в него изменения, важно сохранить (если не сохранил, подскажет белый кружок на вкладке). Сохранил - пропиши commit, чтобы потом вспомнил что изменял.

*git commit -m "text"* - такое печатай, а вместо text пиши что сделал, воды не лей, но и чтобы понятно было младшей сестре.

Проверь какие изменения уже вносил:

*git log* - покажет список, если список большой, предложил по терминалу пролистать либо клавиней "вниз" либо "Enter"

Чтобы перейти к версии ранее, используй команду:

*git checkout номер версии* - номер версии можно взять из предыдущей команды *git log* похожа на такое 6b9a852b2d10de98871dd5b28082331a85d67f51. Говорят, что можно писать первые 4 символа с этого большого имени, но у меня работает только если пишу полное имя.

Бац, и все пропало. Не очкуй, используй команду

*git checkout master* - и тебя вернет обратно :)

Кароч, все что вспомнил :)

# Ветвление

Удобная программа для людей :) Я бы ее и на работе внедрил, а то столько людей договор редактирует, что просто жуть, концов не найдешь, даже в режиме редактирования. Git все это можем отслеживать.

*Чтобы создать ветку и в ней спокойно работать, используй команду:*

__git branch <branch_name>__ 

Не забудь потом проверить, что там насоздавалось командой:

__git branch__ 

При этом он покажет все ветки, которые уже есть и звездочкой отметит ту, в которой сейчас находишься ты.## Слияние веток

После того, как ветки готовы к включению в основную ветку *master*, используем команду:

__*git merge <branch_name>*__

При этом важно помнить, в какой ветке находимся, к такой и присоединяем. Перед тем как соединять ветки проверь где ты, __*git branch*__ чтобы проверить, __*git checkout <brnach-name>*__ чтобы перейти в нужную ветку.

## Слияние веток

После того, как ветки готовы к включению в основную ветку *master*, используем команду:

__*git merge <branch_name>*__

При этом важно помнить, в какой ветке находимся, к такой и присоединяем. Перед тем как соединять ветки проверь где ты, __*git branch*__ чтобы проверить, __*git checkout <brnach-name>*__ чтобы перейти в нужную ветку.

### Слияние быстрое

Если при слиянии веток, изменения затронули только один раздел, ну например какой-то пункт изменялся в разрезе отдельной ветки и в главной ветке *master* его не изменяли, то слияние произойдет *"быстро"* и терминал выдаст соответствующее сообщение. (Как называется не помнб, после слияния напишу).

### Слияние без конфликтов

Если слияние происходит с веткой, в которой изменения затронули какой-то раздел, а в ветке __*Master*__ тоже были измнения, но они затронули иной раздел, отличный от раздела присоединямой ветки, то такое слияние произойдет без конфликтов, при этом оба раздела будут включены в ветку __*Master*__ без дополнительного согласования.

### Слияние с конфликтами

Если, в присоединямой ветке и в главное ветке __*Master*__ были изменены одинаковые области, то при присоединении ветки терминал выдаст ошибку, подпишет что это conflict И подсветит файл рабочий слева в проводнике красным цветом. При этом мы сможем выбрать какие изменения добавить: Текущие, Новые или добавить оба. В зависимости от обстоятельств, выбираем нужный вариант. 

# Работа с удаленными репозиториями.

Работа с удаленными репозиториями происходит с помощью сервиса gitHub

Ссылка https://github.com 

Есть и другие ресурсы, но этот самый распростарненный. Для того, чтобы начать работать надо зарегистрироваться.

Для того, чтобы начать работать с удаленным репозиторием для начала его надо создать на GitHub и клонировать в VCD. 

Команда для клонирования

*__git clone <адрес репозитория>__*

Адрес репозитория можно получить, нажав на зеленую кнопку *Code*

Послк выполнения команды вы сможете работать с этим репозиторием, при этом скопируется вся его история и ветки.

Перед тем как внести какие-то измненения, необходимо обновить ветку __*master*__.

Для этого используй команду 

 >__*git pull origin master*__

 Таким образом можно актуализировать любую ветку заменив название ветки в команде.

 Для обновления сразу всех веток можно использовать команду

 >__*git pull*__

 На первом этапе наверное так можно делать, но в адльнейшем насколько я понял, предпочтение отдается обновлению веток по отдельности.

 Если ты работаешь с удаленным репозиторием и тебе необходимо отправить обновления на GH, то используй команду

 >__*git push*__ 

 Это также подгрузит обновления всех веток в удаленный репозиторий.



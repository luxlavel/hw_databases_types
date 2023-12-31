# Домашнее задание к занятию "`Базы данных, их типы`" - `Lobakin Pavel`

---

### Задание 1

`Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему?`

`1.1 Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков. СУБД должна гарантировать целостность и чёткую структуру данных`

` Ответ:`
`Реляционные: Oracle Database, MySQL`

`1.2 Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? СУБД должны быть гибкими и быстрыми.`

` Ответ:`
`Для лендинга ключ-значение - Redis, Memcached`
`Для CRM - графовые - Neo4j, Amazon Neptune, InfiniteGraph, InfoGrid`

`1.3 Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.`

` Ответ:`
`документная - CouchDB, MongoDB, Amazon DocumentDB`

`1.4 Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать со связями.`

` Ответ:`
`графовые - Neo4j, Amazon Neptune, InfiniteGraph, InfoGrid`

---

### Задание 2

`2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы транзакция завершилась успешно. Ориентируйтесь на шесть действий.`

1. `заходит в приложение оператора/банка и т.п.`
2. `пользователь идентифицируется в БД оператора по номеру телефона`
3. `идентифицируется баланс счета пользователя в БД оператора`
4. `создается транзакция включающая номер телефона пользователя и суммы пополнения`
5. `сумма пополнения списывается со счета пользователя в банке`
6. `сумма зачисляется на счет пользователя в БД оператора`

---

### Задание 3

`3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL.`

1. `SQL БД следуют требованиям ACID. ACID —  Atomicity (атомарность), Consistency (согласованность), Isolation (изолированность) и Durability (надёжность).`
2. `данные хранятся в виде таблиц, которые легко использовать.`
3. `SQL БД используют структурированный язык запросов (SQL) для управления данными, их обработки, хранения, обновления, удаления.`
4. `транзакционность`
5. `высокая нормализация данных.` 

---

### Задание 4

`Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу выделено 1000 машин.`
`На основе какого критерия будете выбирать тип СУБД и какая модель распределенных вычислений здесь справится лучше всего и почему?`

`Ответ:`
`СУБД - MongoDB по причинам:`
 
1. `распределенного выполнения операций предварительной обработки (map) и свертки (reduce) большого объема данных. При этом функции map работают независимо друг от друга и могут выполняться параллельно на разных узлах кластера.`

2. `быстрота обработки больших объёмов данных за счет распределения операций по вышеописанному принципу. В частности, всего за пару часов MapReduce может отсортировать целый петабайт данных.`

3. `отказоустойчивость и оперативное восстановления после сбоев: при отказе рабочего узла, производящего операцию map или reduce, его работа автоматически передается другому рабочему узлу в случае доступности входных данных для проводимой операции.`

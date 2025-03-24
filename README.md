# Домашнее задание к занятию «Базы данных»
### Грибанов Антоню FOPS-31

---
### Легенда

Заказчик передал вам [файл в формате Excel](https://github.com/netology-code/sdb-homeworks/blob/main/resources/hw-12-1.xlsx), в котором сформирован отчёт. 

На основе этого отчёта нужно выполнить следующие задания.

### Задание 1

Опишите не менее семи таблиц, из которых состоит база данных:

- какие данные хранятся в этих таблицах;
- какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

Приведите решение к следующему виду:

Сотрудники (

- идентификатор, первичный ключ, serial,
- фамилия varchar(50),
- ...
- идентификатор структурного подразделения, внешний ключ, integer).

```bash
01. Проекты_название (
- идентификатор, первичный ключ, SERIAL
- название проекта VARCHAR(150)
)

02. Филиалы_адреса (
- идентификатор, первичный ключ, SERIAL
- область_id, внешний ключ, INTEGER
- город_id, внешний ключ, INTEGER
- адрес филиала, VARCHAR(350)
)

03. Область_название (
- идентификатор, первичный ключ, SERIAL
- название области, VARCHAR(50)
)

04. Города (
- идентификатор, первичный ключ, SERIAL
- название города, VARCHAR(50)
)

05. Подразделения_название (
- идентификатор, первичный ключ, SERIAL
- подразделение, VARCHAR(150)
- тип_подразделения_id, внешний ключ, INTEGER
)

06. Подразделения_типы (
- идентификатор, первичный ключ, SERIAL
- тип подразделения, VARCHAR(50)
)

07. Должность_название (
- идентификатор, первичный ключ, SERIAL
- должности, VARCHAR(50)
)

08. Сотрудники (
- идентификатор, первичный ключ, SERIAL
- ФИО, VARCHAR(150)
- дата найма, DATA
- оклад, MONEY
- должность_id, внешний ключ, INTEGER
- подразделение_id, внешний ключ, INTEGER
- филиал_id, внешний ключ, INTEGER
)

```


## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.


### Задание 2*

Перечислите, какие, на ваш взгляд, в этой денормализованной таблице встречаются функциональные зависимости и какие правила вывода нужно применить, чтобы нормализовать данные.

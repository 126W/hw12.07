# Домашнее задание к занятию "12.07 Репликация и масштабирование. Часть 2" - Евгений Шахов.
---
### Задание 1.
##### Опишите основные преимущества использования масштабирования методами:
- активный master-сервер и пассивный репликационный slave-сервер;
- master-сервер и несколько slave-серверов;
- активный сервер со специальным механизмом репликации — distributed replicated block device (DRBD);
- SAN-кластер.
##### Дайте ответ в свободной форме.
> - Этот метод масштабирования реализуется путём добавления дополнительных серверов которые постоянно или периодически копирут информацию с master-сервера. Таким образом повышается надёжность самой базы данных т.к. если master упадёт, то один из slave-серверов станет master и далее по кругу.  
> - В данном методе slave серверы могут отдавать информацию, а это снижает нагрузку на mastera т.к. ему приходится отвечать на меньшее количество запросов. Повышает отказоустойчивость и производительность БД в целом.
> - В отличии от master-slave подхода, DRBD можно настроить только на одной ноде. Есть отказоустоичивость с ограничениеями в пропускной способности и размером хранилища.
> - Высокая скорость, так же возможность подключения множества серверов для пользования общими ресурсами хранения информации.
---
### Задание 2.
##### Разработайте план для выполнения горизонтального и вертикального шаринга базы данных. База данных состоит из трёх таблиц:
- пользователи,
- книги,
- магазины (столбцы произвольно).
##### Опишите принципы построения системы и их разграничение или разбивку между базами данных. Пришлите блоксхему, где и что будет располагаться. Опишите, в каких режимах будут работать сервера.
> ![image](https://github.com/126W/hw12.07/assets/122415129/4427c956-fa9f-4b1c-96cd-a1975c15ce8a)
---

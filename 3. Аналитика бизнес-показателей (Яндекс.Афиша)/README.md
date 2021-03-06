﻿# Проект "Аналитика бизнес-показателей в Яндекс.Афише"

### Цель:
На основе данных о посещениях сайта Яндекс.Афиши изучить, как люди пользуются продуктом.
Так же необходимо помочь маркетологам оптимизировать маркетинговые затраты, найти оптимальные рекламные источники

### Данные:

***Таблица visits (лог сервера с информацией о посещениях сайта):***
* Uid — уникальный идентификатор пользователя
* Device — категория устройства пользователя
* Start Ts — дата и время начала сессии
* End Ts — дата и время окончания сессии
* Source Id — идентификатор рекламного источника, из которого пришел пользователь

***Таблица orders (информация о заказах):***
* Uid — уникальный id пользователя, который сделал заказ
* Buy Ts — дата и время заказа
* Revenue — выручка Яндекс.Афиши с этого заказа

***Таблица costs (информация о затратах на маркетинг):***
* source_id — идентификатор рекламного источника
* dt — дата
* costs — затраты на этот рекламный источник в этот день

### Задачи:
1. Сделать предобработка данных
2. Построить отчеты и рассчитать метрики
2.1. Продукт:
* DAU, WAU, MAU
* Sticky factor
* ASL или средняя продолжительность сессии
* Retention Rate по визитам
2.2. Продажи:
* Через какое время совершается покупка
* Сколько раз покупают за период
* Средний чек в когортах по месяцам
* Retention rate по покупкам
* Экономика одного покупателя LTV, CAC, ROMI
2.3. Маркетинг:
* Затраты на рекламные источники
* Стоимость привлечения 1 покупателя
* ROMI, окупаемость расходов на рекламу
* Анализ посещаемости ресурса по типу устройства
3. Общий вывод


### Выводы:
Средняя продолжительность сессии длится - 60 секунд.
В среднем пользователи начинают покупать через минуту после начала сессии. Т.е. пользователи знают точно, что они хотят приобрести. 

***DAU***, количество уникальных пользователей в день: 908    
***WAU***, количество уникальных пользователей в неделю: 5716    
***MAU***, количество уникальных пользователей в месяц: 23228    
***Sticky Factor*** (месячный) - 3.9 %
Нормальным считается показатель Sticky factor (месячный) - порядка 20-18%. В данном случае 3,9%, т.е. пользователи в среднем в течение месяца заходил лишь один раз.

После первого месяца количество посетителей и количество покупателей в когорте сильно снижается.

***Retention по визитам***. В первый месяц мы видим низкий коэфициет удержания:
* до декабря 2017 - от 7,7% до 8,5% 
* с декабря 2017 - от 6 % до 4,2%

    Это важный сигнал того, что нужно сосредоточиться на удержании покупателей в первый месяц, ведь большая часть активных покупателей отказывается от сервиса именно в этот период.
    
При этом во всех когортах ***средний чек*** пользователей возрастает на следующий месяц после месяца первой покупки. 
    
С декабря 2017 число покупателей в каждой следующей кагорте падает. Значит, в Яндекс.Афиша со временем приходит всё меньше и меньше новых покупателей.
    
***Первая когорта*** приносит больше всего денег даже после года существования когорты.
У первый когорты спустя год самый высокий коэфициент  удержания Retention Rate. Необходимо подробнее изучить первую когорту и выявить факторы, удерживающие данную ее.
    
***Рекламные источники***
Топ-3 месяцев по затратам на рекламный источник: ноябрь, декабрь, октябрь 2017 г

Меньше всего затрат на 9 и 10 рекламный источник. Но они не приносят много выручки, поэтому источники не являются оптимальными. ( По показатею ROMI 9 источник на 4ом месте, 10 источник на предпоследнем)
    
ТОП-3 источников по соотношению выручки и затрат: 1, 2, 5 канал.
    
Самый неэффективным каналом оказался 3 канал. Он самый дорогостоящий и при этом по выручке занимает всего 6-ое место.
    
***Устройства***
Пользователи заходят на сервис Яндекс.Афиша в основном через ПК и редко обращаются к данному сервису через мобильные устройства. Может быть мобильная версия сайта не достаточна удобна для пользователей и через нее проблематичней делать заказы.
* Количество сессий на ПК больше в 2,7 раза, чем на моб.устройстве.
* Продолжительность сессий на ПК больше в 4 разаб чем на моб.устройстве.

### Используемые инструменты и навыки:
`plotly`,  `seaborn`, `pandas`, `numpy`, предобработка данных, исследовательский анализ данных, когортный анализ, продуктовые метрики, юнит экономика, визуализация данных
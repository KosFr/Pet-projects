# Дашборд для компании Bolid

## Техническое задание на создание дашборда по продажам для компании “Bolid.Team”

### Описание компании
Группа компаний Bolid Team работает на рынке аттракционов и развлечений с 2002 года. Деятельность компании включает 3 направления: 
-	производство аттракционов, 
-	эксплуатация аттракционов,
-	производство мягких призовых игрушек. 
Сайты по направлению поставки мягкой игрушки (b2b):
https://softprize.ru 
https://мягкий-приз.рф
https://plush.team/
Сайт производственного направления:
https://bolid.team 

### Описание проекта

Требуется создать дашборд в DataLens, который позволит анализировать продажи услуг аркадных аттракционов - как верхнеуровнево, так и в разрезе объектов и аттракционов.
На данный момент дашборд будет строиться на исторических данных, в дальнейшем планируется подключение к базе данных и обновление информации в режиме реального времени.
Для построения дашборда используется выгрузка информации о чеках и товарных позициях с сайта https://platformaofd.ru/ за 2022 г и январь - август 2023 гг.

### Результаты

Этот раздел дополняется.

### Описание данных

Файл **items.csv** содержит информацию о товарных позициях в чеках за период с 1 января 2022 г. по 21 августа 2023 г.

ФП - фискальный признак документа — контрольная величина, подтверждающая правильность введенных данных. Вместе с номером документа и номером смены может использоваться как уникальный идентификатор транзакции;

Номер документа - номер по порядку фискального документа;

Дата/время - дата и время формирования документа (чека);

Номер смены - номер смены (по данным кассы), в которую был сформирован документ;

Наименование - название товарной позиции в чеке;

Итого по чеку - общая сумма по чеку в рублях;

Наличными по чеку - сумма наличными по чеку в рублях;

Электронными по чеку - сумма наличными по чеку в рублях;

Цена товара - цена товарной позиции в рублях;

Количество единиц измерения в чеке - количество товара в товарной позиции;

Номер товара в чеке - порядковый номер товара в чеке;

Сумма товара - общая стоимость товара в товарной позиции в рублях. Результат умножения значений параметров «Цена товара» и «Количество единиц измерения в чеке» должно быть равно значению параметра «Сумма товара»;

Название игры - столбец сформирован из данных столбца Наименование, содержит название и ценовую категорию аттракциона;

Группа игры - категория аттракциона.

Файл **checks.csv** содержит информацию о кассовых чеках за период с 1 января 2022 г. по 21 августа 2023 г.

Дата/время - дата и время формирования чека;

Магазин - название объекта

Имя кассы - название кассы (на одном объекте может быть несколько касс)

ФП - фискальный признак документа — контрольная величина, подтверждающая правильность введенных данных. Вместе с номером документа и номером смены может использоваться как уникальный идентификатор транзакции;

Номер документа - номер по порядку фискального документа;

Номер смены - номер смены (по данным кассы), в которую был сформирован чек;

Номер чека за смену - порядковый номер чека в смене (по данным кассы);

Признак расчета - тип операции: приход, расход, возврат прихода, возврат расхода;

Наличными - сумма наличными по чеку в рублях;

Электронными - сумма наличными по чеку в рублях; 

Итого - общая сумма по чеку в рублях;

Статус - статус кассы (Используется / Не используется);

Город - город, в котором расположен объект.


### Платформа для построения дашборда

Требуется построить дашборд в Yandex.DataLens.

Основные пользователи - руководители компании. Дашборд будет использоваться для определения прибыльных аттракционов, групп аттракционов и объектов, а также определения сезонных трендов.

### Макет дашборда

Макет дашборда и навигация по дашборду (одностраничный дашборд, навигация с помощью вкладок, навигация с использованием параметров) - на усмотрение участника. 

Важную информацию и KPI (индикаторы) располагайте сверху, остальные визуализации - по уменьшению степени важности (участник определяет самостоятельно, как скомпоновать метрики).

Добавьте к дашборду название и описание.

К сложным визуализациям можно добавить пояснение о том, как ими пользоваться.
Внизу дашборда добавьте информацию об авторе дашборда и его контакты, а также дату последнего обновления дашборда.

### Основные метрики для построения дашборда

-	общая выручка (индикатор);
-	общее количество проданных услуг (индикатор); 
-	общее количество чеков (индикатор);
-	среднее количество позиций в чеке (индикатор);
-	средняя цена проданной услуги (метрика используется вместо метрики среднего чека)  (индикатор);
-	доля по группам цен (для просмотра, какая доля услуг продается по минимальной цене) (кольцевая диаграмма);
-	выручка по способу расчета (доля наличных и электронных платежей) (кольцевая диаграмма);
-	выручка по признаку расчета (доля приходов и возвратов)  (кольцевая диаграмма).


###  Дополнительные метрики
Изменение метрик в динамике:
- выручка (расчет скользящего среднего для прогноза трендов; сравнение выручки с предыдущим периодом) (линейная диаграмма);
- количество проданных услуг, чеков и средняя цена услуги (линейная диаграмма);
- доля по группам цен (нормированная диаграмма).
Метрики средних продаж по часам, дням, неделям, месяцам, годам:
- средняя выручка (индикатор);
- среднее количество проданных услуг (индикатор);
- среднее количество чеков (индикатор);
- средние продажи на объект (индикатор);
- средние продажи на аттракцион (индикатор);
- средние продажи в час, в день недели, в месяц, в квартал, в год (линейная диаграмма).

Показать на графиках отклонение от среднего в абсолютах и в процентах.

### Уровень детализации
Ключевые показатели - города - объекты - группы аттракционов - аттракционы
Фильтры и срезы данных
Фильтры:
●	Дата;
●	Город;
●	Объект;
●	Группа аттракционов;
●	Аттракцион
Срезы:
●	Дата (по часам, дням, неделям, месяцам, годам);
●	Город;
●	Объект;
●	Группа аттракционов;
●	Аттракцион.
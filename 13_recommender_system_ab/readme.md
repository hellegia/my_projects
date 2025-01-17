## "Оценка корректности проведения и результатов А/В-теста"

## Описание проекта: 

В нашем распоряжении есть датасет с действиями пользователей, техническое задание и несколько вспомогательных датасетов. После предварительного анализа мы получили информацию о том, что пользователи регистрировались с 7 декабря 2020 года и могли совершать любое из 4 событий (вход,  просмотр карточки товара, корзина и покупка), причем эти пользователи пришли с разных регионов - Европа, Северная Америка, Азиатско-Тихоокеанский регион и СНГ. У пользователей было одно из устройств - пк, андроид, айфон и макбук. Все пользователи были разделены на 2 группы - А и В, мы проверяли 1 из проведенных тестов.

## Цель проекта:

Провести оценку корректности А/В-теста и результатов А/В- теста, дать оценку на соответствие теста ТЗ

## Описание данных:

**Датасет final_ab_events.csv содержит колонки:**

`event_dt` — дата и время события

`event_name` — тип события

`user_id` — идентификатор пользователя

`details` — дополнительные данные о событии, например стоимость покупки

**Датасет final_ab_new_users.csv содержит колонки:**

`first_date` — дата и время события

`region` — регион пользователя

`user_id` — идентификатор пользователя

`device` — устройство, с которого происходила регистрация

**Датасет final_ab_participants.csv содержит колонки:**

`ab_test` — название теста

`region` — регион пользователя

`user_id` — идентификатор пользователя

`device` — устройство, с которого происходила регистрация

**Датасет final_ab_marketing_events.csv (календарь маркетинговых событий) содержит колонки:**

`name` — название маркетингового события

`regions` — регионы, в которых будет проводиться кампания

`group` — группа пользователя.

## Техническое задание:

Название теста: recommender_system_test ;

группы: А — контрольная, B — новая платёжная воронка;

дата запуска: 2020-12-07;

дата остановки набора новых пользователей: 2020-12-21;

дата остановки: 2021-01-04;

аудитория: 15% новых пользователей из региона EU;

назначение теста: тестирование изменений, связанных с внедрением улучшенной рекомендательной системы;

ожидаемое количество участников теста: 6000.

## Выводы:

Несмотря на отсутствие критичных пропусков и дубликатов, при внешне кажущихся хороших данных, организован А/В-тест был не очень качественно, мы увидели, что пользователи и участвовали в обеих группах, и пересекались в разных тестах, и совпали по времени с 2 маркетинговыми кампаниями. Также, из Европы новых пользователей оказалось 13%, что также не соответствует требованиям ТЗ (не менее 15%)

Еще в качестве нюанса можно назвать большое количество коротких лайфтаймов у пользователей, а лайфтайм больше 14 оказался у 351 пользователя.

Ожидаемое количество участников нужного нам теста не достигло 6000 человек, в итоге в тесте приняли участие 2788 человек, несмотря на это, такого количесва достаточно (согласно онлайн-калькуляторам       https://www.evanmiller.org/ab-testing/sample-size.html).

Подводя итоги А/В-теста, конверсии пользователей не только не увеличились, согласно ТЗ, не менее, чем на 10% по каждому событию, но даже уменьшились, на 16.17%, 9.74% и на 11.65% для событий `product_page`, `product_cart`, `purchase` соответственно.

При проведении проверки на равенство долей пользователей, совершающих одинаковые события, но находящихся в группах А и В, статистически значимыми оказалось только различие долей по событию `product_page`, по остальным событиям `product_cart`, `purchase` доли статистически не различаются, значимого увеличения конверсии не произошло, цели А/В-теста не достигнуты.

В воронках для каждой из групп нет потери пользователей после перехода из корзину в покупку, то есть, если сложили в корзину, то всегда купили. Наибольшая потеря пользователей возникает после 1 шага - входа в систему, и после просмотра страницы товара к корзине. Значит, нужно обратить внимание на повторное привлечение пользователей после регистрации, мотивировать их, и разрабатывать систему рекомендаций по улучшению подбора товара, чтобы после просмотра карточки он добавлялся в корзину.

В дальнейшем требуется более тщательный сбор данных и более качественная организация А/В-теста. Из дополнительных рекомендаций - избегать время проведения теста вблизи больших праздников и значимых событий (например, Олимипада, Новый год, ), так как в эти периоды поведение пользователей нетипично, и результаты могут дополнительно искажаться.
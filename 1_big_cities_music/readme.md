## Музыка больших городов

Иногда, мы сталкиваемся с стереотипами и мифами, связанными с жителями разных городов, но бизнес должен отличать мифы от действительности, и игнорировать стереотипы, не подтвержденные исследованиями, чтобы принимать рациональные решения.

На датасете из  Яндекс Музыки мы проверим гипотезы и сравним поведение пользователей двух городов - Москвы и Санкт-Петербурга.

## Гипотезы

Сформулируем гипотезы для проверки:

1. Активность пользователей зависит от дня недели. Причём в Москве и Петербурге это проявляется по-разному.
2. Утром в понедельник в Москве преобладают одни жанры музыки, а в Петербурге — другие. Это верно и для вечера пятницы.
3. Москва и Петербург предпочитают разные жанры музыки. В Москве чаще слушают поп-музыку, в Петербурге — русский рэп.

## Данные

- `userID` — идентификатор пользователя;
- `Track` — название трека;
- `artist` — имя исполнителя;
- `genre` — название жанра;
- `City` — город пользователя;
- `time` — время начала прослушивания;
- `Day` — день недели.

## Выводы:

Мы проверили три гипотезы и установили:

1. День недели по-разному влияет на активность пользователей в Москве и Петербурге.

Первая гипотеза полностью подтвердилась.

1. Музыкальные предпочтения не сильно меняются в течение недели — будь то Москва или Петербург. Небольшие различия заметны в начале недели, по понедельникам:

- в Москве слушают музыку жанра “world”,
- в Петербурге — джаз и классику.

Таким образом, вторая гипотеза подтвердилась лишь отчасти. Этот результат мог оказаться иным, если бы не пропуски в данных.

1. Во вкусах пользователей Москвы и Петербурга больше общего чем различий. Вопреки ожиданиям, предпочтения жанров в Петербурге напоминают московские.

Третья гипотеза не подтвердилась. Если различия в предпочтениях и существуют, на основной массе пользователей они незаметны.







Это мой первый проект как аналитика, с использованием библиотек Pandas и Numpy, выполнен осенью 2021 года.
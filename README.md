# Задание
Реализовать REST API блога.
# Реализация
Реализовал на фрейворке django с применением библиотеки django rest framework. Выбрал его, так как из коробки есть ORM + достаточно распространен.
Хотя раньше для своего проекта использовал библиотеку tastypie, но она мне показалась ограниченной в возможностях.

|функция|адрес|Метод|
|---|---|---|
|Добавление пользователя. Поля: имя пользователя|/users/|POST|
|Список постов пользователя. Сортировка по дате добавления в обе стороны|/user_articles/1?ordering=-date_add|GET|
|Добавление поста. Поля: пользователь, список тэгов, название, сам текст|/articles|POST|
|Чтение постов по тэгам / за период / по словам из названия. Сортировка по дате добавления в обе стороны|/articles/?title=&user_creator=&date_add_0=2017-11-01&date_add_1=&tags=tag0&ordering=-date_add|GET|
|Добавление комментария к посту: Поля: пользователь, сам текст|/comment|POST|
|Изменение комментария к посту: Поля: пользователь, сам текст|/comment/1|PUT|
|Чтение комментариев конкретного поста. Сортировка по дате добавления в обе стороны.|/comment_list/1?ordering=-date_add|GET|
|Блокировка возможности комментирования поста для конкретного пользователя| При создании и изменении поста можно добавить список заблокированны пользовательй|PUT/POST|

Учесть высокую нагрузку, хотя бы минимально. Нет необходимости  использовать поисковые индексы.  

✔ Имена пользователей и тэги должны содержать только латинские буквы и  цифры.  

✔ Обмен информацией в json формате.  

# Нагрузочное тестирование

В тесте с помощью locust показал результат в 300rps.
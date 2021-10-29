# questionnaire
тестовое задание тестовое задание

Задача: спроектировать и разработать API для системы опросов пользователей.

Функционал для администратора системы:

- авторизация в системе (регистрация не нужна)
- добавление/изменение/удаление анкет. Атрибуты анкеты: название, дата старта, дата окончания, описание. После создания поле "дата старта" у анкеты менять нельзя
- добавление/изменение/удаление вопросов в анкете. Атрибуты вопросов: текст вопроса, тип вопроса (ответ текстом, ответ с выбором одного варианта, ответ с выбором нескольких вариантов)

Функционал для пользователей системы:

 - получение списка активных опросов
 - прохождение опроса: опросы можно проходить анонимно, в качестве идентификатора пользователя в API передаётся числовой ID, по которому сохраняются ответы пользователя на вопросы; один пользователь может участвовать в любом количестве опросов
 - получение пройденных пользователем опросов с детализацией по ответам (что выбрано) по ID уникальному пользователя

Использовать следующие технологии: Django 2.2.10, Django REST framework.

Результат выполнения задачи:

 - исходный код приложения в github (только на github, публичный репозиторий)
 - инструкция по разворачиванию приложения (в docker или локально)
 - документация по API
 - Выполнение: Программа написана на Python 3.9, должна работать со всеми врелизами Python 3.x Допольнительные пакеты: Django 2.2.10 pip install Django==2.2.10 Django REST framework pip install djangorestframework

Достоинства и недостатки в реализации

Достоинства: 

 - При одинаковом функционале для разных таблиц создаються практически одинаковые классы с одинаковыми функциями. Отличие состоит лишь в используемых дополнительных классах, описываемые модели и их сериализацию. Проблема решена Передачей классов как параметров в родительсктй класс при помощи функции super(). Файл api_views.py строки 12-67

Недостатки:

 - При пакетном создании анкет данные отдельно записывались в соответствующие таблицы без принципа транзакции. RestFramework скорее всего обладает необходимым функционалом, требуеться более углубленное его изучение.
 - При редактировании поля не рзаходит в метод update сериализатора. Поставил кастыль, теперь работает!

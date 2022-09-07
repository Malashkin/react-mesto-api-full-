# Репозиторий для приложения `Mesto`.

## Одностраничное приложение - Серверная часть в директории "backend/", пользовательский интерфейс - в "frontend/".  

### `Функционал:` реазилована возможность регистрации, авторизации, редактирование профиля пользователя(имя, о себе, аватар), карточка с изображением(добавление, удаление только собственных, постановка и снятие "лайка")
### `Описание Backend:`
#### Стек: Node.js + Express + MongoDB
Особенности проекта:
1) Eslint - отлавливает ошибка + кодстайл Airbnb.
2) 12 роутов - регистрация, авторизация, действия с пользователем, действия с карточками.
3) Часть роутов имеет предварительную валидацию для снижения нагрузки на сервер - celebrate, Joi.
4) Обработка ошибок путём вылавливания на каждом этапе блоками .catch.
5) Все роуты, кроме '/signup', '/signin' защищены необходимостью авторизации.
6) При регистрации создается JWT token, который хранится в localStorage, а пароль не возвращается пользователю сохраняясь в MongoDB.
7) Авторизированный пользователь может "ставить лайк" всем карточка, находящимся в Базе данный проекта, но удалять может только созданные им.

### `Описание Frontend:`
#### Стек: Фреймворк ReactJS + HTML-5 + CSS
Особенности проекта:
1) React - функциональные и классовые компоненты, защищенные маршруты, createContext, useEffect, useState. 
2) Запросы отправляются на собственное API, в процессе отправки пользователь получает обратную связь от приложения - на время отправки данных на сервер кнопки submit изменяются c "Сохранить" на "Сохранение...", чтобы у него было понимание, что сервер не завис, а работает с его запросом.
3) Вёрстка - Flexbox + Grid layout.
4) Адаптивный дизайн от 320px до 1280px с помощью медиа-запросов.
5) Валидация введенных данных встроенными средствами HTML-5.
6) Переиспользование элементов верстки. 
7) Файлы структурированы по БЭМ(Nested).

### `Вид макета:` Figma.

#### `Deploy`
Для проведения ревью осуществлялся деплой данного проекта через Yandex.Cloud(ВМ: Ubuntu 20.04 + Nginx), но пробный период закончился, сейчас остается возможность запуска локально(Frontend - порт 3000, Backend - порт 3001). Необходимо только скопировать проект и установить зависимости с помощью npm install.




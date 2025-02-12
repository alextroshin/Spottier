# Spottier

Платформа для поиска баскетбольных площадок и матчей с использованием геоданных.

Описание:
Сервис предоставляет возможность пользователям находить баскетбольные площадки и организовывать матчи по различным городам и странам.
Основной фокус сервиса - работа с геоданными, которые позволяют пользователям выбирать интересующие их оборудованные площадки.

Указатель:

<!-- code_chunk_output -->

- [Spottier](#spottier)
  - [Services](#services)
  - [API](#api)

<!-- /code_chunk_output -->

Функционал сервиса:

- Регистрация и аутентификация пользователей: пользователи могут создавать аккаунты и входить в систему для использования сервиса.
-
- Управление доступом на базе пользователей и групп: сервис предоставляет возможность администраторам управлять правами доступа пользователей и формировать группы пользователей с различными правами.

- Поиск площадок: пользователи могут искать площадки по по различным параметрам, таким как город, страна, тип мероприятия, длительность, стоимость и т.д.

4. Просмотр информации о площадках и матчах которые на них проходили: пользователи могут просматривать подробную информацию, проведенные матчи ,включая описание, фотографии, отзывы и рейтинги.
5. Создания матча: пользователи смогут создавать и регистрировать команды для участия в матчах, на любой баскетбольной площадки.
6. Работа с геоданными: сервис использует геоданные для отображения местоположения площадок на карте на карте, а также для предоставления дополнительной информации о достопримечательностях и местах интереса в выбранных местах. Также проверенные платформой пользователи смогут сами добавлять игровые площадки.

Технологии и СУБД:
Для реализации сервиса можно использовать следующие технологии и СУБД:

- Фреймворк fastapi для разработки веб-приложения
- База данных PostgreSQL для хранения информации о пользователях, площадок и матчей.
- Redis для кэширования данных и ускорения работы сервиса
- Elasticsearch для поиска и индексации площадок.
- Mapbox API для работы с геоданными и отображения карты с местоположением спортивных площадок

## Services

1. Аутентификационный сервис (Authentication Service):

   - Отвечает за регистрацию и аутентификацию пользователей.
   - Хранит информацию о пользователях в базе данных PostgreSQL.
   - Обеспечивает генерацию и проверку токенов доступа для авторизации пользователей.

2. Управление доступом (Access Management Service):

   - Отвечает за управление правами доступа пользователей
   - Хранит информацию о правах доступа пользователей в базе данных PostgreSQL.

3. Сервис поиска площадок (Venue Search Service):

   - Отвечает за поиск площадок на основе различных параметров.
   - Использует Elasticsearch для индексации и поиска площадок.
   - Хранит информацию о площадках в базе данных PostgreSQL.

4. Сервис управления площадками (Venue Management Service):

   - Отвечает за добавление, редактирование и удаление площадок.
   - Хранит информацию о площадках в базе данных PostgreSQL.

5. Сервис управления матчами (Match Management Service):

   - Отвечает за создание, редактирование и удаление матчей.
   - Хранит информацию о матчах в базе данных PostgreSQL.

6. Сервис управления командами (Match Management Service):

   - Отвечает за создание, редактирование и удаление команд.
   - Хранит информацию о командах в базе данных PostgreSQL.

7. Сервис работы с геоданными (Geolocation Service):

   - Отвечает за работу с геоданными и отображение карты с местоположением площадок.
   - Использует Mapbox API для работы с геоданными.
   - Хранит информацию о геоданных в базе данных PostgreSQL(PostGIS|MongoDB).

8. Кэширующий сервис (Caching Service):
   - Отвечает за кэширование данных и ускорение работы сервиса.
   - Использует Redis для кэширования данных.

## API

1. Регистрация и аутентификация пользователей:
   - `POST` **/auth/register** - создание новой учетной записи пользователя
   - `POST` **/auth/jwt/login** - вход пользователя в систему
   - `POST` **/auth/jwt/logout** - выход пользователя из системы
     </br>
2. Управление доступом на базе пользователей и групп:

   - `GET` **/users/me** - получение информации о текущем пользователе
   - `GET` **/users/{id}** - получение информации о конкретном пользователе
   - `PATCH` **/users/me** - обновление информации о текущем пользователе
   - `PATCH` **/users/{id}** - обновление информации о конкретном пользователе (доступно только администраторам)
   - `DELETE` **users/{id}** - удаление пользователя (доступно только администраторам)
     </br>

3. Поиск и фильтрация:
4. Просмотр информации о спортивных площадках:
5. Бронирование:
6. Отзывы и рейтинги:
7. Управление спортивными площадками:
8. Управление командами:
9. Управление матчами:

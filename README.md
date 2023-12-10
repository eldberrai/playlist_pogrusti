## **Телеграмм-бот для работы с плейлистами**

В рамках нашего проекта мы хотим создать телеграмм бот, который интегрируется с аккаунтом пользователя на yandex music , имеющий следующие функции:
1. Перенос музыки c платформ Spotify и Vk Music в yandex music
2. Создание новых плейлистов, аналогичных тем, что были на начальной платформе. 

*На настоящий момент планируется поддержка двух платформ, с которых можно будет переносить плейлисты на yandex music.

Данные функции будут работать посредством реализации данного алгоритма:

1. Вход в пользователя в систему на стартовой музыкальной платформе
2. Получение песен из плейлистов со стартовой платформы в виде списка (этап скрэпинга).
3. Перенос музыки с другой платформы в yandex music и при желании пользователя создание новых плейлистов, идентиичных тем, что были на стартовой платформе


Разделение обязанностей:
1. Киреев Алексей - изучение api сервиса yandex music, подготовка процесса интеграции новой перенесенной музыки в аккаунт пользователя в yandex music и механизма создания плейлистов.
2. Корнилова Ульяна - скрэппинг данных с платформы Vk Music, осуществление извлечения песен и плейлистов из медиатеки в виде списка
3. Сидоренко Марина - работа над телеграм-ботом
4. Мирзоева Алина - скрэппинг данных с платформы Spotify, осуществление извлечения песен и плейлистов из медиатеки в виде списка


**КТ-2**

Для Spotify:

Что уже работает?

 1. Получить список песен по названию плейлиста в медиатеке пользователя
 2. Получить список песен из плейлиста по ссылке
 3. По списку песен, переданном пользователем в бот, бот ищет каждую из песен и добавляет их в плейлист с желаемым названием.

Что нужно доработать?

 1. Добавить логгирование для каждого этапа
 2. Сейчас client_id и secret_id хранятся в файле типа .env: дальше надо подумать оптимальное ли это решениеё
 3. Возможно, стоит улучшить функцию поиска и предусмотреть случаи, когда данной песни нет в Spotify
 4. Политика Spotify разрешает полный доступ к API для учебных проектов с одним ограничением: чтобы человек мог пользоваться приложением с этим client_id и secret_id автор приложения должен добавить аккаунт пользователя в список на сайте https://developer.spotify.com. Мы читали о том, как получить полный доступ, но там нужно предоставить Spotify достаточно много данных о своем проекте и к тому же на сайте явно написано, что если проект учебный, то такой доступ не дадут. В нашей ситуации такой доступ  можно дать 25 пользователям, мы думаем, что этого вполне хватит для демонстрации работы бота и защиты проекта, но если что, готовы эту часть обсудить на консультации :)

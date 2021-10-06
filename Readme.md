## Table Users

| id | chanel_name   | password                         | key_auth | last_session                     |
|----|---------------|----------------------------------|----------|----------------------------------|
| 1  | Tester        | 5f4dcc3b5aa765d61d8327deb882cf99 | 2190     | c5bb14929981128d5de0da99288ac868 |

В данной таблице kay_auth - типа дфухвакторная аутентификация. Далее, last_session - это ключ, создаваемый из случайных символов и прогоняемый через любую хэш функцию (в данном случаем просто важно повысить уникальность ключа, так что его можно хоть через md4 или sha1 создавать), он нужен для того, чтобы после входа мы на стороне клиента/приложения запехнули его в cookie или localsorage и при перемещении по сайту проверяли, авторизован ли юзер. Этот ключ будет создаваться каждый раз при авторизации. 

## Table About Users
| user_id | about  | on_vk         | on_fb         | on_tw                | on_sputinik        |
|---------|--------|---------------|---------------|----------------------|--------------------|
| 1       | Tester | vk.com/tester | fb.com/tester | twitter.com/max_katz | Error, im a teapot |

## Table of videos
| user_id | path_to_video                 | name          | about                                               | category            |
|---------|-------------------------------|---------------|-----------------------------------------------------|---------------------|
| 1       | "home/project/one/video.webp" | "First Video" | "\<p\>A pretty about text written by CKeditor<\/p>" | Blog/id_of_category |

## Table of Subscribers
| from_id | to_id | when_started  |
|---------|-------|---------------|
| 1       | 101   | 1633362036820 |

when_started - поле с типом int, обозначает время, когда человек подписался. В момент отписки строка просто удаляется.

## Table of emotions
| user_id | id_of_liked_content | type_of_content     | emotion |
|---------|---------------------|---------------------|---------|
| 1       | 12121212            | video/comment/reply | 1/0     |

Эмоция может быть только 1 или 0 т.к. мы добавляем запись в эту таблицу только после нажатия на лийк/дизлайк.

# На чем мы это реализуем (Backend сайта):
## Если на GoLang:
- Gin Gonic - Web Framework общего назначения
- GORM - ORM для MySQL/SQLite или Postgresql
- Hare - встраиваямая БД на чистом Go где каждая таблица - отдельный JSON-файл
- FastCache - быстрый кэш в ОЗУ

## Если на Python 3
- Flask (+Flask-Admin, +Flask-REST) - Web Framework 
- Peewee ORM - быстрая ORM, работает со могими БД. 

## Если на PHP
- Fat-Free/Flight PHP - web frameworks
- Smarty - движок шаблонов
- RedBean - хорошая ORM

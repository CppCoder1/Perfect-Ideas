## Table Users

| id | chanel_name   | password                         | key_auth | last_session                     |
|----|---------------|----------------------------------|----------|----------------------------------|
| 1  | Tester        | 5f4dcc3b5aa765d61d8327deb882cf99 | 2190     | c5bb14929981128d5de0da99288ac868 |

## Table About Users
| user_id | about  | on_vk         | on_fb         | on_tw                | on_sputinik        |
|---------|--------|---------------|---------------|----------------------|--------------------|
| 1       | Tester | vk.com/tester | fb.com/tester | twitter.com/max_katx | Error, im a teapot |

## Table of videos
| user_id | path_to_video                 | name          | about                                            | category            |
|---------|-------------------------------|---------------|--------------------------------------------------|---------------------|
| 1       | "home/project/one/video.webp" | "First Video" | "\<p\>A pretty about text written by CKeditor<\/p>" | Blog/id_of_category |

## Table of Subscribers
| from_id | to_id | when_started  |
|---------|-------|---------------|
| 1       | 101   | 1633362036820 |

## Table of emotions
| user_id | id_of_liked_content | type_of_content     | emotion |
|---------|---------------------|---------------------|---------|
| 1       | 12121212            | video/comment/reply | 1/0     |

Эмоция может быть только 1 или 0 т.к. мы добавляем запись в эту таблицу только после нажатия на лийк/дизлайк.

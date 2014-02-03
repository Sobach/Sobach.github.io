---
layout: post
category : research
title: 'Ко дню рождения смайла'
tags : [twitter, research]
---

Утром 19 сентября 1982 года Скотт Фалман опубликовал в университетской BBS'ке такое сообщение:

    ----------------------------
    19-Sep-82 11:44 Scott E Fahlman :-)
    From: Scott E Fahlman <Fahlman at Cmu-20c>
    I propose that the following character sequence for joke markers:
    :-)
    Read it sideways. Actually, it is probably more economical to mark
    things that are NOT jokes, given current trends. For this, use
    :-(

    ----------------------------

[оригинал того сообщения](http://www.cs.cmu.edu/~sef/Orig-Smiley.htm)

Различные варианты использования стандартной типографики для изображения эмоций предлагались и ранее:

* А.Бирсом в 1912 году:

> "an improvement in punctuation – the snigger point, or note of cachinnation: it is written 
thus \\\_\_\_/! and presents a smiling mouth" ([Wikipedia](http://en.wikipedia.org/wiki/Emoticon#cite_note-5));

* В.Набоковым в 1969 году:

> "I often think there should exist a special typographical sign for a smile -- some sort of 
concave mark, a supine round bracket, which I would now like to trace in reply to your question" 
([The New York Times](http://lib.ru/NABOKOW/Inter11.txt_with-big-pictures.html)).

Однако на сегодняшний день именно 19 сентября является "официальным" днем рождения смайла. Приятно, что сам 
я -- хоть и всего на 1 день -- но старше смайла.

<!--break-->

За 31 год "джентельменский набор" смайлов заметно расширился по сравнению с "двоеточием-дефисом-скобкой" и довольно 
глупо выглядят рассуждения о том, что без смайлов общение в сети было бы совсем другим... (ваш КО, да). 
Поэтому я опускаю всю патетику по теме и перехожу сразу к результатам несерьезного (как и требуют обстоятельства) 
исследования под условным названием "пара слов про смайлы в московском твиттере".

С 1 по 31 августа с помощью [Twitter filter stream](https://dev.twitter.com/docs/api/1.1/post/statuses/filter) 
я старательно собирал все твиты, о которых было известно, что их писали в Москве и ближайших окрестностях. 
Всего получилось около 1 млн твитов (999&nbsp;620). Из них 20,7% содержали что-то похожее на смайлы 
(распознавание смайлов было сделано с помощью регулярных выражений).

В процессе сбора встретилось много всего, в том числе, и странного (может кто-то сможет обогатить свой смайло-набор):

![Smiles cloud](/media/smile_cloud.png)

## Корреляции-результаты-выводы

Смайлы -- это перенесенные на экран эмоции, а эмоции -- это прежде всего межличностное общение. 
Можно предположить, что в face-to-face твитах смайлов должно быть больше. Эта гипотеза подтверждается. 
65% твитов со смайлами содержат в тексте упоминания других пользователей (mention) -- т.е., речь идет 
либо о персональном обращении, ответе (reply), либо ретвите (retweet). Среди сообщений без смайлов упоминания 
пользователей встречаются лишь в 41% случаев.

![Smiles-mentions correlation](/media/smiles_mentions.png)

За 31 год смайлов придумано великое множество. Соответствующая страница 
[Википедии](http://en.wikipedia.org/wiki/List_of_emoticons), помимо "стандартного" набора демонстрирует потрясающие 

* `=:o]` -- Билл Клинтон;
* `~(_8^(I)` -- Гомер Симпсон;
* `@}-;-'---` -- розочка.
 
Часть смайлов можно смело отнести к [ASCII-art](http://ru.wikipedia.org/wiki/ASCII-%D0%B3%D1%80%D0%B0%D1%84%D0%B8%D0%BA%D0%B0).
Тем не менее, в реальности все эти "интересности" практически не используются. Более того -- даже предложенный Фалманом
вариант из двоеточия, тире и скобки и то оказывается слишком сложным для скоротечной твиттер-коммуникации.
Наиболее популярный вариант смайла -- скобка. Просто скобка. Так хорошо -- ")", а вот так -- "(" -- плохо.
Для определения градаций эмоциональности количество скобок увеличивается. Большинству вполне хватает одной, двух
или трех скобок. Но встречаются и уникумы. В собранной подборке есть один твит с 66-ю "негативными" скобками и один --
со 111-ю (sic!) "позитивными". Не забываем, что лимит на количество знаков в твите -- 140. Так что пока есть, куда расти.
В итоге, для передачи эмоций твиттер-москвичам в 56% случаев хватает самых обычных скобок. Визуально это выглядит
вот так (площадь прямоугольника соответствует "встречаемости" смайла):

![Smiles treemap](/media/smile_treemap.png)

Обратили внимание на еще одну интересную особенность? Позитивные смайлы не просто преобладают над негативными, 
они напрочь "давят" все остальные классы эмоций. Почему так? Может быть людям до сих пор кажется странным подкреплять
свой _действительно_ негативный текст "смайлом"? Или просто соцсети становятся территорией позитива? Я склоняюсь к
первой гипотезе.

Наибольший накал эмоций в московском твиттере наблюдается вечером и ночью: с 18:00 до 01:00.

![Smiles by hour](/media/smile_hour.png)

Причем это касается всех типов смайлов. Графики нейтральных и удивленных смайлов не такие плавные из-за относительно 
малого количества наблюдений. Думается, если собрать побольше статистики, форма гистограммы приблизится к позитивным
и негативным.

По дням недели тоже особой разницы незаметно. Чуть большие показатели четверга, пятницы и субботы объясняются тем,
что в августе этих дней недели было по 5 (остальных -- по 4).

![Smiles by weekday](/media/smile_weekday.png)

Если же смотреть на весь месяц целиком, то общий эмоциональный настрой повышается к концу месяца. Это видно и
по позитивным смайлам, и по негативным. И там, и там 29-30 августа смайлов "натвитили" больше всего.
Видимо, тут сошлось сразу все: конец недели, конец месяца, конец лета и начало осени.

![Positive days in august](/media/smile_positive_calendar.png)

![Negative days in august](/media/smile_negative_calendar.png)

И, конечно, раз уж я ограничил поиски смайлов Москвой было бы глупо не посмотреть, где в городе самые "эмоциональные"
места. С центром города все понятно -- если ориентироваться на соцсети, жизнь в Москве есть только в пределах
Бульварного кольца. Но на графике ниже видно еще несколько "горячих" точек.

![Moscow smiles density map](/media/smile_map.png)

* Район Щукино -- Полежаевской -- Октябрьского поля. Есть у меня подозрения, но пока не буду озвучивать.
* Чертаново -- Новоясеневская. Казалось бы.
* Шереметьево -- как раз здесь все понятно, аэропорт, чекин, смайлик.
 
Вот в общем-то, и все. На ценность и глобальность выводов весь этот текст не претендует. Просто к празднику, просто
"рисёч". Тем, кто хочет более серьезного чтения, научности и культурологичности предлагаю почитать текст 
["Emoticon Style: Interpreting Differences in Emoticons Across Cultures"](http://www.aaai.org/ocs/index.php/ICWSM/ICWSM13/paper/view/6132/6386).

Всех с праздником, всем привет! ;o)
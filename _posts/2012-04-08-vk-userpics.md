---
layout: post
category : research
title: 'Гадание по юзерпику: инструментальный аспект'
tags : [vkontakte, research, audience]
---

Сегодня мы поговорим о том, как получать в 1,5-2 раза больше данных о наших любимых пользователях социальных сетей при незначительном росте трудозатрат.

SMM-щикам и тем, кто пытается что-то изучать в социальных сетях при анализе аудитории очень хочется оперировать традиционными социально-демографическими показателями. И хотя интернет позволят оперировать поведенческими и стилевыми данными аудитории, рано или поздно разговор вернется к соцдему. Однако пользователи часто не готовы раскрывать свой возраст, а иногда – даже и пол первому встречному (стесняются?). Так, например, в социальной сети ВКонтакте информация о возрасте доступна только для 18% профилей. Хотя показать себя любимого на юзерпике готово гораздо больше народу. Притом, что пользователи часто используют в качестве аватарки свою собственную фотографию, часть скрытой информации можно попытаться восстановить "на глазок". Такой вариант подходит, когда число профилей исчисляется десятками. В противном случае трудозатраты растут непропорционально результату. И тут нам на помощь, как обычно, приходят роботы.

<!--break-->

Сервисы распознавания лиц сегодня не только предлагают поиск человека на фото, но и пытаются определить основные социально-демографические характеристики найденных лиц. В частности, сервис Face.com недавно анонсировал функционал определения возраста по лицу. Мы попытались определить, насколько эти нововведения могут улучшить качество собираемой информации на больших массивах.

Для эксперимента из всех аккаунтов ВКонтакте случайным образом было выбрано 100000 профилей. 20% из них оказались заблокированы и в дальнейшем анализе участия не принимали. Через публичный API, не требующий разрешения от пользователя, была собрана информация о состоянии профиля (заблокирован или активен), поле, возрасте, наличии юзерпика. Далее полученные аватарки были "скормлены" Face.com для определения половозрастных характеристик по фотографии. Дальнейший анализ включал в себя оценку количества добавляющейся информации и качество получаемых таким образом данных.

Для оценки результативности предлагаемого метода мы сравнили долю пользователей с известным возрастом до и после использования сервиса Face.com. Приоритет, в любом случае, отдавался данным, полученным из профиля ВКонтакте. Если соответствующие данные отсутствовали, брались результаты распознавания лиц. В итоге, процент профилей с доступными возрастными данными увеличился с 26,7% до 47%. Фактически, появилась информация о вдвое большем количестве профилей. На наш взгляд, это весьма существенный прирост.

Однако ценность этого прироста пока сомнительна, так как неизвестно качество добавленной информации. Для оценки качества собираемых с помощью сервиса распознавания лиц данных мы отобрали профили, для которых был определен как возраст по профилю ВКонтакте, так и по юзерпику. Получилось около 11 тысяч наблюдений. Гистограммы двух возрастных распределений вроде бы выглядят похоже.

![Гистограмма распределений предсказанных и указанных возрастов пользователей](/media/vk_upics.jpg)

Гистограмма возрастных распределений ВКонтакта и Face.com
 
Стоит обратить внимание на наличие «слишком ранних» возрастных групп в данных Face.com (от нуля лет – видимо, ставим дите на аватарку) и слишком больших «ВКонтактных» возрастов (90 и более лет – шутим или правда есть такие пользователи?). В остальном – «на глазок» - все более-менее похоже, хотя тесты говорят об обратном. Средние значения для возрастов не пересекаются (на 95% доверительном интервале). Коэффициент корреляции равен 0,36 (уровень значимости 0,01), что, в общем-то, неплохо, но явно недостаточно для взаимозаменяемости показателей. Добавление фильтров по возрасту (от 5 до 70 лет) – чтобы ограничить выбросы – особого эффекта не приносит. Корреляция растет только до 0,39. Не спасает и отбор только тех наблюдений, где возраст на фото был распознан с высокой долей вероятности (от 50 и выше) – корреляция 0,4.

Тем не менее, полностью игнорировать новый источник информации о пользователях не стоит. Все-таки почти двукратное увеличение информации (при сомнительном, правда, качестве). С другой стороны, кто мешает пользователям указать неправильный возраст в своем профиле? И каким цифрам после этого верить? Кроме того, будем помнить, что в данном случае профили пользователей выбирались абсолютно случайно. В случае решения реальной исследовательской задачи (например, аудиторный анализ сообществ в соцсети) профили пользователей могут быть «более живыми» и непротиворечивыми. В ближайших сериях попытаемся это проверить.
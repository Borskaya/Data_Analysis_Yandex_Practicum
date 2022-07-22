# Исследование перспективности тарифов.ipynb
Вы аналитик компании «Мегалайн» — федерального оператора сотовой связи. Клиентам предлагают два тарифных плана: «Смарт» и «Ультра». Чтобы скорректировать рекламный бюджет, коммерческий департамент хочет понять, какой тариф приносит больше денег.

Вам предстоит сделать предварительный анализ тарифов на небольшой выборке клиентов. В вашем распоряжении данные 500 пользователей «Мегалайна»: кто они, откуда, каким тарифом пользуются, сколько звонков и сообщений каждый отправил за 2018 год. Нужно проанализировать поведение клиентов и сделать вывод — какой тариф лучше.

Описание тарифов

Тариф «Смарт» Ежемесячная плата: 550 рублей Включено 500 минут разговора, 50 сообщений и 15 Гб интернет-трафика Стоимость услуг сверх тарифного пакета: минута разговора: 3 рубля сообщение: 3 рубля 1 Гб интернет-трафика: 200 рублей

Тариф «Ультра» Ежемесячная плата: 1950 рублей Включено 3000 минут разговора, 1000 сообщений и 30 Гб интернет-трафика Стоимость услуг сверх тарифного пакета: минута разговора: 1 рубль сообщение: 1 рубль 1 Гб интернет-трафика: 150 рублей

Примечание: «Мегалайн» всегда округляет секунды до минут, а мегабайты — до гигабайт. Каждый звонок округляется отдельно: даже если он длился всего 1 секунду, будет засчитан как 1 минута.

Для веб-трафика отдельные сессии не считаются. Вместо этого общая сумма за месяц округляется в бо́льшую сторону. Если абонент использует 1025 мегабайт в этом месяце, с него возьмут плату за 2 гигабайта.

Цель исследования — проверить две гипотезы:

Средняя выручка пользователей тарифов «Ультра» и «Смарт» различаются;
Средняя выручка пользователей из Москвы отличается от выручки пользователей из других регионов.
Ход исследования

Данные о клиентах получены из файла /datasets/data.csv. О качестве данных ничего не известно. Поэтому перед проверкой гипотез будет проведен обзор данных.

Проверим данные на ошибки и оценим их влияние на исследование. В процессе предобработки мы исправим критичные ошибки ради получения корректного результата исследования.

Исследование пройдёт в три этапа:

Обзор данных Предобработка данных. Проверка гипотез.

Ход исследования

Данные о клиентах получены из файлов /datasets/calls.csv, /datasets/internet.csv, /datasets/messages.csv, /datasets/tariffs.csv, /datasets/users.csv. О качестве данных ничего не известно. Поэтому перед проверкой гипотез будет проведен обзор данных.

Проверим данные на ошибки и оценим их влияние на исследование. На этапе предобработки мы исправим критичные ошибки ради получения корректного результата исследования. Непосредственно перед проведением исследования сделаем все необходимые расчеты, которые используем в процессе проверки выдвинутых гипотез.

Исследование пройдёт в четыре этапа:

Изучение данных.
Подготовка данных.
Анализ данных.
Проверка гипотез.

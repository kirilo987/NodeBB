# ![NodeBB](public/images/sm-card.png)

[![Workflow](https://github.com/NodeBB/NodeBB/actions/workflows/test.yaml/badge.svg)](https://github.com/NodeBB/NodeBB/actions/workflows/test.yaml)
[![Coverage Status](https://coveralls.io/repos/github/NodeBB/NodeBB/badge.svg?branch=master)](https://coveralls.io/github/NodeBB/NodeBB?branch=master)
[![Code Climate](https://codeclimate.com/github/NodeBB/NodeBB/badges/gpa.svg)](https://codeclimate.com/github/NodeBB/NodeBB)
[![](https://dcbadge.limes.pink/api/server/S2aAweHwDc?style=flat)](https://discord.gg/S2aAweHwDc)

[**Форумне програмне забезпечення NodeBB**](https://nodebb.org) працює на базі Node.js та підтримує бази даних Redis, MongoDB або PostgreSQL. Воно використовує вебсокети для миттєвої взаємодії та сповіщень у реальному часі. NodeBB поєднує в собі найкраще від сучасного вебу: обговорення в режимі реального часу, адаптивність для мобільних пристроїв та повноцінні інтерфейси RESTful API для читання й запису, залишаючись при цьому вірним класичному формату форумів (bulletin board) &rarr; категоріальна ієрархія, локальні облікові записи користувачів та асинхронний обмін повідомленнями.

Сам по собі NodeBB містить «спільне ядро» (common core) базових функцій, тоді як додаткові можливості та інтеграції реалізуються за допомогою сторонніх плагінів.

### [Спробувати зараз](//try.nodebb.org) | [Документація](//docs.nodebb.org)

## Скріншоти

Рушій тем оформлення NodeBB є надзвичайно гнучким і не обмежує ваші дизайнерські рішення. Перегляньте кілька прикладів стилізованих встановлень на скріншотах нижче:

[![](http://i.imgur.com/VCoOFyqb.png)](http://i.imgur.com/VCoOFyq.png)
[![](http://i.imgur.com/FLOUuIqb.png)](http://i.imgur.com/FLOUuIq.png)
[![](http://i.imgur.com/Ud1LrfIb.png)](http://i.imgur.com/Ud1LrfI.png)
[![](http://i.imgur.com/h6yZ66sb.png)](http://i.imgur.com/h6yZ66s.png)
[![](http://i.imgur.com/o90kVPib.png)](http://i.imgur.com/o90kVPi.png)
[![](http://i.imgur.com/AaRRrU2b.png)](http://i.imgur.com/AaRRrU2.png)
[![](http://i.imgur.com/LmHtPhob.png)](http://i.imgur.com/LmHtPho.png)
[![](http://i.imgur.com/paiJPJkb.jpg)](http://i.imgur.com/paiJPJk.jpg)

Наша мінімалістична тема «Harmony» дозволить вам почати роботу одразу, без необхідності мати досвід програмування.

![Візуалізація встановленого форуму NodeBB на настільних та мобільних пристроях](https://user-images.githubusercontent.com/923011/228570420-2a4db745-b20d-474a-a571-1b59259508ef.png)

## Як стежити за проєктом / зробити свій внесок?

* Якщо ви розробник, ви можете вільно переглядати вихідний код і надсилати запити на злиття (pull requests). Ми також маємо широкий вибір [плагінів](http://community.nodebb.org/category/7/nodebb-plugins), які стануть чудовою відправною точкою для вивчення кодової бази.
* Якщо ви designer, [NodeBB потребує тем](http://community.nodebb.org/category/10/nodebb-themes)! Система тем NodeBB дозволяє розширювати базові шаблони, а також стилізувати їх за допомогою SCSS або CSS. Базова тема NodeBB використовує [Bootstrap 5](http://getbootstrap.com/) як фронтенд-інструментарій.
* Якщо ви знаєте інші мови, окрім англійської, ви можете допомогти нам з перекладом NodeBB. Для інтернаціоналізації ми використовуємо [Transifex](https://explore.transifex.com/nodebb/nodebb/).
* Будь ласка, не забудьте поставити **лайк**, **підписатися** та **додати наш репозиторій у вибране (star)**! Приєднуйтесь до нашої зростаючої [спільноти](http://community.nodebb.org), щоб залишатися в курсі останніх новин розробки NodeBB.

## Вимоги

Для роботи NodeBB необхідно встановити таке програмне забезпечення:

* Версія Node.js не нижче 22 ([інструкції зі встановлення/оновлення](https://github.com/nodesource/distributions))
* MongoDB версії 5 або вище **або** Redis версії 7.2 або вище
* Якщо ви використовуєте [кластеризацію](https://docs.nodebb.org/configuring/scaling/), вам потрібно встановити та налаштувати Redis.
* nginx версії 1.3.13 або вище (**тільки якщо** ви плануєте використовувати nginx для проксування запитів до NodeBB)
* (Необов'язково) [Docker](https://docs.docker.com/get-docker/) для розгортання в контейнерах

> Процес встановлення залежить від операційної системи. Будь ласка, перейдіть за посиланнями на офіційну документацію вище.

## Встановлення

[Будь ласка, зверніться до документації зі встановлення для конкретної платформи](https://docs.nodebb.org/installing/os).
Якщо встановлення виконується у хмарі (або за допомогою Docker), [дивіться документацію зі встановлення у хмарі](https://docs.nodebb.org/installing/cloud/).

## Огляд налаштування для розробки

> NodeBB використовує налаштування на базі CLI (інтерфейсу командного рядка) і не запускається за допомогою стандартної команди `npm start`.

Ви можете запустити NodeBB локально двома способами:

### Варіант 1: Локальне (нативне) встановлення (рекомендовано для новачків та контриб'юторів)

Цей підхід допоможе вам зрозуміти, як влаштований NodeBB зсередини.

**Основний процес:**
1. Клонуйте репозиторій ```` https://github.com/NodeBB/NodeBB.git ````
2. Запустіть скрипт налаштування ```` cd NodeBB ```` ```` ./nodebb setup ````
3. Запустіть додаток  ```` ./nodebb start ````

**Під час налаштування ви вкажете конфігурацію для:**
   - Бази даних (MongoDB / Redis)
   - Облікового запису адміністратора
   - Порту (за замовчуванням: 4567)

### Варіант 2: Встановлення через Docker (швидке та ізольоване)

> Вимагає встановленого Docker: https://docs.docker.com/get-docker/

Запустіть:

```bash
docker-compose up
```

Це запустить NodeBB разом із необхідними сервісами за адресою: ```` http://localhost:4567 ````

**Для отримання детальнішої інформації дивіться: https://docs.nodebb.org**

## Захист NodeBB

Важливо переконатися, що ваші сервери NodeBB та баз даних захищені. Зверніть увагу на такі моменти:

1. Хоча деякі дистрибутиви налаштовують Redis із більш суворими обмеженнями, за замовчуванням Redis прослуховує всі інтерфейси. Це особливо небезпечно, якщо сервер відкритий для публічного доступу. Кілька порад:
    * Встановіть `bind_address` на `127.0.0.1`, щоб обмежити доступ лише локальною машиною
    * Використовуйте `requirepass`, щоб захистити Redis паролем (бажано довгим)
    * Ознайомтеся з розділом [Безпека Redis (Redis Security)](http://redis.io/topics/security)
2. Використовуйте `iptables`, щоб захистити свій сервер від небажаних відкритих портів. В Ubuntu утиліта `ufw` надає зручніший інтерфейс для роботи з `iptables`.
    * Наприклад: якщо ваш NodeBB працює через проксі-сервер, жодні порти не повинні бути відкриті, крім 80 (та, можливо, 22 для доступу через SSH)


## Оновлення NodeBB

Детальні інструкції з оновлення наведені у розділі [Оновлення NodeBB (Upgrading NodeBB)](https://docs.nodebb.org/configuring/upgrade/)

## Ліцензія

NodeBB ліцензується на умовах **GNU General Public License v3 (GPL-3)** (http://www.gnu.org/copyleft/gpl.html).

Цікавить субліцензійна угода для використання NodeBB у комерційному чи обмеженому середовищі? Зв'яжіться з нами за адресою sales@nodebb.org.

## Більше інформації / Посилання

* [Демоверсія](https://try.nodebb.org)
* [Спільнота розробників](http://community.nodebb.org)
* [Документація та інструкції зі встановлення](https://docs.nodebb.org)
* [Допомогти з перекладом NodeBB](https://explore.transifex.com/nodebb/nodebb/)
* [Блог NodeBB](https://nodebb.org/blog)
* [Преміумхостинг для NodeBB](https://www.nodebb.org/ "NodeBB")
* Неофіційна IRC-спільнота &ndash; канал `#nodebb` на Libera.chat
* [Стежте за нами в Twitter](http://www.twitter.com/NodeBB/ "NodeBB Twitter")
* [Поставте нам лайк на Facebook](http://www.facebook.com/NodeBB/ "NodeBB Facebook")

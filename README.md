# Sonar 1C BSL Public

Direct Plugin Chat   | SonarQube-Russian-Chat |
:-------------------:|:----------------------:|
[![Gitter Chat https://gitter.im/silverbulleters/sonar-1c-bsl-public](https://badges.gitter.im/silverbulleters/sonar-1c-bsl-public.svg)](https://gitter.im/silverbulleters/sonar-1c-bsl-public)            | [![Gitter Chat https://gitter.im/sonarqube-ru/public](https://badges.gitter.im/Join-Chat.svg)](https://gitter.im/sonarqube-ru/public)           |


## English

SonarQube for 1C:Enterprise support calculate metrics on 1C:BSL lang and for 1C:Querry lang on:

* duplcation
* complexity
* cognitive complexity
* code coverage
* techdebt

contains:

* over 150 rules to check - current list publuished on our sonarqube server https://sonar.silverbulleters.org/coding_rules#languages=bsl (you need a GitHub account to login)

this is public repository and page for

* main description of plugin
* request checks via Vanessa Torpedo 
* release anonsements
* social activity for SonarQube Russia

english landing page - [Vanessa Torpedo](https://silverbulleters.org/sonarqube_eng)

## Russian

публичный репозиторий для заказа проверок продукта **Vanessa Torpedo**

* список текущих проверок можно посмотреть тут https://sonar.silverbulleters.org/coding_rules#languages=bsl 
* коммерческие контакты - `b2b@silverbulleters.org` 
* `+7(499)346-7019` и '8-800-100-1305'

### Функциональность (для НЕ понимающих)

SonarQube для 1С поддерживает

* расчёт метрик качества всего проекта с указанием конкретной строки
  * на дублирование
  * на запутанность
  * на ошибки, критические баги и просто недочёты
  * на замечания по стандартам ИТС, по Вашим внутренним стандартам и дополнительно по стандартам разработанным командой **SilverBulleter's**  
  * на расчёт покрытия кода тестами и проверками поведения (с помощью проектов VanessaBehavior и xUnitFor1C)
  * на предмет **когнитивной сложности** (https://blog.sonarsource.com/cognitive-complexity-because-testability-understandability/)
  
а также

* управление приоритетами исправлений
* управление задачами на исправление

и еще многое другое - более подробно стоит изучить

* демонстрационные репозиторий https://github.com/silverbulleters/sonar-bsl-demo
* документацию на русском https://sonar-russian.silverbulleters.org/

## Техническая информация и план релизов

* поддерживаемые версии SonarQube - **6.1, 6.2, 6.3, 6.4, 6.5**
* в состав продукта входят:
  * **sonar-bsl-plugin-VERSION.jar** - плагин для установки в каталог расширений SonarQube
  * **sonar-bsl-plugin.pdf** - пользовательская документация
  * **AST-Toolkit.jar** - помошник написания своих правил на базе Abstract Systax Tree и XPath выражений (смотри скриншот ниже)
  * **sonar-graphite-extension.jar** - расширение для 1С:Graphite в режиме онлайн проверки и в режиме подключения к серверу SonarQube
  
## Параметры производительности

версия 1.4.2 - на контуре UAT `4 CPU 8 RAM SSD`, **анализ с нуля - первый старт**

| ERP 2.1 | БП КОРП 3 | ЗУП КОРП 3 |
|---------|-----------|------------|
| 37 минут - 5.5+ миллиона строк | 25 минут - 3.5+ миллиона строк | 10 минут - 2.1+ миллиона строк|

Последующие анализы проходят быстро - больше помещений: быстрей анализ.
Как ориентир - `30.000 строк кода - 9 секунд.`

В каждом релизе `Sonar BSL Plugin` обязательно идет улучшение производительности. 
Следите за новостями - нажав кнопку **Watch**

### Рекомендуемые параметры для ERP редакция 2.X (2.1, 2.2, 2.4.1)

* сервер запуска анализа - `4 vCPU c 16Gb RAM SSD`
* портал хранения данных - `4 VCPU 16Gb RAM HDD`

для остальных конфигураций можно меньше, например 

### для БСП достаточно

* сервер запуска анализа - `1 vCPU 2Gb RAM SATA`
* портал хранения данных - `2 vCPU 4GB RAM SATA`

## Компоненты SonarQube

* опционально: Хранилище 1С с подключенным проектом GITSYNC http://oscript.io/library/package/gitsync
* Git репозиторий - как хранилище исходных кодов и авторов
* сервер CI - любой с поддержкой SonarRunner http://docs.sonarqube.org/display/SONAR/Analyzing+Source+Code
  * http://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner
* портал хранения данных анализа - http://docs.sonarqube.org/display/SONAR/Installing+the+Server

более подробно тут https://github.com/silverbulleters/sonar-bsl-demo

### Поддерживаемые языки

* **BSL** - язык платформы 1С для программирования бизнес-логики
* **SDBL** - язык запросов 1С для описания способов выборки данных 
* **Metadata** - XML описание метаданных (для формата выгрузки из Конфигуратора 1С)
* `в релизе 1.5` **MDO** - концептуальное описание бизнес-модели, будет использоваться для оценки качества моделирования ([пример такого файла](https://github.com/1C-Company/dt-demo-configuration/blob/master/DemoConfDT/src/Documents/%D0%97%D0%B0%D0%BA%D0%B0%D0%B7/%D0%97%D0%B0%D0%BA%D0%B0%D0%B7.mdo))

### Технологии (проверены в связке с 1С)

* Сервера управления исходными кодами
  * GitHub (включая GitHub Enterprise)
  * GitLab (включая GitLab EE)
  * Bitbucket (включая Bitbucket Server)
  * Visual Studio Team Services (TFS)

* Сервера сборок
  * Jenkins 
  * Visual Studio Team Services (TFS)
  * GitLab CI
  * TeamCity
  * Bamboo

для репликации 1С кода из хранилища 1С используется проект [GitSync](https://github.com/oscript-library/gitsync) или продукт [Vanessa Tools для VSTS](https://silverbulleters.org/vannessavsts)

### Дополнительные ссылки

Вы можете установить SonarQube с русским интерфейсом для своего проекта на C#, Java, Python, Ruby и посмотреть в реальности как это выглядит полностью бесплатно, так как проект является открытым с небольшим объемом коммерческих плагинов.

* наше **открытое** расширение для поддержки русскоязычных пользователей https://github.com/silverbulleters/sonar-l10n-ru
* наше **открытое** расширение для Visual Studio Code для онлайн исправления замечаний https://github.com/silverbulleters/sonarqube-inject-vsc
* Использования для C++ и PVC Studio https://habrahabr.ru/company/pvs-studio/blog/315422/
* Вот как это можно сделать на PHP https://habrahabr.ru/post/259149/

для снижения порога вхождения в технологию - посмотрите вебинар http://infostart.ru/webinars/571342/

## Обсуждение продукта на русском

* в чате https://gitter.im/silverbulleters/sonar-1c-bsl-public
* на форуме https://xdd.silverbulleters.org/t/bazovye-veshhi-sonarqube/533
* ответы на базовые вопросы накапливаются [в центре поддержке](http://help.silverbulleters.org/sonar-qube-%D0%BD%D0%B0-%D1%80%D1%83%D1%81%D1%81%D0%BA%D0%BE%D0%BC)

## Публичные видео

* описание способа управления "аутсорсерами* - https://youtu.be/qqjp6MQHf0M
* место **SonarQube BSL Plugin** в производственном процессе -  https://youtu.be/r3belFHR2sw 
* другие инженерные практики

## Архитектурные схемы

![Работа сервера](http://www.plantuml.com/plantuml/proxy?src=https://raw.github.com/silverbulleters/sonar-1c-bsl-public/master/arch/simple.wsd)

![Работа разработчика](http://www.plantuml.com/plantuml/proxy?src=https://raw.github.com/silverbulleters/sonar-1c-bsl-public/master/arch/developer.wsd)

## Скриншоты

### XPath помошник написания своих правил

![](https://xdd.silverbulleters.org/uploads/default/original/1X/3e341da650bcba6ba708f62f39ca039e6db78c69.png)

# Sonar 1C BSL Public

[![Gitter](https://badges.gitter.im/silverbulleters/sonar-1c-bsl-public.svg)](https://gitter.im/silverbulleters/sonar-1c-bsl-public?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

[Vanessa Torpedo](https://www.silverbulleters.org/sonarqube/)

## English

public repository to request checks via Vanessa Torpedo

## Russian

публичный репозиторий для заказа проверок продукта Vanessa Torpedo

список текущих проверок можно посмотреть тут https://sonar.silverbulleters.org/coding_rules#languages=bsl (требуется акаунт GitHub Для входа)

### Функциональность (для НЕ понимающих)

SonarQube для 1С поддерживает

* расчёт метрик качества всего проекта с указанием конкретной строки
  * на дублирование
  * на запутанность
  * на ошибки, критические баги и просто недочёты
  * на замечания по стандартам ИТС, по Вашим внутренним стандартам и дополнительно по стандартам разработанным командой **SilverBullete's**  
  * на расчёт покрытия кода тестами и проверками поведения (с помощью проектов VanessaBehavior и xUnitFor1C)
  
а также

* управление приоритетами исправлений
* управление задачами на исправление

и еще многое другое 

## Параметры производительности

версия 1.0.4. - на контуре UAT `4 CPU 8 RAM SSD`, **анализ с нуля - первый старт**

| ERP 2.1 | БП КОРП 3 |
|---------|-----------|
| 1 час 17 минут - 5.3+ миллиона строк | 29 минут - 3.4+ миллиона строк |

Последующие анализы проходят быстро - больше помещений: быстрей анализ.
Как ориентир - `30.000 строк кода - 15 секунд.`

В каждом релизе `Sonar BSL Plugin` обязательно идет улучшение производительности. 
Следите за новостями - нажав кнопку **Watch**

### Рекомендуемые параметры для ERP редакция 2

* сервер запуска анализа - `4 vCPU 8Gb RAM SSD`
* портал хранения данных - `4 VCPU 16Gb RAM SSD`

для остальных конфигураций можно меньше, например 

### для БСП достаточно

* сервер запуска анализа - `1 vCPU 2Gb RAM SATA`
* портал хранения данных - `2 vCPU 4GB RAM SATA`

## Компоненты SonarQube

* опционально: Хранилище 1С с подключенным поектов GITSYNC http://oscript.io/library/package/gitsync
* Git репозиторий - как хранилище исходных кодов и авторов
* сервер CI - любой с поддержкой SonarRunner http://docs.sonarqube.org/display/SONAR/Analyzing+Source+Code
  * http://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner
* портал хранения данных анализа - http://docs.sonarqube.org/display/SONAR/Installing+the+Server

### Поддерживаемые языки

* **BSL** - язык платформы 1С для программирования бизнес-логики
* **SDBL** - язык запросов 1С для описания способов выборки данных 
* `в перспективе` **MDO** - концептуальное описание бизнес-модели, будет использоваться для оценки качества моделирования ([пример такого файла](https://github.com/1C-Company/dt-demo-configuration/blob/master/DemoConfDT/src/Documents/%D0%97%D0%B0%D0%BA%D0%B0%D0%B7/%D0%97%D0%B0%D0%BA%D0%B0%D0%B7.mdo))

### Технологии (проверены в связке с 1С)

* Сервера управления исходными кодами
  * GitHub (включая GitHub Enterprise)
  * GitLab
  * Bitbucket (включая Bitbucket Server)
  * Visual Studio Team Services (TFS)

* Сервера сборок
  * Jenkins 
  * Visual Studio Team Services (TFS)
  * GitLab CI
  * TeamCity
  * Bamboo

для реликации 1С кода из хранилища 1С используется проект [GitSync](https://github.com/oscript-library/gitsync)

### Дополнительные ссылки

Вы можете установить SonarQube с русским интерфейсом для своего проекта на C#, Java, Python, Ruby и посмотреть в реальности как это выглядит полностью бесплатно, так как проект является открытым с небольшим объемом коммерческих плагинов.

* наше **открытое** расширение для поддержки русскоязычных пользователей https://github.com/silverbulleters/sonar-l10n-ru
* наше **открытое** расширение для Visual Studio Code для онлайн исправления замечаний https://github.com/silverbulleters/sonarqube-inject-vsc
* развивающийся открытый проект для управления качеством требований https://github.com/silverbulleters/sonar-gherkin
* Использования для C++ и PVC Studio https://habrahabr.ru/company/pvs-studio/blog/315422/
* Вот как это можнос сделать на PHP https://habrahabr.ru/post/259149/

## Обсуждение продукта на русском

* в чате https://gitter.im/silverbulleters/sonar-1c-bsl-public
* на форуме https://xdd.silverbulleters.org/t/bazovye-veshhi-sonarqube/533

## Публичные видео

* описание способа управления "аутсорсерами* - https://youtu.be/qqjp6MQHf0M
* место **SonarQube BSL Plugin** в производственном процессе -  https://youtu.be/r3belFHR2sw 
* другие инженерные практики

## Архитектурные схемы

![Работа сервера](http://www.plantuml.com/plantuml/proxy?src=https://raw.github.com/silverbulleters/sonar-1c-bsl-public/master/arch/simple.wsd)

![Работа разработчика](http://www.plantuml.com/plantuml/proxy?src=https://raw.github.com/silverbulleters/sonar-1c-bsl-public/master/arch/developer.wsd)

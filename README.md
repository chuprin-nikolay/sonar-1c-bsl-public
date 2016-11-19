# Sonar 1C BSL Public

[![Gitter](https://badges.gitter.im/silverbulleters/sonar-1c-bsl-public.svg)](https://gitter.im/silverbulleters/sonar-1c-bsl-public?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

[Vanessa Torpedo](https://www.silverbulleters.org/sonarqube/)

## English

public repository to request checks via Vanessa Torpedo

## Russian

публичный репозиторий для заказа проверок продукта Vanessa Torpedo

список текущих проверок можно посмотреть тут https://sonar.silverbulleters.org/coding_rules#languages=bsl (требуется акаунт GitHub Для входа)

### Функционал (для не понимающих)

SonarQube для 1С поддерживает

* расчёт метрик качества всего проекта с указанием конкретной строки
  * на дублирование
  * на запутанность
  * на ошибки и критические баги
  * на замечания по стандартам ИТС и по стандартам
  * на расчёт покрытия кода тестами и проверками поведения
  
а также

* управление приоритетами исправлений
* управление задачами на исправление

и еще многое другое 

### Поддерживаемые языки

* BSL - язык платформы 1С для программирования бизнес-логики
* BSQL - язык запросов 1С для описания способов выборки данных 
* `в перспективе` MDO - концептуальное описание бизнес-модели, будет использоваться для оценки качества моделирования

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

## Архитектурные схемы

![Работа сервера](http://www.plantuml.com/plantuml/proxy?src=https://raw.github.com/silverbulleters/sonar-1c-bsl-public/master/arch/simple.wsd)

![Работа разработчика](http://www.plantuml.com/plantuml/proxy?src=https://raw.github.com/silverbulleters/sonar-1c-bsl-public/master/arch/developer.wsd)

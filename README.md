# Домашнее задание к занятию "11.03 Микросервисы: подходы"

## Задача 1: Обеспечить разработку

Предложите решение для обеспечения процесса разработки: хранение исходного кода, непрерывная интеграция и непрерывная поставка. Решение может состоять из одного или нескольких программных продуктов и должно описывать способы и принципы их взаимодействия.

Решение должно соответствовать следующим требованиям:

Решение должно соответствовать следующим требованиям:
- Облачная система;
- Система контроля версий Git;
- Репозиторий на каждый сервис;
- Запуск сборки по событию из системы контроля версий;
- Запуск сборки по кнопке с указанием параметров;
- Возможность привязать настройки к каждой сборке;
- Возможность создания шаблонов для различных конфигураций сборок;
- Возможность безопасного хранения секретных данных: пароли, ключи доступа;
- Несколько конфигураций для сборки из одного репозитория;
- Кастомные шаги при сборке;
- Собственные докер образы для сборки проектов;
- Возможность развернуть агентов сборки на собственных серверах;
- Возможность параллельного запуска нескольких сборок;
- Возможность параллельного запуска тестов;

**Ответ:**   
Я бы предложил использовать **Gitlab**, так как он удовлетворяет всем требованиям. Можно использовать в облаке, есть система версионирования, возможно использование репозиториев на каждый сервис, запуск сборки через пайплайн с параметрами; с использованием yml-файлов можно привязывать настройки к сборкам, создавать шаблоны для различных конфигураций, использовать несколько конфигураций для сборки из одного репозитория; через параметр parallel в job возможен параллельный запуск нескольких сборок и параллельный запуск тестов.   
Возможно и использование Teamсity, но мне кажется, что использование Gitlab проще.

## Задача 2: Логи

Предложите решение для обеспечения сбора и анализа логов сервисов в микросервисной архитектуре.
Решение может состоять из одного или нескольких программных продуктов и должно описывать способы и принципы их взаимодействия.

Решение должно соответствовать следующим требованиям:
- Сбор логов в центральное хранилище со всех хостов обслуживающих систему;
- Минимальные требования к приложениям, сбор логов из stdout;
- Гарантированная доставка логов до центрального хранилища;
- Обеспечение поиска и фильтрации по записям логов;
- Обеспечение пользовательского интерфейса с возможностью предоставления доступа разработчикам для поиска по записям логов;
- Возможность дать ссылку на сохраненный поиск по записям логов;

**Ответ:**   
Я бы предложил использовать стек **ELK + Filebeat**.   
Elasticsearch используется в качестве центрального хранилища, Filebeat осуществляют сбор логов, Logstash осуществляют доставку и фильтрацию данных, Kibana предоставляет графический интерфейс.

## Задача 3: Мониторинг

Предложите решение для обеспечения сбора и анализа состояния хостов и сервисов в микросервисной архитектуре.
Решение может состоять из одного или нескольких программных продуктов и должно описывать способы и принципы их взаимодействия.

Решение должно соответствовать следующим требованиям:
- Сбор метрик со всех хостов, обслуживающих систему;
- Сбор метрик состояния ресурсов хостов: CPU, RAM, HDD, Network;
- Сбор метрик потребляемых ресурсов для каждого сервиса: CPU, RAM, HDD, Network;
- Сбор метрик, специфичных для каждого сервиса;
- Пользовательский интерфейс с возможностью делать запросы и агрегировать информацию;
- Пользовательский интерфейс с возможность настраивать различные панели для отслеживания состояния системы;

**Ответ:**   
Мое предложение для решения данной задачи использовать **Prometheus + Grafana**.   
Node exporter для сбора метрик, Prometheus для хранения данных, Grafana - пользовательский интерфейс, с возможностью создания и настройки разлчиных дашбордов

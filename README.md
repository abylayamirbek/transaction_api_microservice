# Микросервис транзакций

## Проект: Проект для отслеживания транзакций

***Данное руководство подразумевается для описания сервиса, и для дальнейшего запуска.***

- [Сервисное описание](#о-сервисе)

* [Endpoints](#endpoints)
* [Технологий](#технологий)

+ [Установка и запуск проекта](#установка)

## О сервисе

Проект предназначен для микрофинансовой организации (МФО) и позволяет отслеживать транзакции с различных сервисов. Все
поступающие транзакции рассчитываются по актуальному курсу валют, при этом базовая валюта — тенге (KZT). Все расчеты
конвертируются в тенге, после чего рассчитываются лимиты. Лимиты могут быть установлены в любой валюте.

### EndPoints

#### API Client

| Method | Path                                    | Description                                        |
|--------|-----------------------------------------|----------------------------------------------------|
| GET    | /api/client/limits                      | Для получения списка лимитов                       |
| GET    | /api/client/transactions/limit-exceeded | Для получения списка транзакций, превышающих лимит |
| POST   | /api/client/limit                       | Для установления лимита                            |

#### API Transations

| Method | Path                   | Description                   |
|--------|------------------------|-------------------------------|
| POST   | /api/transactions/save | Для создания новой транзакции |

#### API Currency

| Method | Path                         | Description                                                       |
|--------|------------------------------|-------------------------------------------------------------------|
| POST   | /currency/update-daily-rates | Запрос на внешний сервер alphavantage, чтобы получить курс валют. |

## Технологий

#### Использовал jdk-21 версий

`
id 'java'
id 'org.springframework.boot' version '3.2.4'
id 'io.spring.dependency-management' version '1.1.4'
`

###### Тесты: JUnit и Mockito

###### Архитектура: Microservice, архитектура внутренних сервисов REST.

###### DB: PostgreSQL JDBC Driver

###### Docker - чтобы все не конфигурировать и устанавливать

###### Spring Cloud и OpenFeign - Для работы с клиентом Feign

###### Lombok, Spring Data, Java SE, Spring WEB, Flyway

###### Mapper: MapStruct

###### Старался придерживаться принципов проектирования и ООП, но применять это было очень мало вариантов в связи с размером проекта

###### Gradle

## Установка

### Перейдем к установке, самого сервиса

#### №1.Убедитесь, что у вас установлены все необходимые зависимости и библиотеки

#### №2. Скопировать мой репозиторий с GitHub по ссылке по команде `git clone ` + ссылка репозиторий, в терминале, внутри папки который вы создали, или можете внутри intellij idea, во верхних вкладках есть `get from version control` с помощью данной утилиты скопировать мои проект

#### №3 Cоздайте базу данных `transactions` в PostgreSQL

#### №4. Скомпилируйте и запустите приложение

## Запуск сервиса через docker compose

#### Dockerfile находится в корне проекта. (docker-compose.yml)

#### Сервис по порту 7777, ссылка: `http://localhost:7777`








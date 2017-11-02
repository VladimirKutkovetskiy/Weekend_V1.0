# Weekend_V1.0

## Веб приожение для подсчета кол-ва выходных дней (выходными считаются   суббота и воскресенье а также даты из таблицы holidays в базе
данных ) между 2-мя датами.

### Сервис доступен только юзерам, которые прошли авторизацию на странице логина! (/login)

### Зарегестрироватся можно на странице (/registration)

### После регистрации/авторизации пользователя перенаправляет на /welcome где есть приветствие, выход, информация о сервисе,
а также форма ввода двух дат.

### После нажатия кнопки "Calculate" производится расчет выходных дней, при удачном рассчете, пользователю выводится количество
выходных дней.

###--------------------------------------------------------------------------------

## Prerequisites
- JDK 1.8 or later
- Maven 3 or later
- MySQL 5.6 or later

## Stack
- Spring MVC
- Spring Security
- Spring Data JPA
- Maven
- JSP
- MySQL

## Run  'mvn jetty:run'

## Структура:

webapp/WEB-INF хранятся файлы конфигурации. Главный файл конфигурации "appconfig-root.xml". Этот файл начальной
загрузки должен использовать <import resource="" />для включения других файлов конфигурации.

webapp/WEB-INF/viwes хранятся файлы jsp, динамично генерируемые HTML веб-страницы. 3 страницы, авторизация, регистрация и страница
рассчета выходных дней.

## Реализация

Логин / аутентификация реализуется с помощью Spring Security, для этого было реальзовано интерфейс UserDetailsService.
Авторизация осуществляется через конфигурацию файла XML appconfig-security.xml.
Реализовано Security Service, для обеспечения текущего входа в систему пользователя и автозапуска после регистрации аккаунта.

Контроллер /login POST предоставляется Spring Security.

Контроллер /registration POST

Контроллер /welcome POST считывает две даты и рассчитывает выходные дни а также даты что зазначенные в бд и выводит.

application.properties - свойства

Чтобы обеспечить проверку входных данных для /registrationконтроллера с помощью Spring Validator, было реализовано
Validator. Коды ошибок, например Size.userForm.username, определяются validation.properties.

AppConfig-mvc.xml  Spring MVC

AppConfig-data.xml Конфигурация Spring Data JPA

AppConfig-security.xml Конфигурация Spring Security

Примеры работы программы находятся в src/main/resources


















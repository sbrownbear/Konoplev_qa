## HTTP
`HTTP – HyperText Transfer Protocol (протокол передачи гипертекста)` использует TCP. HTTP использует клиент-серверную архитектуру. 80 порт.

__Клиент__ (кто отправляет запрос) --- __Сервер__ (удаленный компьютер, который умеет обрабатывать http-запросы)

`Клиент серверная архитектура` – тип компонентно-коннекторной архитектуры, в которой сетевая нагрузка распределены между поставщиками услуг, называемыми серверами, и заказчиками услуг, называемыми клиентами.
__Клиент серверная архитектура: двухуровневая, трехуровневая и многоуровневая система.__

Многоуровневая клиент серверная архитектура: Client – Balancer – Server (2-5) – Database

`TCP – Transmission Control Protocol (протокол управления передачей)` Для пересылки своих сообщений. Гарантирует доставку данных в том же порядке в котором были отправлены. Обеспечивает надежную доставку пакетов без ошибок. 

>HTTP 0.9 (1991) – HTTP 1.0 (1996) - HTTP 1.1 (1997) - HTTP 2.0 (2015) TCP - HTTP 3.0 QUIC (готовиться к публикации)

`HTTPS` – зашифрованная версия HTTP протокола. Наше соединение защищено. Использует протокол TLS. Безопасный обмен данными. 443 порт.

>SSL 2.0 (1995) - SSL 3.0 (1995) - TLS 1.0 (1999) - TLS 1.1 (2006) - __TLS 1.2 (2008) - TLS 1.3 (2018) актуальные версии__

__Безопасность передачи данных:__ безопасность (используется хэш-функции), аутентификация (используется сертификат), контроль целостности.

Сообщение | Хэш сумма | Длина (симв.)
---- |---- | -----
Сергей | 6d74ef9f90274f9af39dfa53c58e287bfdc633a7 | 40
Коноплев Сергей | F00cd2ff301c1afb763a0c4d01d4fd493a2a9460 | 40
Коноплев Сергей Александрович | 7af22de32ab944beb5617eecdfacfa17d4a83b49 | 40

`TLS` использует гибридный метод шифрования: сначала ассиметричное, после симметричное шифрование

__Handshake (рукопожатие)__ – установление контакта между клиентом и сервером (на этом этапе используется ассиметричное шифрование)

## API

`API` — Application Programming Interface, программный интерфейс приложения, с помощью которого одна программа может взаимодействовать с другой. API позволяет слать информацию напрямую из одной программы в другую, минуя интерфейс взаимодействия с пользователем. 

__API__ может быть внутренним, частным — когда программные компоненты связаны между собой и используются внутри системы. А может быть открытым, публичным — в таком случае он позволяет внешним пользователям или другим программам получать информацию, которую можно интегрировать в свои приложения.

Чтобы программам общаться между собой, их API нужно построить по единому стандарту. Одним из них является REST — стандарт архитектуры взаимодействия приложений и сайтов, использующий протокол HTTP. Особенность REST в том, что сервер не запоминает состояние пользователя между запросами. 

__Как тестировать API?__

Тестирование __API__ относится к интеграционному тестированию, а значит в ходе него можно отловить ошибки взаимодействия между модулями системы или между системами. Для тестирования используют специальные инструменты, где можно отправить входные данные в запросе и проверить точность выходных данных. Одним из таких инструментов как раз и является Postman. Вот что он умеет:

- Составлять и отправлять запросы;
- Сохранять запросы в папки и коллекции;
- Параметризовать запросы;
- Добавлять к вызову API контрольные точки;
- Создавать разные окружения для одних и тех же запросов;
- Запускать коллекции с помощью Collection Runner и использовать их как автоматизированные тесты.

## HTTP Запросы

`Методы HTTP запросов` – короткое английское слово, записанное заглавными буквами. Название метода чувствительно к регистру. Название метода можно сделать любым, но клиент и сервер должны их знать.

__Безопасные методы__ – не вызывают изменения сервера. Режим «ready-only» `GET`, `HEAD`, `OPTIONS`, `TRACE`

__Идемпотентные методы__ – повторение второго и последующих запросов имеет один и тот же результат. Все безопасные методы являются идемпотентными. `GET`, `HEAD`, `OPTIONS`, `TRACE`, `PUT`, `DELETE`

Название | GET | POST
---- | ---- | ----
Кнопка “назад” / Перезагрузка | Безопасно | Данные будут отправлены вновь. Браузер должен предупредить, что произойдет повторная отправка данных.
Добавление в закладки | Да | Нет
Кеширование | Да | Нет
История | Остается в истории браузера. | Не остается в истории браузера.
Ограничение в длине запроса | Есть ограничения. Так как данные передаются в URL, то запрос должен ограничиваться 2048 символами (максимальная длина URL). | Нет ограничений.
Ограничение по типу данных | Допускается использование только символов ASCII. | Не имеет ограничение. Допускаются также двоичные данные.
Безопасность | Менее безопасный метод передачи, поскольку передаваемые в URL данные видны пользователю. | POST более безопасный, так как данные не отображаются напрямую в web-клиенте пользователя, кроме того запрос не кешируется и не сохраняется в истории.
Видимость | Данные в URL визуально доступны всем. | Данные не видны в URL.

`GET` – запрашивает ресурс. Может только извлекать данные. Сам запрос не имеет тело, но содержится в теле ответа. 

`HEAD` – запрашивает ресурс. Аналогичен `GET`, но без тела ответа.

`POST` – отправка данных к определенному ресурсу. Используется, когда нужно что-то передать серверу, например, логин и пароль.

`PUT` – обновляет.

`DELETE` – удаляет указанный ресурс.

`CONNECT` – запускает двухстороннюю связь запрошенным ресурсом. 

`OPTIONS` – используется для описания параметра.

`TRACE` – возвращает полученный запрос. Клиент может видеть какую инфу промежуточные серверы добавляют или изменяют в запросе.

`PATCH` – частично изменяет ресурс.

Все серверы общего назначения должны поддерживать методы __GET__ и __HEAD__. Все остальные методы необязательны. . 

Метод | Имеет тело | Успешный ответ имеет тело | Безопасный | Идемпотентный
---- | ---- | ---- | ---- | ---- 
GET	| Нет | Да | Да | Да
HEAD | Нет | Нет | Да | Да
POST | Да | Да | Нет | Нет
PUT | Да | Нет | Нет | Да
DELETE | Может | Может | Нет | Да
CONNECT | Нет | Да | Нет | Нет
OPTIONS | Нет | Да | Да | Да
TRACE | Нет | Нет | Да | Да
PATCH | Да | Да | Нет | Нет

`Серии кодов статусов` (ошибки)

`1хх` – информационный; `2хх` –  успех; `3хх` – редирект; `4хх` – ошибка клиента; `5хх` – ошибка сервера

`200` OK; `202` Accepted («принято»)

`305` Use Proxy («использовать прокси»)

`400` Bad Request («неправильный, некорректный запрос»); `401` Unauthorized («не авторизован (не представился)»); `402` Payment Required («необходима оплата»); `403` Forbidden («запрещено (не уполномочен)»); `404` Not Found («не найдено»)

`505` – неверный метод (get вместо post); `500` Internal Server Error («внутренняя ошибка сервера»); `501` Not Implemented («не реализовано»); `502` Bad Gateway («плохой, ошибочный шлюз»); `503` Service Unavailable («сервис недоступен»); `504` Gateway Timeout («шлюз не отвечает»)

## REST

`REST (Representational State Transfer — «передача состояния представления»)` —архитектурный стиль взаимодействия компонентов распределённого приложения в сети. Не является стандартом или протоколом.

Обеспечивает общение между клиентом (как правило, это браузер) и сервером с помощью обычных HTTP-запросов (GET, POST, PUT, DELETE и т. д), передавая информацию от клиента в параметрах самих запросов, информацию от сервера – в теле ответа (который может быть, например, JSON-объектом или XML-документом).

__REST__ представляет собой согласованный набор ограничений, учитываемых при проектировании распределённой гипермедиа-системы.

В определённых случаях (интернет-магазины, поисковые системы, прочие системы, основанные на данных) это приводит к повышению производительности и упрощению архитектуры. В широком смысле компоненты в REST взаимодействуют наподобие взаимодействия клиентов и серверов во Всемирной паутине.

__Преимущества REST:__

- Надёжность (за счёт отсутствия необходимости сохранять информацию о состоянии клиента, которая может быть утеряна);

- Производительность (за счёт использования кэша);

- Масштабируемость;

- Прозрачность системы взаимодействия (особенно необходимая для приложений обслуживания сети);

- Простота интерфейсов;

- Портативность компонентов;

- Лёгкость внесения изменений;

- Способность эволюционировать, приспосабливаясь к новым требованиям (на примере Всемирной паутины).

## SOAP

`SOAP (Simple Object Access Protocol)` – простой протокол доступа к объектам.

Протокол обмена структурированными сообщениями в распределённой вычислительной среде.

Характеризуется использованием HTTP(S)-протокола лишь как транспорта (чаще всего, методом POST).

Все детали сообщений (в обе стороны – от клиента к серверу и обратно) передаются в стандартизованном XML-документе.

__SOAP__ может работать и с другими протоколами прикладного уровня (SMTP, FTP), но чаще всего он применяется поверх HTTP(S). Несимметричный, не зависит от платформы.

__Недостаток:__

Использование __SOAP__ для передачи сообщений увеличивает их объём и снижает скорость обработки. В системах, где скорость важна, чаще используется пересылка XML-документов через HTTP напрямую, где параметры запроса передаются как обычные HTTP-параметры.

[Отличия rest и soap можно посмотреть тут.](https://habr.com/ru/post/483204/)

## Формат обмена данными JSON и XML

Многие разработчики сравнивают JSON с XML при создании приложений, которые обмениваются данными между разными системами. Это часто превращается в спор «JSON против XML», поскольку каждая сторона защищает свой предпочтительный формат.

Оказывается, __JSON__ и __XML__ имеют несколько разные цели, поэтому не всегда справедливо или уместно говорить, что одно «лучше» другого. Всё зависит от цели.

__JSON__ - это просто формат данных, тогда как __XML__ - это язык разметки.

`JSON` — это формат обмена данными, его __цель__ — облегчить обмен структурированными данными. Это достигается путём непосредственного представления объектов, массивов, чисел, строк и логических значений, которые часто присутствуют в исходном окружении и в месте назначения.

`XML` является языком разметки, его цель — разметка документа.

В любом случае, если проекту требуется разметка документа и информация о метаданных, лучше использовать __XML__, а для более организованного обмена данными __JSON__ может быть вашим предпочтительным выбором.

__XML__ расшифровывается как eXtensible Markup Language. Это способ хранения данных, которые могут быть прочитаны как людьми, так и машинами. Формат XML доступен для использования во многих языках программирования.

__JSON (JavaScript Object Notation) - текстовый формат обмена данными__, основанный на JavaScript. Это формат, реализующий неструктурированное текстовое представление структурированных данных, основанное на принципе пар ключ-значение и упорядоченных списках. __JSON__ требует меньше кода и имеет меньший размер, что ускоряет обработку и передачу данных. Не смотря на то, что __JSON__ написан на JavaScript , он не зависит от языка. Он не имеет каких-либо мощных функций, связанных с проверкой и схемой, которые есть у XML.

__Структуру каждого из них:__

XML

    <employees>
        <employee>
            <firstName>John</firstName> <lastName>Doe</lastName>
        </employee>
        <employee>
            <firstName>Anna</firstName> <lastName>Smith</lastName>
        </employee>
        <employee>
            <firstName>Peter</firstName> <lastName>Jones</lastName>
        </employee>
    </employees>

JSON

    {"employees":[
        { "firstName":"John", "lastName":"Doe" },
        { "firstName":"Anna", "lastName":"Smith" },
        { "firstName":"Peter", "lastName":"Jones" }
    ]}


Как мы видим, структура тегов, безусловно, добавляет некоторую сложность, в то время как формат __JSON__ более читабельный.

Более того, благодаря основанным на JavaScript фреймворкам, таким как Node.js, __JSON__ получает большее признание с каждым днем. Когда интерфейсный код находится в JavaScript, получение данных в формате __JSON__ облегчает загрузку данных в дерево объектов.

__JSON__ идеальный формат для базы данных, так Ткак каждый язык программирования способен анализировать __JSON__.

__JSON__ похож на __XML__ тем, что:

- И JSON, и XML имеют "самоописательную" структуру (понятную для человека)

- И JSON, и XML имеют иерархическую структуру (значения внутри значений)

- И JSON, и XML могут парситься и использоваться любым языком программирования

- И JSON, и XML могут извлекаться при помощи XMLHttpRequest

__JSON__ не похож на __XML__ тем, что:

- JSON не использует конечный тег

- JSON короче

- JSON быстрее читать и писать

- JSON может использовать массивы

Самое значительное отличие __JSON__ от __XML__ заключается в том, что __XML__ приходится парсить при помощи специального __XML__ парсера, а __JSON__ может парситься стандартной функцией JavaScript.

`JSON`

__Pro:__

- Простой синтаксис, который приводит к уменьшению накладных расходов "разметки" по сравнению с XML.

- Прост в использовании с JavaScript, так как разметка представляет собой подмножество буквенной нотации объекта JS и имеет те же основные типы данных, что и JavaScript.

- Схема JSON для описания и проверки типов данных и структуры

- JsonPath для извлечения информации в глубоко вложенных структурах

__Contra:__

- Простой синтаксис поддерживает только несколько различных типов данных.

`XML`

__Pro:__

- Обобщенная разметка; можно создать "диалекты" для любых целей.

- XML Schema я типа данных, проверки структуры. Делает также возможным создание новых типов данных.

- XSLT для преобразования в разные выходные форматы

- XPath/XQuer yдля извлечения информации в глубоко вложенных структурах.

- Встроенная поддержка пространств имен

__Contra:__

- Относительно многословный по сравнению с JSON (приводит к большему количеству данных за тот же объем информации).
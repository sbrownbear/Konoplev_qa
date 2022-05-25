# Konoplev_qa
`Тестирование ПО` – проверка соответствия между реальным и ожидаемым поведением программы. Проверка продукта на соответствие требованиям и нуждам заказчика.

Цель тестирования – предоставление актуальной информации о соответствии требованиям производимого продукта.

Жизненный цикл ПО – период времени, который начинается с момента принятия решения о создании продукта и заканчивается в момент полного изъятия программы из эксплуатации.

1 анализ требований

2 проектирование

3 кодирование(программирование)

4 тестирование и отладка

5 эксплуатация и сопровождение

Баг-репорт (описание бага) - это инфа что бы баг воспроизвести. Цель – предоставить максимально подробно описание бага, но не чрезмерно, для того чтобы разработчики и все остальные понимали, что из себя представляет баг, как его воспроизвести. Документ может содержать:

Название – максимально короткое описание проблемы.

Начать необходимо с описания, что за проблема, закончить тем, где она находится. Пример: Невозможно зарегистрироваться на главной странице сайта.

Не отображается тип платежей в Payment history.

Не открывается календарь при клике на иконку календаря в разделе/logs

Шаги необходимые для того что бы выявить ошибку. Пример:

Авторизоваться на example.com под test@test.com 

и перейти в раздел example.com/admin

Установить чекбокс «supervisor»

Ожидаемый результат и фактический результат

Критичность и/или приоритет

Скриншот, видео, гиф и прочую информацию

Версию, сборку, ресурс и другие данные об окружении

Приоритет (Priority) – это атрибут, указывающий на очередность выполнения задачи или устранения дефекта. Проставляется руководителем или менеджером проекта.

Р1 – Высокий (High) – требуется исправить в первую очередь;

Р2 – Средний (Medium) – требуется исправить во вторую очередь, когда нет дефектов с высоким приоритетом;

Р3 – Низкий (Low) – исправляется в последнюю очередь, когда все дефекты с более высоким приоритетом уже исправлены.

Серьезность (Severity) – это атрибут, характеризующий влияние дефекта на работоспособность приложения. Проставляется тестеровщиком или техническим специалистом, который может оценить степень влияния дефекта на работу системы.

S1 – Блокирующая (Blocker) – дефект полностью блокирует выполнение функционала, нет никакого способа обойти его. 

S2 – Критический (Critical) – дефект блокирует часть функциональности, но есть альтернативный путь для его обхода.

S3 – Значительный (Major) – дефект, указывающий на некорректную работу части функциональности. Зачастую связан не с тем, что функция не работает, а с тем, что она работает неправильно. В любом случае существует более одной точки входа для инициации нужной функциональности. Наиболее часто встречается дефекты, которые можно отнести именно к этому уровню серьезности.

S4 – Незначительный (Minor) – дефект, не относящийся к функциональности системы. Обычно предоставляется для тех дефектов, которые относятся к удобству использования или интерфейсу. 

S5 – Тривиальный (Trivial) – дефект, не затрагивающий функциональность системы, а также оказывающий минимальное влияние на общее качество системы. Часто неотличим от уровня «Minor». Обычно это грамматические дефекты в сопроводительной документации к системе. Иногда дефект относится к «невидимым» проблемам с точки зрения пользователя или пользовательского интерфейса и рассматривает сторонние библиотеки или сервисы, не относящиеся к самой разработанной системе.

Жизненный цикл бага – в разных компаниях бывает разный

Обнаружен (submitted) Open. Тестер находит дефект и предоставляет его на рассмотрение в систему управления дефектами. С этого момента баг начинает свою жизнь и о его существовании знают необходимые люди.

Назначен (assigned). Далее ведущий разработчик рассматривает дефект и назначает его исправление кому-то из команды разработчиков.

В работе (In progress). Разработчик работает над исправлением данного бага.

Исправлен (Fixed). Разраб исправляет и сообщает что задание выполнено.

Проверен (verified). Тестер, который обнаружил ошибку, проверяет на новом билде (в котором исправление данной ошибки заявлено), исправлен ли дефект на самом деле. Только в том случае, если ошибка не проявится на новом билде, тестеровщик меняет статус бага на Verified.

Открыт заново (reopen). Если баг проявляется на новом билде, тестер снова открывает этот дефект.

Отклонен (declined). Баг может быть отклонен. Во-первых, для заказчика какие-то ошибки перестают быть актуальными. Во-вторых, это может случиться по вине тестера из-за плохого знания продукта, требований (дефекта на самом деле нет, не смогли понять, не смогли воспроизвести)

Отложен (deferred). Если исправление конкретного бага сейчас не приоритетная задача или заказчик пока думает, или мы ждем какую-то информацию, от которой зависит исправление.

Закрыт (closed). Закрытым считается баг в состояниях «Проверен» и «Отклонен»

## Тестирование API

API — это Application Programming Interface, или программный интерфейс приложения, с помощью которого одна программа может взаимодействовать с другой. API позволяет слать информацию напрямую из одной программы в другую, минуя интерфейс взаимодействия с пользователем. 
API может быть внутренним, частным — когда программные компоненты связаны между собой и используются внутри системы. А может быть открытым, публичным — в таком случае он позволяет внешним пользователям или другим программам получать информацию, которую можно интегрировать в свои приложения.
Чтобы программам общаться между собой, их API нужно построить по единому стандарту. Одним из них является REST — стандарт архитектуры взаимодействия приложений и сайтов, использующий протокол HTTP. Особенность REST в том, что сервер не запоминает состояние пользователя между запросами. 

Как тестировать API?

Тестирование API относится к интеграционному тестированию, а значит в ходе него можно отловить ошибки взаимодействия между модулями системы или между системами. Для тестирования используют специальные инструменты, где можно отправить входные данные в запросе и проверить точность выходных данных. Одним из таких инструментов как раз и является Postman. Вот что он умеет:

- Составлять и отправлять запросы;

- Сохранять запросы в папки и коллекции;

- Параметризовать запросы;

- Добавлять к вызову API контрольные точки;

- Создавать разные окружения для одних и тех же запросов;

- Запускать коллекции с помощью Collection Runner и использовать их как автоматизированные тесты.

Методы запросов

GET — возвращает ресурс, POST — создает новый, PUT — обновляет существующий, DELETE — удаляет.

В чем отличие GET от POST 

Get - параметры передаются в самом URL, пишутся через вопросительный знак. POST - параметры передаются через "Body" в теле запроса.

В чем отличие REST от SOAP

REST - это архитектурный стиль (нет огромного кол-во правил), поддерживает различные форматы (json, xtml, xml, javascript, текстовые форматы). 

SOAP - это протокол, это формат обмена сообщениями, поддерживает только xtm, работает с различными протоколами, не может быть помещён в кэш.

Серии кодов статусов

1хх – информационный

2хх –  успех

3хх – редирект

4хх – ошибка клиента

5хх – ошибка сервера

## Тестовая документация 

Тест-кейс – это документ, который содержит набор хорошо продуманных и понятных шагов (действий), для проверки конкретной функции или функциональности программного обеспечения. Набор тест-кейсов называется тестовым набором (test suite). 

Состоит: номер, название, шаги, данные, ОР, ФР, attach (логи)

Чек – лист – отличается от тест-кейса степенью подробности. В чек-листе нет подробных шагов кейса, для использования чек-листа при тестировании очень много инфы нужно держать в голове в момент прогона тестов и знать логику работы приложения на отлично.

Состоит: номер, название, ОР

Тест план – это документ, который описывает весь объем работ по тестированию, начиная с описания объекта тестирования, стратегии, расписания, критериев начала и окончания тестирования, до необходимого в процессе работы оборудования, специальных знаний, а также оценки рисков с вариантами их разрешения.

Критерия выбора тестовой документации
Если простой процесс или проект короткий, то используем чек-лист. Сложные и подробные проверки, команда большая и нестабильная – тест-кейс. Что выбрать зависит от заказчика.

## Методология разработки ПО

Модель разработки программного обеспечения описывает, какие стадии жизненного цикла оно проходит и что происходит на каждой из них. А методология включает в себя набор методов по управлению разработкой: это правила, техники и принципы, которые делают её более эффективной.

1. Водопадная (Waterfall) каскадная. Особенности: чтобы перейти к следующему этапу, должны завершить текущий. Простота и понятна.

Requirements (сбор требований) --- Analysis (анализ) --- Design (дизайн) --- Coding (кодирование) --- Testing (тестирование) --- Operations (поддержка)

+ Полное документирование; четкое планирование; прозрачность

- Утверждение полного объема работ на первом этапе; в случае изменения требования - начало работы заново; увеличение затрат при изменении требований

Область применения: некоторые гос. учреждения, банки, когда проект эмигрирует с одной платформы на другую, когда не требуется тестирование

2. V – модель. Модифицированная версия каскадной модели. Особенности: на каждом этапе происходит контроль текущего процесса.

+ Строгие этапы, раннее тестирования, промежуточное тестирование

- Нет гибкости, написание кода только в середине процесса, нет динамического внесения изменения

3. Итерационная модель. Разбит на ряд мини циклов (итерации)

+ Раннее создание ПО, гибкость, процесс тестирования и анализ

- Не каждая фаза самостоятельная, не все требования известны вначале

4. Scrum. Scrum ориентирован на клиента, адаптивен. Возможность изменения требований. Scrum позволяет получить потенциально рабочий продукт в конце каждого Sprint'а. Для малых компаний и стартапов.

5. Kanban. Это доска, на ней стикеры, читаются слева направо, чем выше стикер тем приоритетнее задача. Столбцы: цели проекта, очередь задач, проработка дизайна, разработка, тестирование, деплоймент, закончено. 

Столбцы 1. Принято в разработку 2. Разрабатывается 3. Тестирование 4. Готово для релиза на продакшн 5. Продакшн 
Разница между Канбан и SCRUM:

— В Канбан нет таймбоксов ни на что (ни на задачи, ни на спринты)

— В Канбан задачи больше и их меньше

— В Канбан оценки сроков на задачу опциональные или вообще их нет

— В Канбан «скорость работы команды» отсутствует и считается только среднее время на полную реализацию задачи

## Техники тест дизайна

Это этап процесса тестирования ПО, на котором проектируются и создаются тестовые случаи (тест-кейсы) в соответствии с определенными ранее критериями качества и целями тестирования.

Класс эквивалентности (equivalence class) – набор данных, обработка которых приводит к одному и тому же результату.

Два теста можно считать эквивалентными, в случае, когда:

- они проверяют одну и ту же часть системы

- один тест находит ошибку, то и другой, скорее всего, найдет ошибку и наоборот

- они используют сходные наборы входных данных

- чтобы выполнить тесты, необходимо совершить одни и те же операции

- в результате проведения тестов получаем одинаковый входные данные и   система находится в одном и том же состоянии

- срабатывает один и тот же блок обработки ошибки

- не срабатывает блок обработки ошибки

1. Эквивалентное разделение (использование классов эквивалентности) - это техника, при которой функционал (диапазон возможных входных значений) разделяются на группы значений эквивалентных по воздействию на систему.

2. Анализ граничных значений – это техника тест-дизайна, которая направлена на проверку поведения системы на граничных значениях входных данных (границах классов эквивалентности).

3. Попарное тестирование (большинство ошибок возникает на пересечении двух параметров теста) - это техника формирования наборов тестовых данных из полного набора входных данных в системе, которая позволяет существенно сократить количество тест-кейсов.

Сформулировать суть попарного тестирования можно следующим образом: формирование таких наборов данных, в которых каждое тестируемое значение каждого из проверяемых параметров хотя бы единожды сочетается с каждым тестируемым значением всех остальных проверяемых параметров.

Главные цели Pairwise Testing:
- убрать избыточные проверки;
- обеспечить хорошее тестовое покрытие;
- выявить наибольшее количество багов на минимальном наборе тестов.

4. Тестирование на основе состояний и переходов - применяется для фиксирования требований и описания дизайна приложения.

5. Таблицы принятия решений (матрица принятия решений) - техника тестирования, основанная на методе чёрного ящика, которая применяется для систем со сложной логикой.

6. Доменный анализ - это техника основана на разбиении диапазона возможных значений переменной на поддиапазоны, с последующим выбором одного или нескольких значений из каждого домена для тестирования.

7. Сценарий использования - описывает сценарий взаимодействия двух и более участников (как правило — пользователя и системы).

8. Предугадывание ошибок

9. Исчерпывающее тестирование (такое тестирование на практике невозможно)

10. Графические техники тест дизайна (применение диаграмм для планирования тестирования)

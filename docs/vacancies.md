# Получение вакансий

* [Просмотр вакансии](#item)
* [Отобранные вакансии](#favorited)
* [Поиск по вакансиям](#search)
* [Поиск по вакансиям, похожим на вакансию](#similar)
* [Короткое представление вакансии](#nano)
* [Скрытые вакансии](blacklisted.md)

Смотрите также:

<a name="creation"></a>
<a name="creation-example"></a>
<a name="creation_fields"></a>
<a name="allow_messages"></a>
<a name="creation-results"></a>
<a name="conditions"></a>
<a name="edit"></a>
<a name="edit_more"></a>
<a name="other-actions"></a>
<a name="prolongate"></a>
<a name="prolongate-info"></a>
<a name="branded-template-field"></a>

* [Вакансии для работодателя](employer_vacancies.md)
  * [Публикация вакансий](employer_vacancies.md#creation)
  * [Редактирование вакансий](employer_vacancies.md#edit)
  * [Продление вакансий](employer_vacancies.md#prolongate)
  * [Удаление вакансий](employer_vacancies.md#hide)


<a name="item"></a>
## Просмотр вакансии

`GET /vacancies/{vacancy_id}`

где `vacancy_id` – идентификатор вакансии.

Вернёт подробную информацию по указанной вакансии.

### Ответ

Успешный ответ приходит с кодом `200 OK` и содержит тело:

```json
{
    "id": "8331228",
    "description": "...",
    "branded_description": "<style>...</style><div>...</div><script></script>",
    "key_skills": [
        {
            "name": "Прием посетителей"
        },
        {
            "name": "Первичный документооборот"
        }
    ],
    "schedule": {
        "id": "fullDay",
        "name": "Полный день"
    },
    "accept_handicapped": false,
    "accept_kids": false,
    "experience": {
        "id": "between1And3",
        "name": "От 1 года до 3 лет"
    },
    "address": {
        "city": "Москва",
        "street": "улица Годовикова",
        "building": "9с10",
        "description": "на проходной потребуется паспорт",
        "lat": 55.807794,
        "lng": 37.638699,
        "metro_stations": [
            {
                "station_id": "6.8",
                "station_name": "Алексеевская",
                "line_id": "6",
                "line_name": "Калужско-Рижская",
                "lat": 55.807794,
                "lng": 37.638699
            }
        ]
    },
    "alternate_url": "https://hh.ru/vacancy/8331228",
    "apply_alternate_url": "https://hh.ru/applicant/vacancy_response?vacancyId=8331228",
    "code": "HRR-3487",
    "department": {
        "id": "HH-1455-TECH",
        "name": "HeadHunter::Технический департамент"
    },
    "employment": {
        "id": "full",
        "name": "Полная занятость"
    },
    "salary": {
        "to": null,
        "from": 30000,
        "currency": "RUR",
        "gross": true
    },
    "archived": false,
    "name": "Секретарь",
    "insider_interview": {
        "id": "12345",
        "url": "https://hh.ru/interview/12345?employerId=777"
    },
    "area": {
        "url": "https://api.hh.ru/areas/1",
        "id": "1",
        "name": "Москва"
    },
    "created_at": "2013-07-08T16:17:21+0400",
    "published_at": "2013-07-08T16:17:21+0400",
    "employer": {
        "logo_urls": {
            "90": "https://hh.ru/employer-logo/289027.png",
            "240": "https://hh.ru/employer-logo/289169.png",
            "original": "https://hh.ru/file/2352807.png"
        },
        "name": "HeadHunter",
        "url": "https://api.hh.ru/employers/1455",
        "alternate_url": "https://hh.ru/employer/1455",
        "id": "1455",
        "trusted": true,
        "blacklisted": false
    },
    "response_letter_required": true,
    "type": {
        "id": "open",
        "name": "Открытая"
    },
    "has_test": true,
    "response_url": null,
    "test": {
        "required": false
    },
    "specializations": [
        {
            "profarea_id": "4",
            "profarea_name": "Административный персонал",
            "id": "4.255",
            "name": "Ресепшен"
        },
        {
            "profarea_id": "4",
            "profarea_name": "Административный персонал",
            "id": "4.429",
            "name": "Делопроизводство"
        },
        {
            "profarea_id": "4",
            "profarea_name": "Административный персонал",
            "id": "4.264",
            "name": "Секретарь"
        },
        {
            "profarea_id": "4",
            "profarea_name": "Административный персонал",
            "id": "4.181",
            "name": "Начальный уровень, Мало опыта"
        }
    ],
    "contacts": {
        "name": "Имя",
        "email": "user@example.com",
        "phones": [
            {
                "country": "7",
                "city": "985",
                "number": "000-00-00",
                "comment": null
            }
        ]
    },
    "billing_type": {
        "id": "standard",
        "name": "Стандарт"
    },
    "allow_messages": true,
    "premium": true,
    "driver_license_types": [
        {
            "id": "A"
        },
        {
            "id": "B"
        }
    ],
    "accept_incomplete_resumes": false,
    "working_days": [
        {
            "id": "only_saturday_and_sunday",
            "name": "Работа только по сб и вс"
        }
    ],
    "working_time_intervals": [
        {
            "id": "from_four_to_six_hours_in_a_day",
            "name": "Можно работать сменами по 4-6 часов в день"
        }
    ],
    "working_time_modes": [
        {
            "id": "start_after_sixteen",
            "name": "Можно начинать работать после 16-00"
        }
    ],
    "accept_temporary": false,
    "professional_roles": [
        {
            "id": "96",
            "name": "Программист, разработчик"
        }
    ]
}
```

<a name="vacancy-fields"></a>

Имя | Тип | Описание
---- | --- | --------
id | string | Идентификатор вакансии
description | string | Описание вакансии, содержит html
branded_description | string или null | [Брендированное описание вакансии](#branded_description)
key_skills | array | Информация о ключевых навыках, заявленных в вакансии. Список может быть пустым.
key_skills[].name | string | название ключевого навыка
schedule | object | График работы. Элемент справочника [schedule](dictionaries.md)
schedule.id | string | Идентификатор графика работы
schedule.name | string | Название графика работы
accept_handicapped | boolean | Указание, что вакансия доступна для соискателей с инвалидностью
accept_kids | boolean | Указание, что вакансия доступна для соискателей от 14 лет
experience | object | Требуемый опыт работы. Элемент справочника [experience](dictionaries.md)
experience.id | string | Идентификатор требуемого опыта работы
experience.name | string | Название требуемого опыта работы
address | object или null | [Адрес вакансии](address.md#Адрес)
alternate_url | string | Ссылка на представление вакансии на сайте
apply_alternate_url | string | Ссылка на отклик на вакансию на сайте
code | string или null | Внутренний код вакансии работадателя
department | object или null | Департамент, от имени которого размещается вакансия (если данная возможность доступна для компании). Работодатели могут запросить [справочник департаментов](employer_departments.md).
department.id | string | Идентификатор департамента
department.name | string | Название департамента
employment | object или null | Тип занятости. Элемент справочника [employment](dictionaries.md).
employment.id | string | Идентификатор типа занятости
employment.name | string | Название типа занятости
salary | object или null | Оклад
salary.from | number или null | Нижняя граница вилки оклада
salary.to | number или null | Верняя граница вилки оклада
salary.gross | boolean или null | Признак того что оклад указан до вычета налогов. В случае если не указано - null.
salary.currency | string | Идентификатор валюты оклада (справочник [currency](dictionaries.md)).
archived | boolean | Находится ли данная вакансия в архиве
name | string | Название вакансии
insider_interview | object или null | [Интервью о жизни в компании](#insider-interview)
area | object | Регион размещения вакансии
area.id | string | Идентификатор региона
area.name | string | Название региона
area.url | string | Url получения информации о регионе
created_at | string | Дата и время создания вакансии
published_at | string | Дата и время публикации вакансии
employer | object или null | Короткое представление работодателя. Описание полей смотрите в [информации о работодателе](employers.md#item). Может не прийти в случае, если вакансия анонимная
employer.blacklisted | boolean | Добавлены ли все вакансии работодателя в [список скрытых](blacklisted.md#employers)
response_letter_required | boolean | Обязательно ли заполнять сообщение при отклике на вакансию
type | object | Тип вакансии. Элемент справочника [vacancy_type](dictionaries.md).
type.id | string | Идентификатор типа вакансии
type.name | string | Название типа вакансии
has_test | boolean | Информация о наличии прикрепленного тестового задании к вакансии. В случае присутствия теста - `true`.
response_url | string или null | На вакансии с типом `direct` нельзя откликнуться на сайте hh.ru, у этих вакансий в ключе `response_url` выдаётся URL внешнего сайта (чаще всего это сайт работодателя с формой отклика).
test | object или null | Информация о прикрепленном тестовом задании к вакансии. В случае отсутствия теста — `null`. **В данный момент отклик на вакансии с обязательным тестом через API невозможен.**
test.required | boolean | Обязательно ли заполнение теста для отклика
specialization | array | Специализации. Элементы справочника [specializations](specializations.md)
specializations[].id | string | Идентификатор специализации
specializations[].name | string | Название специализации
specializations[].profarea_id | string | Идентификатор профессиональной области, в которую входит специализация
specializations[].profarea_name | string | Название профессиональной области, в которую входит специализация
contacts | object или null | [Контактная информация](#contacts)
billing_type | object | Биллинговый тип вакансии. Элемент справочника [vacancy_billing_type](dictionaries.md).
billing_type.id | string | Идентификатор биллингового типа вакансии
billing_type.name | string | Название биллингового типа вакансии
allow_messages | boolean | Включена ли возможность соискателю писать сообщения работодателю, после приглашения/отклика на вакансию
premium | boolean | Является ли данная вакансия премиум-вакансией
driver_license_types | array | Список требуемых категорий водительских прав. Список может быть пустым.
driver_license_types[].id | string | Категория водительских прав. Элемент справочника [driver_license_types](dictionaries.md)
accept_incomplete_resumes | boolean | Разрешен ли отклик на вакансию неполным резюме
working_days | object или null | Рабочие дни. Элемент справочника [working_days](dictionaries.md)
working_days.id | string | Идентификатор рабочих дней
working_days.name | string | Название рабочих дней
working_time_intervals | object или null | Временные интервалы работы. Элемент справочника [working_time_intervals](dictionaries.md)
working_time_intervals.id | string | Идентификатор временного интервала работы
working_time_intervals.name | string | Название временного интервала работы
working_time_modes | object или null | Режимы времени работы. Элемент справочника [working_time_modes](dictionaries.md)
working_time_modes.id | string | Идентификатор режима времени работы
working_time_modes.name | string | Название режима времени работы
accept_temporary | boolean или null | Указание, что вакансия доступна для соискателей с временным трудоустройством
professional_roles | array | Массив [объектов профролей](#professional-role). Список может быть пустым.

<a name="contacts"></a>
#### Контактная информация

`contacts` - объект с контактной информацией по вакансии. В вакансиях, где контакты не указаны, возвращается `null`.

Объект содержит следующие поля:

Имя | Тип | Описание
---- | --- | --------
contacts.name | string или null | Имя контактного лица
contacts.email | string или null | Email контактного лица
contacts.phones | array | Список телефонов контактного лица. Может быть пустым.
contacts.phones[].country | string | Код страны
contacts.phones[].city | string | Код города
contacts.phones[].number | string | Номер телефона
contacts.phones[].comment | string или null | Комментарий

В архивных вакансиях контакты доступны:
* менеджеру вакансии
* другим пользователям с правами на архив менеджера вакансии


<a name="branded_description"></a>
#### Брендированное описание вакансии

`branded_description` - строка с кодом HTML (возможно наличие `<script/>` и
`<style/>`), которая является альтернативой стандартному описанию вакансии.

HTML адаптирован для мобильных устройств и корректно отображается без поддержки
javascript. При этом:

* Контент тянется по ширине на 100% ширины контейнера, и умещается без
  прокрутки в 300px.
* Контент рассчитан на то, что он будет вставлен в обвязку, в которую входит
  название, требуемый опыт работы, регион, тип занятости и рабочего дня
  вакансии, а также ссылка на компанию, опубликовавушю вакансию.
* Изображения, которые могут встретиться в таком описании, адаптированы под
  retina дисплеи.
* Размер шрифта не меньше 12px, размер межстрочного интервала не меньше 16px.

Значение может быть `null`, если у вакансии отсутствует индивидуальное описание.


<a name="insider-interview"></a>
#### Интервью о жизни в компании

`insider_interview` — объект с информацией об интервью о жизни в компании или null,
если для данной вакансии отсутствует интервью. Объект содержит следующие поля:

Имя | Тип | Описание
---- | --- | --------
id | string | идентификатор интервью
url | string | адрес страницы, содержащей интервью

<a name="professional-role"></a>
#### Профессиональная роль
Профессиональные роли приходят на замену специализациям. 
В настоящее время профессиональные роли и специализации используются параллельно для обеспечения обратной совместимости.

Имя | Тип | Описание
-----|-----|---------
id | string | Идентификатор профессиональной роли
name | string | Название профессиональной роли


<a name="vacancy-fields-applicant"></a>
#### Дополнительные поля вакансии для соискателей

При авторизации соикателем возвращаются дополнительные поля:

```json
{
    "relations": [
        "favorited",
        "got_response"
    ],
    "negotiations_url": "https://api.hh.ru/negotiations?vacancy_id=8331228",
    "suitable_resumes_url": "https://api.hh.ru/vacancies/8331228/suitable_resumes"
}
```

Имя | Тип | Описание
---- | --- | --------
relations | array | При авторизации соискателем, возвращает связи с вакансией. Значения из [справочника vacancy_relation](dictionaries.md).
negotiations_url | string | Cсылка для получения списка откликов/приглашений
suitable_resumes_url | string | Подходящие резюме на вакансию

Смотрите также [отклики на вакансии](negotiations.md#post_negotiation).


<a name="author"></a>
#### Дополнительные поля вакансии для работодателей

В случае с запросом вакансии с авторизацией автора (работодателя), в объекте
будут выданы дополнительные поля:

```json
{
    "expires_at": "2015-01-09T17:03:35+0300",
    "response_notifications": false,
    "manager": {
        "id": "1337"
    },
    "hidden": false,
    "branded_template": {
        "id": "marketing",
        "name": "Маркетинг"
    },
    "can_upgrade_billing_type": true
}
```

Имя | Тип | Описание
---- | --- | --------
expires_at | строка | дата и время окончания публикации вакансии
response_notifications | логический | уведомлять ли менеджера о новых откликах
hidden | логический | удалена ли вакансия (скрыта из архива)
can_upgrade_billing_type | логический | Можно ли улучшить биллинговый тип вакансии

В объекте `manager` — информация о менеджере, который разместил данную вакансию.

В объекте `branded_template` — информация об используемом в вакансии
[брендированном шаблоне](employer_vacancy_branded_templates.md).

Также для автора вакансии в объекте `test` доступен ключ `id`, а в объекте
`address` доступны:

```json
{
  "address": {
    "id": "1448",
    "show_metro_only": false
  }
}
```

Подробнее об этих полях вы можете прочитать в разделе о
[публикации вакансии](#creation_fields).

При запросе с авторизацией менеджера, имеющего доступ к откликам по вакансии,
в объекте будет выдано дополнительное поле с различными счётчиками по вакансии:

```json
{
    "counters": {
        "views": 100500,
        "responses": 5,
        "unread_responses": 3,
        "resumes_in_progress": 5,
        "invitations": 10
    }
}
```

Имя | Тип | Описание
---- | --- | --------
counters.views | number | количество просмотров вакансии
counters.responses | number | количество откликов на вакансию
counters.unread_responses | number | количество непросмотренных откликов на вакансию
counters.resumes_in_progress | number | количество резюме в работе на вакансию
counters.invitations | number | количество приглашений на вакансию

### Ошибки

* `404 Not Found` - если вакансия не найдена или у пользователя нет прав на просмотр данной вакансии
* `403 Forbidden` - необходимо пройти капчу (может прийти только, если не передан токен)

Дополнительное описание ошибок:

HTTP code | type | value | описание
----------|------|-------|-----------
403 | captcha_required | captcha_required | [Подробнее о капче](errors_additional.md#captcha_required)

<a name="favorited"></a>
## Отобранные вакансии

Данные методы требуют авторизации соискателем, иначе вернут `403 Forbidden`.

`GET /vacancies/favorited` - возвращает подмножество вакансий, добавленных
пользователем в отобранные.  Пейджинг работает по стандартным page&per_page,
страницы нумеруются с нуля.

`PUT /vacancies/favorited/{vacancy_id}` добавит указанную вакансию в список.
Данная операция — идемпотентная: при добавлении вакансии, которая уже есть в
отобранных, вернётся также `204 No Content`, как и в случае первичного
добавления.

`DELETE /vacancies/favorited/{vacancy_id}` удалит вакансию из списка отобранных
авторизованного пользователя. Операция также идемпотентна. 
При успешном удалении метод возвращает `204 No Content`.

### Ошибки

* `404 Not Found` - если вакансия не найдена 
* `403 Forbidden` - у пользователя не хватает прав
* `403 Forbidden` - при запросе не от имени соискателя
Дополнительно к HTTP коду сервер может вернуть описание [причины ошибки](errors.md#vacancies_favorited).

<a name="search"></a>
## Поиск по вакансиям

### Запрос

`GET /vacancies` вернёт результаты поиска вакансий.

<a name="search-params"></a>
Принимаемые параметры:

> !! Внимание: неизвестные параметры и параметры с ошибкой в названии игнорируются

Некоторые параметры принимают множественные значения: `key=value&key=value`.

* `text` — текстовое поле.  
Переданное значение ищется в полях вакансии, указанных в параметре `search_field`.  
Доступен язык запросов, как и на основном сайте: [https://hh.ru/article/1175](https://hh.ru/article/1175).
Специально для этого поля есть [автодополнение](suggests.md#vacancy-search-keyword).

* `search_field` — область поиска.  
Справочник с возможными значениями: `vacancy_search_fields` в [/dictionaries](dictionaries.md).  
По умолчанию, используются все поля.  
Возможно указание нескольких значений.  

* `experience` — опыт работы.  
Необходимо передавать `id` из справочника `experience` в [/dictionaries](dictionaries.md).  

* `employment` — тип занятости.
Необходимо передавать `id` из справочника `employment` в [/dictionaries](dictionaries.md).  
Возможно указание нескольких значений.  

* `schedule` — график работы.  
Необходимо передавать `id` из справочника `schedule` в [/dictionaries](dictionaries.md).  
Возможно указание нескольких значений.  

* <a name="field-area"></a> `area` — регион.
Необходимо передавать `id` из справочника [/areas](areas.md).    
Возможно указание нескольких значений.  

* `metro` — ветка или станция метро.  
Необходимо передавать `id` из справочника [/metro](metro.md).    
Возможно указание нескольких значений.  

* `specialization` — профобласть или специализация. 
Необходимо передавать `id` из справочника [/specializations](specializations.md).    
Возможно указание нескольких значений. Будет заменен профессиональными ролями (параметр `professional_role`), в настоящее время работает в режиме обратной совместимости.
  
* `industry` - индустрия компании, разместившей вакансию. 
Необходимо передавать `id` из справочника [/industries](industries.md).
Возможно указание нескольких значений.
  
* `employer_id` — идентификатор [компании](employers.md).  
Возможно указание нескольких значений.  

* `currency` — код валюты.  
Справочник с возможными значениями: `currency` (ключ code) в [/dictionaries](dictionaries.md).  
Имеет смысл указывать только совместно с параметром `salary`.

* `salary` — размер заработной платы.  
Если указано это поле, но не указано `currency`, то используется значение RUR у `currency`.  
При указании значения будут найдены вакансии, в которых вилка зарплаты близка к
указанной в запросе. При этом значения пересчитываются по текущим курсам ЦБ РФ.
Например, при указании `salary=100&currency=EUR` будут найдены вакансии, где
вилка зарплаты указана в рублях и после пересчёта в Евро близка к 100 EUR.
По умолчанию будут также найдены вакансии, в которых вилка зарплаты не указана,
чтобы такие вакансии отфильтровать, используйте `only_with_salary=true`.

* `label` — фильтр по меткам вакансий.   
Необходимо передавать `id` из справочника `vacancy_label` в [/dictionaries](dictionaries.md).  
Возможно указание нескольких значений.  

* `only_with_salary` — показывать вакансии только с указанием зарплаты.  
Возможные значения: true или false.  
По умолчанию, используется false.  

* `period` — количество дней, в пределах которых нужно найти вакансии.  
Максимальное значение: 30.

* `date_from` – дата, которая ограничивает снизу диапазон дат публикации
  вакансий.  
  Нельзя передавать вместе с параметром `period`.  
  Значение указывается в формате [ISO 8601](general.md#date-format) -
  `YYYY-MM-DD` или с точность до секунды `YYYY-MM-DDThh:mm:ss±hhmm`.  
  Указанное значение будет округлено до ближайших 5 минут.

* `date_to` – дата, которая ограничивает сверху диапазон дат публикации
  вакансий.  
  Необходимо передавать только в паре с параметром `date_from`.  
  Нельзя передавать вместе с параметром `period`.  
  Значение указывается в формате [ISO 8601](general.md#date-format) -
  `YYYY-MM-DD` или с точность до секунды `YYYY-MM-DDThh:mm:ss±hhmm`.  
  Указанное значение будет округлено до ближайших 5 минут.

* `top_lat`, `bottom_lat`, `left_lng`, `right_lng` — значение гео-координат.  
При поиске используется значение указанного в вакансии адреса.  
Принимаемое значение — градусы в виде десятичной дроби.  
Необходимо передавать одновременно все четыре параметра гео-координат, иначе вернется ошибка.  

* `order_by` — сортировка списка вакансий.  
Справочник с возможными значениями: `vacancy_search_order` в [/dictionaries](dictionaries.md).   
Если выбрана сортировка по удалённости от гео-точки `distance`, необходимо также задать её координаты `sort_point_lat`,`sort_point_lng`.

* `sort_point_lat`, `sort_point_lng` - значение гео-координат точки, по расстоянию от которой будут отсортированы вакансии. Необходимо указывать только, если `order_by` установлено в `distance`.

* `clusters` — возвращать ли [кластеры для данного поиска](clusters.md), по умолчанию: `false`.

* `describe_arguments` — возвращать ли [описание использованных параметров поиска](vacancies_search_arguments.md), по умолчанию: `false`.

* `per_page`, `page` — [параметры пагинации](general.md#pagination). Параметр per_page ограничен значением в 100.

* `no_magic` – Если значение `true` – отключить автоматическое преобразование
  вакансий. По умолчанию – `false`. При включённом автоматическом преобразовании,
  будет предпринята попытка изменить текстовый запрос пользователя на набор
  параметров. Например, запрос `text=москва бухгалтер 100500` будет преобразован
  в `text=бухгалтер&only_with_salary=true&area=1&salary=100500`.

* `premium` – Если значение `true` – в сортировке вакансий будет учтены
  премиум вакансии. Такая сортировка используется на сайте.
  По умолчанию – `false`.

* `responses_count_enabled` — Если значение `true` – включить дополнительное поле `counters` с количеством откликов для вакансии. По-умолчанию – `false`.  

* `part_time` — Вакансии для подработки. Возможные значения:  
  * все элементы из `working_days` в [/dictionaries](dictionaries.md).   
  * все элементы из `working_time_intervals` в [/dictionaries](dictionaries.md).   
  * все элементы из `working_time_modes` в [/dictionaries](dictionaries.md).   
  * элементы `part` или `project` из `employment` в [/dictionaries](dictionaries.md).   
  * элемент `accept_temporary`, показывает вакансии только с временным трудоустройством.  
  
   Возможно указание нескольких значений.  
  
* `professional_role` — профессиональная роль. Необходимо передавать `id` из справочника
  [professional_roles](https://api.hh.ru/openapi/redoc#tag/Spravochniki/paths/~1professional_roles/get).
  Возможно указание нескольких значений. Замена специализациям (параметр `specialization`)

<a name="search-results"></a>

При указании параметров пагинации (page, per_page) работает ограничение: глубина
возвращаемых результатов не может быть больше 2000. Например, возможен запрос
`per_page=10&page=199` (выдача с 1991 по 2000 вакансию), но запрос с
`per_page=10&page=200` вернёт ошибку (выдача с 2001 до 2010 вакансию).

### Ответ

В зависимости от текущей авторизации выдача может отличаться, так как для
соискателей применяется фильтрация по
[списку скрытых вакансий и компаний](blacklisted.md).

Выдача может отличаться при выборе [различных сайтов](hosts.md) (параметр
`host`). Однако выбор регионального сайта, например `hh.kz`, не сужает выборку
до данного региона, для ограничения выборки по региону используйте параметр
[`area`](#field-area).

```json
{
  "per_page": 1,
  "items": [
    {
      "salary": {
        "to": null,
        "from": 30000,
        "currency": "RUR",
        "gross": true
      },
      "name": "Секретарь",
      "insider_interview": {
          "id": "12345",
          "url": "https://hh.ru/interview/12345?employerId=777"
      },
      "area": {
        "url": "https://api.hh.ru/areas/1",
        "id": "1",
        "name": "Москва"
      },
      "url": "https://api.hh.ru/vacancies/8331228",
      "published_at": "2013-07-08T16:17:21+0400",
      "relations": [ ],
      "employer": {
        "logo_urls": {
          "90": "https://hh.ru/employer-logo/289027.png",
          "240": "https://hh.ru/employer-logo/289169.png",
          "original": "https://hh.ru/file/2352807.png"
        },
        "name": "HeadHunter",
        "url": "https://api.hh.ru/employers/1455",
        "alternate_url": "https://hh.ru/employer/1455",
        "id": "1455",
        "trusted": true
      },
      "contacts": {
          "name": "Имя",
          "email": "user@example.com",
          "phones": [
              {
                  "country": "7",
                  "city": "985",
                  "number": "000-00-00",
                  "comment": null
              }
          ]
      },
      "response_letter_required": true,
      "address": {
        "city": "Москва",
        "street": "улица Годовикова",
        "building": "9с10",
        "description": "на проходной потребуется паспорт",
        "lat": 55.807794,
        "lng": 37.638699,
        "metro_stations": [
          {
            "station_id": "6.8",
            "station_name": "Алексеевская",
            "line_id": "6",
            "line_name": "Калужско-Рижская",
            "lat": 55.807794,
            "lng": 37.638699
          }
        ]
      },
      "sort_point_distance": 226.001293,
      "alternate_url": "https://hh.ru/vacancy/8331228",
      "apply_alternate_url": "https://hh.ru/applicant/vacancy_response?vacancyId=8331228",
      "department": {
        "id": "HH-1455-TECH",
        "name": "HeadHunter::Технический департамент"
      },
      "type": {
        "id": "open",
        "name": "Открытая"
      },
      "id": "8331228",
      "has_test": true,
      "response_url": null,
      "snippet": {
          "requirement": "Высшее образование. Опыт работы в качестве <highlighttext>секретаря</highlighttext>, офис-менеджера. Знание делопроизводства, документооборота. Коммуникативные навыки.",
          "responsibility": "Документооборот (регистрация, отправка, контроль исполнения писем, ведение протоколов, отчетность). Распределение корреспонденции. Прием и распределение телефонных звонков."
      },
      "schedule": {
        "id": "fullDay",
        "name": "Полный день"
      },
      "counters": {
        "responses": 0
      }
    }
  ],
  "page": 0,
  "pages": 13,
  "found": 13,
  "clusters": null,
  "arguments": null
}
```

Пример: [https://api.hh.ru/vacancies](https://api.hh.ru/vacancies)

Где помимо [стандартных полей вакансии](#nano) вернутся дополнительные поля:

Имя | Тип | Описание
---- |---- |---------
sort_point_distance | число, null | Расстояние в метрах между центром сортировки (заданной параметрами `sort_point_lat`, `sort_point_lng`) и указанным в вакансии адресом. В случае, если в адресе указаны только станции метро, выдается расстояние между центром сортировки и средней геометрической точкой указанных станций. Значение `sort_point_distance` выдается только в случае, если заданы параметры `sort_point_lat`, `sort_point_lng`, `order_by=distance`
snippet | объект | Дополнительные текстовые снипеты (отрывки) по найденной вакансии. Если в тексте снипета встретилась поисковая фраза (параметр `text`), она будет подсвечена тегом `highlighttext`.
snippet.requirement | строка, null | Отрывок из требований по вакансии, если они найдены в тексте описания.
snippet.responsibility | строка, null | Отрывок из обязанностей по вакансии, если они найдены в тексте описания.
counters.responses | number | Количество откликов на вакансию

Также возможен возврат [кластеров](clusters.md) (ключ `clusters`) и
[использованных параметров](vacancies_search_arguments.md) (ключ `arguments`) для данного поиска.

### Ошибки

* `400 Bad request` - Если параметры переданы с ошибкой
* `403 Forbidden` - Необходимо пройти капчу (может прийти только, если не передан токен)

Дополнительное описание ошибок:

HTTP code | type | value | описание
----------|------|-------|-----------
403 | captcha_required | captcha_required | [Подробнее о капче](errors_additional.md#captcha_required)

<a name="similar"></a>
## Поиск по вакансиям, похожим на вакансию

### Запрос

`GET /vacancies/{vacancy_id}/similar_vacancies`

где `vacancy_id` - идентификатор вакансии.

Принимает те же параметры, что и [поиск по вакансиям](#search-params)

### Ответ

Возвращает результаты в том же виде, что и [поиск по вакансиям](#search-results).

### Ошибки

Возвращает те же ошибки, что и [поиск по вакансиям](#search-results) и дополнительно:
* `404 Not Found` - если вакансия с идентификатором `vacancy_id` не существует

<a name="nano"></a>
## Короткое представление вакансии

```json
{
    "id": "7760476",
    "premium": true,
    "has_test": true,
    "response_url": null,
    "address": null,
    "alternate_url": "https://hh.ru/vacancy/7760476",
    "apply_alternate_url": "https://hh.ru/applicant/vacancy_response?vacancyId=7760476",
    "department": {
        "id": "HH-1455-TECH",
        "name": "HeadHunter::Технический департамент"
    },
    "salary": {
        "to": null,
        "from": 100000,
        "currency": "RUR",
        "gross": true
    },
    "name": "Специалист по автоматизации тестирования (Java, Selenium)",
    "insider_interview": {
        "id": "12345",
        "url": "https://hh.ru/interview/12345?employerId=777"
    },
    "area": {
        "url": "https://api.hh.ru/areas/1",
        "id": "1",
        "name": "Москва"
    },
    "url": "https://api.hh.ru/vacancies/7760476",
    "published_at": "2013-10-11T13:27:16+0400",
    "relations": [],
    "employer": {
        "url": "https://api.hh.ru/employers/1455",
        "alternate_url": "https://hh.ru/employer/1455",
        "logo_urls": {
            "90": "https://hh.ru/employer-logo/289027.png",
            "240": "https://hh.ru/employer-logo/289169.png",
            "original": "https://hh.ru/file/2352807.png"
        },
        "name": "HeadHunter",
        "id": "1455"
    },
    "response_letter_required": false,
    "type": {
        "id": "open",
        "name": "Открытая"
    },
    "archived": "false",
    "working_days": [
        {
            "id": "only_saturday_and_sunday",
            "name": "Работа только по сб и вс"
        }
    ],
    "working_time_intervals": [
        {
            "id": "from_four_to_six_hours_in_a_day",
            "name": "Можно работать сменами по 4-6 часов в день"
        }
    ],
    "working_time_modes": [
        {
            "id": "start_after_sixteen",
            "name": "Можно начинать работать после 16-00"
        }
    ],
    "accept_temporary": false
}
```

Описание полей смотрите в [выдаче полной вакансии](#vacancy-fields).

`url` и `alternate_url` могут принимать значение `null` в случае, если подробная
информация о вакансии недоступна (например, вакансия была удалена).

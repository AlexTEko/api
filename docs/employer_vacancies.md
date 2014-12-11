# Вакансии для работодателя

## Список опубликованных вакансий

`GET /employers/{employer_id}/vacancies/active?manager_id={manager_id}`

Для просмотра списка опубликованных вакансий необходимо указать id менеджера, даже если необходимо сделать запрос для 
текущего менеджера (значение можно взять из `/me`).

Помимо стандартных полей вакансии вернутся дополнительные поля:

```json
{
  "counters": {
    "views": 0,
    "responses": 0,
    "invitations": 0
  },
  "expires_at": "2013-07-08T16:17:21+0400",
  "has_new_messages": false
}
```

ключ                  | тип     | описание
----------------------|---------|---------------------------------------------------------
counters.views        | number  | количество просмотров вакансии  
counters.responses    | number  | количество откликов на вакансию
counters.invitations  | number  | количество приглашений на вакансию
expires_at            | string  | дата окончания публикации вакансии
has_new_messages      | boolean | есть ли новые сообщения в переписках по данной вакансии


### Поддерживаемые параметры 

Помимо стандартных параметров для пагинации `per_page` и `page`, коллекция поддерживает:

* `text` — строка для поиска по названию вакансии
* `area` — id региона (см. [список регионов, в которых есть активные вакансии](employer_vacancy_areas_active.md))
* `order_by` — сортировка вакансий, возможные варианты доступны в справочнике `employer_active_vacancies_order`
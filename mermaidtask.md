## Mermaid: примеры диаграмм
 
Короткие универсальные примеры основных типов диаграмм Mermaid.
---
 
#### 1. Блок-схема (flowchart)
 
```mermaid
graph TD
    Start([Старт]) --> Check{Данные корректны?}
    Check -->|Да| Save[Сохранить в БД]
    Check -->|Нет| Error[Показать ошибку]
    Error --> Fix[Исправить данные]
    Fix --> Check
    Save --> Finish([Готово])
```
 
#### 2. Блок-схема с подграфами
 
```mermaid
flowchart LR
    subgraph Frontend [Клиент]
        A[Форма ввода] --> B[Валидация]
    end
    subgraph Backend [Сервер]
        C[Обработка запроса] --> D[Ответ клиенту]
    end
    B --> C
```
 
#### 3. Формы узлов
 
```mermaid
flowchart LR
    A[Обычный узел]
    B(Скруглённый узел)
    C([Терминал])
    D[[Вложенный процесс]]
    E[(Хранилище)]
    F((Точка))
    G{Условие}
    H{{Решение}}
    A --> B --> C
    D --> E --> F
    G --> H
```
 
#### 4. Диаграмма последовательности (sequenceDiagram)
 
```mermaid
sequenceDiagram
    participant U as Пользователь
    participant S as Сервер
    participant DB as База данных
    U->>S: Отправить форму
    S->>DB: Сохранить запись
    DB-->>S: Подтверждение
    S-->>U: Успешно сохранено
```
 
#### 5. Диаграмма классов (classDiagram)
 
```mermaid
classDiagram
    class Vehicle {
        +String model
        +int year
        +start()
        +stop()
    }
    class Car {
        +openTrunk()
    }
    class Bike {
        +ringBell()
    }
    Vehicle <|-- Car
    Vehicle <|-- Bike
```
 
#### 6. Диаграмма состояний (stateDiagram)
 
```mermaid
stateDiagram-v2
    [*] --> Draft
    Draft --> Review : отправить
    Review --> Approved : одобрить
    Review --> Draft : вернуть на доработку
    Approved --> Published : опубликовать
    Published --> [*]
```
 
#### 7. ER-диаграмма (erDiagram)
 
```mermaid
erDiagram
    AUTHOR ||--o{ BOOK : writes
    BOOK ||--|{ CHAPTER : includes
    AUTHOR {
        int id
        string fullName
    }
    BOOK {
        int id
        string title
        int year
    }
    CHAPTER {
        int id
        string name
        int pages
    }
```
 
#### 8. Диаграмма Ганта (gantt)
 
```mermaid
gantt
    title План разработки
    dateFormat YYYY-MM-DD
    section Проектирование
    Сбор требований :done, a1, 2026-10-01, 4d
    Архитектура :active, a2, after a1, 6d
    section Реализация
    Разработка API :a3, after a2, 8d
    Тестирование :a4, after a3, 4d
```
 
#### 9. Круговая диаграмма (pie)
 
```mermaid
pie title Распределение бюджета
    "Разработка" : 45
    "Маркетинг" : 25
    "Поддержка" : 20
    "Резерв" : 10
```
 
#### 10. Пользовательский путь (journey)
 
```mermaid
journey
    title Путь покупателя
    section Выбор
      Просматривает каталог: 4: Покупатель
      Добавляет в корзину: 5: Покупатель
    section Оформление
      Вводит адрес: 3: Покупатель
      Оплачивает заказ: 4: Покупатель
```
 
#### 11. Git-граф (gitGraph)
 
```mermaid
gitGraph
    commit id: "start"
    branch feature/login
    checkout feature/login
    commit id: "add login"
    commit id: "fix validation"
    checkout main
    merge feature/login
    commit id: "v1.0"
```
 
#### 12. Ментальная карта (mindmap)
 
```mermaid
mindmap
  root((Проект))
    Планирование
      Цели
      Сроки
    Разработка
      Дизайн
      Код
    Запуск
      Тесты
      Релиз
```
 
#### 13. Хронология (timeline)
 
```mermaid
timeline
    title История версий
    2018 : Первый релиз
    2021 : Крупное обновление
    2023 : Редизайн
    2025 : Переход на новую платформу
```





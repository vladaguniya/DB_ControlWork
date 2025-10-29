erDiagram
  КЛІЄНТ {
    int     ID_Клієнта PK
    string  Ім_я
    string  Телефон
    string  Email
  }

  АВТОМОБІЛЬ {
    int     ID_Авто PK
    string  Марка
    string  Модель
    string  Номер
    int     ID_Клієнта FK
  }

  ЗАМОВЛЕННЯ {
    int     ID_Замовлення PK
    date    Дата
    string  Статус
    int     ID_Авто FK
  }

  РОБОТА {
    int     ID_Роботи PK
    string  Назва
    int     Вартість
    int     ID_Майстра FK
    int     ID_Замовлення FK
  }

  МАЙСТЕР {
    int     ID_Майстра PK
    string  Ім_я
    string  Спеціалізація
  }

  АДМІНІСТРАТОР {
    int     ID_Адм PK
    string  Ім_я
    string  Логін
  }

  %% --- Зв’язки ---
  КЛІЄНТ       ||--o{ АВТОМОБІЛЬ   : володіє
  АВТОМОБІЛЬ   ||--o{ ЗАМОВЛЕННЯ  : має
  ЗАМОВЛЕННЯ   ||--o{ РОБОТА      : містить
  МАЙСТЕР      ||--o{ РОБОТА      : виконує
  АДМІНІСТРАТОР ||--o{ МАЙСТЕР    : керує

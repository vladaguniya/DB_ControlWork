erDiagram
  %% === СУТНОСТІ ТА АТРИБУТИ (PK/FK) ===
  Loc {
    int    Locno PK
    string Lname
  }

  Dept {
    int    Deptno PK
    string Dname
    int    Locno FK      %% → Loc.Locno
  }

  Emp {
    int    Empno PK
    string Ename
    string Job
    int    Mgr   FK      %% self-FK → Emp.Empno (менеджер)
    date   Hiredate
    int    Sal
    int    Comm
    int    Deptno FK     %% → Dept.Deptno
  }

  %% === ЗВʼЯЗКИ (кратності) ===
  Loc  ||--o{ Dept : "розміщує"
  Dept ||--o{ Emp  : "містить"
  Emp  ||--o{ Emp  : "керує"   %% 1 менеджер → багато підлеглих

flowchart TD
  %% --- Таблиці ---
  E[Emp]
  D[Dept]
  L[Loc]

  %% --- Вибірки (за не PK/FK полями) ---
  S1[σ Emp.Comm > 0]          %% неключове поле Emp.Comm
  S2[σ Dept.Dname = "IT"]     %% неключове поле Dept.Dname

  %% --- З'єднання (3 таблиці) ---
  J1[⋈ Emp.Deptno = Dept.Deptno]
  J2[⋈ Dept.Locno = Loc.Locno]

  %% --- Проекція (на 1–2 поля) ---
  P[π Emp.Ename, Dept.Dname]

  %% --- Потік виконання ---
  E --> S1
  D --> S2
  S1 --> J1
  S2 --> J1
  J1 --> J2
  L  --> J2
  J2 --> P
